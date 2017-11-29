---
title: "Mikro hizmet etki alanı modeli .NET Core ile uygulama"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Mikro hizmet etki alanı modeli .NET Core ile uygulama"
keywords: "Docker, mikro, ASP.NET, kapsayıcı"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a><span data-ttu-id="622de-104">Mikro hizmet etki alanı modeli .NET Core ile uygulama</span><span class="sxs-lookup"><span data-stu-id="622de-104">Implementing a microservice domain model with .NET Core</span></span> 

<span data-ttu-id="622de-105">Önceki bölümde temel tasarım ilkeleri ve etki alanı modeli tasarlama modeller açıklandığı.</span><span class="sxs-lookup"><span data-stu-id="622de-105">In the previous section, the fundamental design principles and patterns for designing a domain model were explained.</span></span> <span data-ttu-id="622de-106">.NET Core kullanarak etki alanı modeli uygulamak için olası yollarını keşfetmek şimdi (düz C\# kodu) ve EF çekirdek.</span><span class="sxs-lookup"><span data-stu-id="622de-106">Now it is time to explore possible ways to implement the domain model by using .NET Core (plain C\# code) and EF Core.</span></span> <span data-ttu-id="622de-107">Etki alanı modeli yalnızca kodunuzu oluşan unutmayın.</span><span class="sxs-lookup"><span data-stu-id="622de-107">Note that your domain model will be composed simply of your code.</span></span> <span data-ttu-id="622de-108">EF üzerinde yalnızca EF çekirdek modeli gereksinimleri ancak değil gerçek bağımlılıkları gerekir.</span><span class="sxs-lookup"><span data-stu-id="622de-108">It will have just the EF Core model requirements, but not real dependencies on EF.</span></span> <span data-ttu-id="622de-109">Etki alanı modelinizde sabit bağımlılıklar veya EF çekirdek veya diğer ORM başvuruları olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="622de-109">You should not have hard dependencies or references to EF Core or any other ORM in your domain model.</span></span>

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a><span data-ttu-id="622de-110">Özel bir .NET standart Kitaplığı'nda etki alanı modeli yapısı</span><span class="sxs-lookup"><span data-stu-id="622de-110">Domain model structure in a custom .NET Standard library</span></span>

<span data-ttu-id="622de-111">EShopOnContainers başvuru uygulaması için kullanılan klasör kuruluş uygulama DDD modeli gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="622de-111">The folder organization used for the eShopOnContainers reference application demonstrates the DDD model for the application.</span></span> <span data-ttu-id="622de-112">Farklı bir klasör kuruluş uygulamanız için yapılan tasarım seçenekleri daha net bir şekilde iletişim kurar bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="622de-112">You might find that a different folder organization more clearly communicates the design choices made for your application.</span></span> <span data-ttu-id="622de-113">Şekil 9-10'gördüğünüz sıralama etki alanı modelinde var. iki toplamalar, sipariş toplama ve alıcı toplama</span><span class="sxs-lookup"><span data-stu-id="622de-113">As you can see in Figure 9-10, in the ordering domain model there are two aggregates, the order aggregate and the buyer aggregate.</span></span> <span data-ttu-id="622de-114">Bir tek etki alanı varlığı (Birleşik kök veya kök varlık) de oluşan bir toplama olabilir ancak her toplama etki alanı varlıkları ve değer nesnelerin grubudur.</span><span class="sxs-lookup"><span data-stu-id="622de-114">Each aggregate is a group of domain entities and value objects, although you could have an aggregate composed of a single domain entity (the aggregate root or root entity) as well.</span></span>

![](./media/image11.png)

<span data-ttu-id="622de-115">**Şekil 9-10**.</span><span class="sxs-lookup"><span data-stu-id="622de-115">**Figure 9-10**.</span></span> <span data-ttu-id="622de-116">EShopOnContainers içinde sıralama mikro hizmet için etki alanı modeli yapısı</span><span class="sxs-lookup"><span data-stu-id="622de-116">Domain model structure for the ordering microservice in eShopOnContainers</span></span>

<span data-ttu-id="622de-117">Ayrıca, etki alanı modeli katmanı, etki alanı modelinin altyapı gereksinimleri olan depo sözleşmeleri (arabirimler) içerir.</span><span class="sxs-lookup"><span data-stu-id="622de-117">Additionally, the domain model layer includes the repository contracts (interfaces) that are the infrastructure requirements of your domain model.</span></span> <span data-ttu-id="622de-118">Diğer bir deyişle, bu arabirimleri altyapısı katmanından uygulanmalı hangi depoları express ve nasıl.</span><span class="sxs-lookup"><span data-stu-id="622de-118">In other words, these interfaces express what repositories the infrastructure layer must implement and how.</span></span> <span data-ttu-id="622de-119">Etki alanı modeli katmanı "API veya Entity Framework gibi altyapısı teknolojileri sınıflardan contaminated olmayan şekilde" depoları uygulama etki alanı modeli katmanı altyapı Katmanı kitaplığı dışında yerleştirilen önemlidir.</span><span class="sxs-lookup"><span data-stu-id="622de-119">It is critical that the implementation of the repositories be placed outside of the domain model layer, in the infrastructure layer library, so the domain model layer is not “contaminated” by API or classes from infrastructure technologies, like Entity Framework.</span></span>

<span data-ttu-id="622de-120">Ayrıca bkz bir [SeedWork](https://martinfowler.com/bliki/Seedwork.html) etki alanı varlıkları ve değeri için temel olarak kullanabileceğiniz özel temel sınıflar içeren klasörü nesneleri, her etki alanının nesne sınıfında yedekli kodu içermeyen şekilde.</span><span class="sxs-lookup"><span data-stu-id="622de-120">You can also see a [SeedWork](https://martinfowler.com/bliki/Seedwork.html) folder that contains custom base classes that you can use as a base for your domain entities and value objects, so you do not have redundant code in each domain’s object class.</span></span>

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a><span data-ttu-id="622de-121">Özel bir .NET standart kitaplığında toplamalar yapılandırma</span><span class="sxs-lookup"><span data-stu-id="622de-121">Structuring aggregates in a custom .NET Standard library</span></span>

<span data-ttu-id="622de-122">Bir toplama etki alanı nesnelerini işlemsel tutarlılık eşleştirmek için bir arada gruplandırılmış bir kümeye başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="622de-122">An aggregate refers to a cluster of domain objects grouped together to match transactional consistency.</span></span> <span data-ttu-id="622de-123">Bu nesneler (biri toplama kök veya kök varlık olan) varlıkları herhangi bir ek değer nesne olabilir.</span><span class="sxs-lookup"><span data-stu-id="622de-123">Those objects could be instances of entities (one of which is the aggregate root or root entity) plus any additional value objects.</span></span>

<span data-ttu-id="622de-124">İşlemsel tutarlılık toplama tutarlı ve bir iş eylemi sonunda güncel olması sağlanır anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="622de-124">Transactional consistency means that an aggregate is guaranteed to be consistent and up to date at the end of a business action.</span></span> <span data-ttu-id="622de-125">Örneğin, Şekil 9-11'de gösterildiği gibi sipariş toplama mikro hizmet etki alanı modeli sıralama eShopOnContainers öğesinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="622de-125">For example, the order aggregate from the eShopOnContainers ordering microservice domain model is composed as shown in Figure 9-11.</span></span>

![](./media/image12.png)

<span data-ttu-id="622de-126">**Şekil 9-11**.</span><span class="sxs-lookup"><span data-stu-id="622de-126">**Figure 9-11**.</span></span> <span data-ttu-id="622de-127">Visual Studio çözümünde toplama sırası</span><span class="sxs-lookup"><span data-stu-id="622de-127">The order aggregate in Visual Studio solution</span></span>

<span data-ttu-id="622de-128">Birleşik bir klasörde bulunan dosyalardan herhangi birinin açarsanız, nasıl özel bir temel sınıf ya da varlık veya değer nesnesi gibi arabirimi olarak işaretlenmiş uygulanan gibi gördüğünüz [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) klasör.</span><span class="sxs-lookup"><span data-stu-id="622de-128">If you open any of the files in an aggregate folder, you can see how it is marked as either a custom base class or interface, like entity or value object, as implemented in the [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) folder.</span></span>

## <a name="implementing-domain-entities-as-poco-classes"></a><span data-ttu-id="622de-129">Etki alanı varlıklar POCO sınıflarını uygulama</span><span class="sxs-lookup"><span data-stu-id="622de-129">Implementing domain entities as POCO classes</span></span>

<span data-ttu-id="622de-130">Etki alanı varlıklarınızı uygulamak POCO sınıfları oluşturarak .NET içinde bir etki alanı modeli uygular.</span><span class="sxs-lookup"><span data-stu-id="622de-130">You implement a domain model in .NET by creating POCO classes that implement your domain entities.</span></span> <span data-ttu-id="622de-131">Aşağıdaki örnekte, sipariş sınıfı bir varlık ve ayrıca bir toplama kök olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="622de-131">In the following example, the Order class is defined as an entity and also as an aggregate root.</span></span> <span data-ttu-id="622de-132">Sipariş sınıfı varlık temel sınıfından türetilen çünkü varlıklarla ilgili ortak kodun yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="622de-132">Because the Order class derives from the Entity base class, it can reuse common code related to entities.</span></span> <span data-ttu-id="622de-133">Bu nedenle kodu, olmayan bir ORM EF gibi altyapı kod bu temel sınıflar ve arabirimler sizin tarafınızdan etki alanı modeli projesi tanımlandığından emin aklınızda size aittir.</span><span class="sxs-lookup"><span data-stu-id="622de-133">Bear in mind that these base classes and interfaces are defined by you in the domain model project, so it is your code, not infrastructure code from an ORM like EF.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

<span data-ttu-id="622de-134">Bu bir POCO sınıfı olarak uygulanan bir etki alanı varlığı olduğunu dikkate almak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="622de-134">It is important to note that this is a domain entity implemented as a POCO class.</span></span> <span data-ttu-id="622de-135">Entity Framework Çekirdek doğrudan bağımlılıkları veya başka bir altyapı framework yok.</span><span class="sxs-lookup"><span data-stu-id="622de-135">It does not have any direct dependency on Entity Framework Core or any other infrastructure framework.</span></span> <span data-ttu-id="622de-136">Bu olmalıdır gibi yalnızca C uygulamasıdır\# etki alanı modeli uygulama kodu.</span><span class="sxs-lookup"><span data-stu-id="622de-136">This implementation is as it should be, just C\# code implementing a domain model.</span></span>

<span data-ttu-id="622de-137">Ayrıca, sınıf IAggregateRoot adlı bir arabirim ile donatılmış.</span><span class="sxs-lookup"><span data-stu-id="622de-137">In addition, the class is decorated with an interface named IAggregateRoot.</span></span> <span data-ttu-id="622de-138">Bu arabirim bazen adlı boş bir arabirim olduğundan bir *işaret arabirimi*, yani yalnızca bu varlık sınıfı ayrıca bir toplama kök olduğunu göstermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="622de-138">That interface is an empty interface, sometimes called a *marker interface*, that is used just to indicate that this entity class is also an aggregate root.</span></span>

<span data-ttu-id="622de-139">Bir işaretçi arabirimi bazen koruma deseni olarak değerlendirilir. Ancak, bu da bu arabirimi özellikle gelişen sonra bir sınıf olarak işaretlemek için bir temiz yoludur.</span><span class="sxs-lookup"><span data-stu-id="622de-139">A marker interface is sometimes considered as an anti-pattern; however, it is also a clean way to mark a class, especially when that interface might be evolving.</span></span> <span data-ttu-id="622de-140">Bir öznitelik işaret için diğer seçim olabilir, ancak bir toplama özniteliği işaretleyici sınıfı yukarıda koyma yerine IAggregate arabirimi yanındaki taban sınıfı (varlık) görmek hızlıdır.</span><span class="sxs-lookup"><span data-stu-id="622de-140">An attribute could be the other choice for the marker, but it is quicker to see the base class (Entity) next to the IAggregate interface instead of putting an Aggregate attribute marker above the class.</span></span> <span data-ttu-id="622de-141">Metter Tercihler, herhangi bir durumda değil.</span><span class="sxs-lookup"><span data-stu-id="622de-141">It is a metter of preferences, in any case.</span></span>

<span data-ttu-id="622de-142">Bu kod çoğunu tutarlılık için ilgili iş kuralları toplama 's varlıkların sipariş toplama kök sınıfı (toplama ÖgeSipariş nesneyi eklerken, örneğin, AddOrderItem) yöntemleri olarak uygulanmalıdır bir toplama kök anlamına sahip .</span><span class="sxs-lookup"><span data-stu-id="622de-142">Having an aggregate root means that most of the code related to consistency and business rules of the aggregate’s entities should be implemented as methods in the Order aggregate root class (for example, AddOrderItem when adding an OrderItem object to the aggregate).</span></span> <span data-ttu-id="622de-143">Oluşturma veya gerekir OrderItems nesneleri bağımsız olarak veya doğrudan güncelleştirme; AggregateRoot sınıfı, Denetim ve onun alt varlıkları karşı herhangi bir güncelleştirme işlemi tutarlılığını tutmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="622de-143">You should not create or update OrderItems objects independently or directly; the AggregateRoot class must keep control and consistency of any update operation against its child entities.</span></span>

<span data-ttu-id="622de-144">Örneğin, aşağıdakileri yapmalısınız *değil* herhangi bir sınıftan komut işleyici yöntemi veya uygulama katmanı aşağıdakileri yapın:</span><span class="sxs-lookup"><span data-stu-id="622de-144">For example, you should *not* do the following from any command handler method or application layer class:</span></span>

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

<span data-ttu-id="622de-145">Bu durumda, ekleme yöntemi OrderItems koleksiyona doğrudan erişimi olan veri eklemek için yalnızca bir işlemidir.</span><span class="sxs-lookup"><span data-stu-id="622de-145">In this case, the Add method is purely an operation to add data, with direct access to the OrderItems collection.</span></span> <span data-ttu-id="622de-146">Bu nedenle, etki alanı mantığı, kurallar veya doğrulamaları en alt varlıkları işlemiyle uygulama katmanı (komut işleyicileri ve Web API denetleyicilerinin) yayılan ilgili.</span><span class="sxs-lookup"><span data-stu-id="622de-146">Therefore, most of the domain logic, rules, or validations related to that operation with the child entities will be spread across the application layer (command handlers and Web API controllers).</span></span>

<span data-ttu-id="622de-147">Toplama kök giderseniz, toplama kök kendi invariants, kendi geçerlilik ya da kendi tutarlılığı garanti edemez.</span><span class="sxs-lookup"><span data-stu-id="622de-147">If you go around the aggregate root, the aggregate root cannot guarantee its invariants, its validity, or its consistency.</span></span> <span data-ttu-id="622de-148">Sonunda spaghetti kod veya işlem bir kod sahip olur.</span><span class="sxs-lookup"><span data-stu-id="622de-148">Eventually you will have spaghetti code or transactional script code.</span></span>

<span data-ttu-id="622de-149">DDD desenleri izlemek için varlıkları ortak ayarlayıcılar herhangi bir varlık özellik olmaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="622de-149">To follow DDD patterns, entities must not have public setters in any entity property.</span></span> <span data-ttu-id="622de-150">Bir varlık değişiklikleri varlıkta performans gösterdiğini değişikliği açık bulunabilen dil açık yöntemleriyle yönlendirilir.</span><span class="sxs-lookup"><span data-stu-id="622de-150">Changes in an entity should be driven by explicit methods with explicit ubiquitous language about the change they are performing in the entity.</span></span>

<span data-ttu-id="622de-151">Ayrıca, varlık (örneğin, sipariş öğeleri) içindeki koleksiyonlar salt okunur özellikler olmalıdır (daha sonra AsReadOnly yöntemi açıklanmıştır).</span><span class="sxs-lookup"><span data-stu-id="622de-151">Furthermore, collections within the entity (like the order items) should be read-only properties (the AsReadOnly method explained later).</span></span> <span data-ttu-id="622de-152">Birleşik kök sınıf yöntemlerini ya da alt varlık yöntemleri içinde yalnızca güncelleştirmeniz.</span><span class="sxs-lookup"><span data-stu-id="622de-152">You should be able to update it only from within the aggregate root class methods or the child entity methods.</span></span>

<span data-ttu-id="622de-153">Sipariş toplama kök kodunda görebileceğiniz gibi varlık sınıfı yöntemleri aracılığıyla gerçekleştirilmek üzere varlığın veri ya da kendi alt varlıkları karşı herhangi bir işlem sahip olması tüm ayarlayıcılar harici olarak özel veya salt okunur en az olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="622de-153">As you can see in the code for the Order aggregate root, all setters should be private or at least read-only externally, so that any operation against the entity’s data or its child entities has to be performed through methods in the entity class.</span></span> <span data-ttu-id="622de-154">Bu işlem komut dosyası kod uygulama yerine denetimli ve nesne yönelimli bir yolla tutarlılık tutar.</span><span class="sxs-lookup"><span data-stu-id="622de-154">This maintains consistency in a controlled and object-oriented way instead of implementing transactional script code.</span></span>

<span data-ttu-id="622de-155">Aşağıdaki kod parçacığını sipariş toplama ÖgeSipariş nesne ekleme görevini kod için uygun şekilde gösterir.</span><span class="sxs-lookup"><span data-stu-id="622de-155">The following code snippet shows the proper way to code the task of adding an OrderItem object to the Order aggregate.</span></span>

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

<span data-ttu-id="622de-156">Bu parçacığında, sipariş toplama kök denetiminde doğrulamaları ya da bir ÖgeSipariş nesnesinin oluşturulmasını ilişkili mantığını çoğu olacaktır — AddOrderItem yönteminde — özellikle doğrulamaları ve mantığı ilgili diğer öğelere toplama.</span><span class="sxs-lookup"><span data-stu-id="622de-156">In this snippet, most of the validations or logic related to the creation of an OrderItem object will be under the control of the Order aggregate root—in the AddOrderItem method—especially validations and logic related to other elements in the aggregate.</span></span> <span data-ttu-id="622de-157">Örneğin, AddOrderItem için birden fazla çağrı sonucunu ile aynı ürün alabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="622de-157">For instance, you might get the same product item as the result of multiple calls to AddOrderItem.</span></span> <span data-ttu-id="622de-158">Bu yöntemde, ürün öğeleri inceleyin ve birkaç birimleri ile tek bir ÖgeSipariş nesne aynı ürün öğeleri birleştirir.</span><span class="sxs-lookup"><span data-stu-id="622de-158">In that method, you could examine the product items and consolidate the same product items into a single OrderItem object with several units.</span></span> <span data-ttu-id="622de-159">Ayrıca, farklı iskonto tutarlarının vardır, ancak ürün kimliği aynı olduğundan, büyük olasılıkla daha yüksek indirim uygular.</span><span class="sxs-lookup"><span data-stu-id="622de-159">Additionally, if there are different discount amounts but the product ID is the same, you would likely apply the higher discount.</span></span> <span data-ttu-id="622de-160">Bu ilkeyi ÖgeSipariş nesne için başka bir etki alanı mantığı uygular.</span><span class="sxs-lookup"><span data-stu-id="622de-160">This principle applies to any other domain logic for the OrderItem object.</span></span>

<span data-ttu-id="622de-161">Ayrıca, yeni OrderItem(params) işlemi de denetimli ve olması sipariş toplama kök AddOrderItem yöntemi tarafından gerçekleştirilen.</span><span class="sxs-lookup"><span data-stu-id="622de-161">In addition, the new OrderItem(params) operation will also be controlled and performed by the AddOrderItem method from the Order aggregate root.</span></span> <span data-ttu-id="622de-162">Bu nedenle, mantığı ya da doğrulamaları çoğunu işlemi (özellikle her şey, diğer alt varlıklar arasında tutarlılığı etkiler) toplama kök içinde tek bir yerde olacağını ilgili.</span><span class="sxs-lookup"><span data-stu-id="622de-162">Therefore, most of the logic or validations related to that operation (especially anything that impacts the consistency between other child entities) will be in a single place within the aggregate root.</span></span> <span data-ttu-id="622de-163">Birleşik kök düzeni nihai amacı olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="622de-163">That is the ultimate purpose of the aggregate root pattern.</span></span>

<span data-ttu-id="622de-164">Entity Framework 1.1 kullandığınızda, Entity Framework Çekirdek 1.1 yeni özelliklerden biri izin verdiğini olduğundan DDD varlık daha iyi ifade edilebilir [alanlarına eşleme](https://docs.microsoft.com/ef/core/modeling/backing-field) özellikleri yanı sıra.</span><span class="sxs-lookup"><span data-stu-id="622de-164">When you use Entity Framework 1.1, a DDD entity can be better expressed because one of the new features of Entity Framework Core 1.1 is that it allows [mapping to fields](https://docs.microsoft.com/ef/core/modeling/backing-field) in addition to properties.</span></span> <span data-ttu-id="622de-165">Bu, alt varlıkları veya değer nesnelerini koleksiyonları korurken faydalı olur.</span><span class="sxs-lookup"><span data-stu-id="622de-165">This is useful when protecting collections of child entities or value objects.</span></span> <span data-ttu-id="622de-166">Bu geliştirme ile özellikleri yerine basit özel alanlar kullanabilirsiniz ve herhangi bir güncelleştirme alan koleksiyonuna ortak yöntemleri uygulamak ve AsReadOnly yöntemi aracılığıyla salt okunur erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="622de-166">With this enhancement, you can use simple private fields instead of properties and you can implement any update to the field collection in public methods and provide read-only access through the AsReadOnly method.</span></span>

<span data-ttu-id="622de-167">Yöntemleri herhangi değişmeyen ve veri tutarlılığını denetlemek için varlık (veya oluşturucusu) aracılığıyla yalnızca varlık güncelleştirmek istediğiniz GGG böylece yalnızca bir get erişimcisine özellikleri tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="622de-167">In DDD you want to update the entity only through methods in the entity (or the constructor) in order to control any invariant and the consistency of the data, so properties are defined only with a get accessor.</span></span> <span data-ttu-id="622de-168">Özellikler özel alanları tarafından desteklenir.</span><span class="sxs-lookup"><span data-stu-id="622de-168">The properties are backed by private fields.</span></span> <span data-ttu-id="622de-169">Özel üyelerin yalnızca sınıf içinde erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="622de-169">Private members can only be accessed from within the class.</span></span> <span data-ttu-id="622de-170">Ancak, burada bir özel durum: EF çekirdek de bu alanları ayarlayın gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="622de-170">However, there one exception: EF Core needs to set these fields as well.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a><span data-ttu-id="622de-171">Eşleme özellikleri yalnızca alanları veritabanı tablosunda get erişimcileri</span><span class="sxs-lookup"><span data-stu-id="622de-171">Mapping properties with only get accessors to the fields in the database table</span></span>

<span data-ttu-id="622de-172">Veritabanı tablo sütunlarına eşleme özellikleri bir etki alanı sorumluluğu ancak altyapı ve kalıcılığı katmanının bir parçası değil.</span><span class="sxs-lookup"><span data-stu-id="622de-172">Mapping properties to the database table columns is not a domain responsibility, but part of the infrastructure and persistence layer.</span></span> <span data-ttu-id="622de-173">EF varlıkları nasıl model oluşturabilirsiniz için ilgili 1.1'nda yeni özelliklerden haberdar; bu nedenle, biz bu burada yalnızca Bahsediyor.</span><span class="sxs-lookup"><span data-stu-id="622de-173">We mention this here just so you are aware of the new capabilities in EF 1.1 related to how you can model entities.</span></span> <span data-ttu-id="622de-174">Bu konu hakkında daha fazla ayrıntı altyapı ve kalıcılığı bölümünde açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="622de-174">Additional details on this topic are explained in the infrastructure and persistence section.</span></span>

<span data-ttu-id="622de-175">DbContext içinde EF 1.0 kullandığınızda, yalnızca veritabanı tablosunun gerçek alanlarla alıcıları ile tanımlanmış özellikleri eşlemek gerekir.</span><span class="sxs-lookup"><span data-stu-id="622de-175">When you use EF 1.0, within the DbContext you need to map the properties that are defined only with getters to the actual fields in the database table.</span></span> <span data-ttu-id="622de-176">Bu DataGrid'i sınıfı HasField yöntemi ile gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="622de-176">This is done with the HasField method of the PropertyBuilder class.</span></span>

### <a name="mapping-fields-without-properties"></a><span data-ttu-id="622de-177">Özellikleri olmayan alanlarını eşleme</span><span class="sxs-lookup"><span data-stu-id="622de-177">Mapping fields without properties</span></span>

<span data-ttu-id="622de-178">EF çekirdek 1. 1'i sütunları alanlarına eşlemek için yeni özellik ile aynı zamanda özellikleri kullanmamayı mümkündür.</span><span class="sxs-lookup"><span data-stu-id="622de-178">With the new feature in EF Core 1.1 to map columns to fields, it is also possible to not use properties.</span></span> <span data-ttu-id="622de-179">Bunun yerine, yalnızca bir tablodaki sütunların alanlara eşleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="622de-179">Instead, you can just map columns from a table to fields.</span></span> <span data-ttu-id="622de-180">Bu genel bir kullanım örneği özel alanlar için varlık erişilecek gerekmez bir iç durum modudur.</span><span class="sxs-lookup"><span data-stu-id="622de-180">A common use case for this is private fields for an internal state that does not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="622de-181">Örneğin, önceki örnekte kod, \_someOrderInternalState alan ayarlayıcı veya alıcı için ilgili hiçbir özelliğe sahiptir.</span><span class="sxs-lookup"><span data-stu-id="622de-181">For example, in the preceding code example, the \_someOrderInternalState field has no related property for either a setter or getter.</span></span> <span data-ttu-id="622de-182">Bu alan da sipariş iş mantığı içinde hesaplanır ve sipariş yöntemleri kullanılır, ancak veritabanında kalıcı hale getirmek gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="622de-182">That field will also be calculated within the order’s business logic and used from the order’s methods, but it needs to be persisted in the database as well.</span></span> <span data-ttu-id="622de-183">Bu nedenle, EF 1.1 ilgili bir özellik olmayan bir alan veritabanında bir sütunun eşlemek için bir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="622de-183">So, in EF 1.1 there is a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="622de-184">Bu ayrıca içinde açıklanan [altyapısı katmanından](#the-infrastructure-layer) başlığına bakın.</span><span class="sxs-lookup"><span data-stu-id="622de-184">This is also explained in the [Infrastructure layer](#the-infrastructure-layer) section of this guide.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="622de-185">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="622de-185">Additional resources</span></span>

-   <span data-ttu-id="622de-186">**Vaughn Vernon. Toplamalar DDD ve Entity Framework ile modelleme.**</span><span class="sxs-lookup"><span data-stu-id="622de-186">**Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework.**</span></span> <span data-ttu-id="622de-187">Bu Not *değil* Entity Framework Çekirdek.</span><span class="sxs-lookup"><span data-stu-id="622de-187">Note that this is *not* Entity Framework Core.</span></span>
    [<span data-ttu-id="622de-188">*https://vaughnvernon.co/?p=879*</span><span class="sxs-lookup"><span data-stu-id="622de-188">*https://vaughnvernon.co/?p=879*</span></span>](https://vaughnvernon.co/?p=879)

-   <span data-ttu-id="622de-189">**Julie Lerman. Etki alanı Odaklı Tasarım kodlama: Veri odaklı Devs için ipuçları**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span><span class="sxs-lookup"><span data-stu-id="622de-189">**Julie Lerman. Coding for Domain-Driven Design: Tips for Data-Focused Devs**
[*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span></span>

-   <span data-ttu-id="622de-190">**UDI Dahan. Etki alanı modelleri tam oluşturma kapsüllenmiş**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="622de-190">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="622de-191">[Önceki] (mikro hizmet-etki-model.md) [sonraki] (seedwork-domain-model-base-classes-interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="622de-191">[Previous] (microservice-domain-model.md) [Next] (seedwork-domain-model-base-classes-interfaces.md)</span></span>