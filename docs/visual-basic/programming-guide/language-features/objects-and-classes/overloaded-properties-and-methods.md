---
title: "Aşırı Yüklenmiş Özellikler ve Yöntemler (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a872540716941ccd0dbb8b058508b89ce26a988
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="dea27-102">Aşırı Yüklenmiş Özellikler ve Yöntemler (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dea27-102">Overloaded Properties and Methods (Visual Basic)</span></span>
<span data-ttu-id="dea27-103">Aşırı yükleme birden fazla yordam, örnek oluşturucusu ya da bir sınıf aynı adlı ancak farklı bağımsız değişken türleri ile özelliğinde oluşturulmasını olur.</span><span class="sxs-lookup"><span data-stu-id="dea27-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="dea27-104">Kullanım aşırı yüklemesi</span><span class="sxs-lookup"><span data-stu-id="dea27-104">Overloading Usage</span></span>  
 <span data-ttu-id="dea27-105">Nesne modeli, farklı veri türlerinde çalışmayabilir yordamlar için aynı adları uygulamadığınız belirleyen aşırı özellikle yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="dea27-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="dea27-106">Örneğin, birkaç farklı veri türlerini görüntülemek için bir sınıf olabilir `Display` şuna yordamları:</span><span class="sxs-lookup"><span data-stu-id="dea27-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 <span data-ttu-id="dea27-107">Aşırı yükleme olmadan aynı şeyi sonraki gösterildiği gibi yaparlar olsa bile her bir yordam için farklı adlar oluşturmanız gerekecek:</span><span class="sxs-lookup"><span data-stu-id="dea27-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 <span data-ttu-id="dea27-108">Aşırı yükleme, kullanılabilir veri türleri seçimine sağladığından özelliklerinin veya yöntemlerin kullanılacağını kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="dea27-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="dea27-109">Örneğin, aşırı yüklenmiş `Display` ele alınan yöntemi daha önce çağrılabilir herhangi bir kod aşağıdaki satırları ile:</span><span class="sxs-lookup"><span data-stu-id="dea27-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 <span data-ttu-id="dea27-110">Çalışma zamanında [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] parametrelerinin veri türleri üzerinde doğru yordamı dayalı aramalar belirtin.</span><span class="sxs-lookup"><span data-stu-id="dea27-110">At run time, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="dea27-111">Kuralları aşırı yüklemesi</span><span class="sxs-lookup"><span data-stu-id="dea27-111">Overloading Rules</span></span>  
 <span data-ttu-id="dea27-112">İki veya daha fazla özelliklerinin veya yöntemlerin aynı ada sahip ekleyerek aşırı yüklenmiş bir üyesi için bir sınıf oluşturun.</span><span class="sxs-lookup"><span data-stu-id="dea27-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="dea27-113">Aşırı yüklenmiş türetilmiş üyeler dışında aşırı yüklenmiş her üyesinin farklı parametre listeleri sahip olması gerekir ve aşağıdaki öğeleri farklılaştırıcı bir özellik olarak bir özellik veya yordam aşırı yüklemesi kullanılamaz:</span><span class="sxs-lookup"><span data-stu-id="dea27-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="dea27-114">Değiştiriciler, gibi `ByVal` veya `ByRef`, üye veya üye parametreleri için geçerli.</span><span class="sxs-lookup"><span data-stu-id="dea27-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="dea27-115">Parametrelerinin adları</span><span class="sxs-lookup"><span data-stu-id="dea27-115">Names of parameters</span></span>  
  
-   <span data-ttu-id="dea27-116">Dönüş türleri yordamları</span><span class="sxs-lookup"><span data-stu-id="dea27-116">Return types of procedures</span></span>  
  
 <span data-ttu-id="dea27-117">`Overloads` Aşırı yüklendiğinde anahtar sözcüğü isteğe bağlı, ancak varsa aşırı üyeyi kullanan `Overloads` anahtar sözcüğü ve ardından diğer tüm aşırı yüklenmiş üyeler aynı ada sahip de belirtmelisiniz bu anahtar sözcük.</span><span class="sxs-lookup"><span data-stu-id="dea27-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="dea27-118">Türetilen sınıflar devralınan üyeleri aynı parametreleri ve parametre türleri olarak da bilinen bir işlem sahip üyeleriyle aşırı yükleme *ad ve imza tarafından gölgeleme*.</span><span class="sxs-lookup"><span data-stu-id="dea27-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="dea27-119">Varsa `Overloads` anahtar sözcük ad ve imza tarafından Gölgeleme, üye uyarlamasını türetilen sınıfın temel sınıf uygulamasında yerine kullanılacak ve bu üye için diğer aşırı yüklemeler için örnekleri kullanılabilir olduğunda kullanılır türetilmiş sınıf.</span><span class="sxs-lookup"><span data-stu-id="dea27-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="dea27-120">Varsa `Overloads` anahtar sözcüğü, aynı parametreleri ve parametre türleri sahip bir üye devralınan bir üyesiyle aşırı yüklendiğinde atlanırsa, ardından aşırı yüklemesi adlı *adıyla gölgeleme*.</span><span class="sxs-lookup"><span data-stu-id="dea27-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="dea27-121">Ada göre gölgeleme üyesi devralınan uyarlamasını değiştirir ve, tüm diğer aşırı yüklemeler türetilmiş sınıf ve kendi decedents örnekleri için kullanılamaz hale getirir.</span><span class="sxs-lookup"><span data-stu-id="dea27-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="dea27-122">`Overloads` Ve `Shadows` değiştiricileri hem kullanılamaz aynı özellik veya yöntem.</span><span class="sxs-lookup"><span data-stu-id="dea27-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="dea27-123">Örnek</span><span class="sxs-lookup"><span data-stu-id="dea27-123">Example</span></span>  
 <span data-ttu-id="dea27-124">Aşağıdaki örnek, ya da kabul aşırı yüklenmiş yöntemler oluşturur bir `String` veya `Decimal` dolar tutar ve return vergi içeren bir dize gösterimi.</span><span class="sxs-lookup"><span data-stu-id="dea27-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="dea27-125">Aşırı yüklenmiş yöntemin oluşturmak için bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="dea27-125">To use this example to create an overloaded method</span></span>  
  
1.  <span data-ttu-id="dea27-126">Yeni bir proje açın ve adlı bir sınıf ekleyin `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="dea27-126">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="dea27-127">Aşağıdaki kodu ekleyin `TaxClass` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="dea27-127">Add the following code to the `TaxClass` class.</span></span>  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  <span data-ttu-id="dea27-128">Aşağıdaki yordam formunuza ekleyin.</span><span class="sxs-lookup"><span data-stu-id="dea27-128">Add the following procedure to your form.</span></span>  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  <span data-ttu-id="dea27-129">Arama ve form düğme ekleme `ShowTax` yordamdan `Button1_Click` düğmesinin olayı.</span><span class="sxs-lookup"><span data-stu-id="dea27-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="dea27-130">Projeyi çalıştırın ve aşırı yüklenmiş sınamak için formu düğmeyi tıklatın `ShowTax` yordamı.</span><span class="sxs-lookup"><span data-stu-id="dea27-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="dea27-131">Çalışma zamanında derleyici kullanılmasını parametrelerini eşleşen uygun aşırı yüklenmiş işlevi seçer.</span><span class="sxs-lookup"><span data-stu-id="dea27-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="dea27-132">Düğmeye tıkladığınızda, aşırı yüklenmiş yöntemin önce çağrılır bir `Price` bir dize ve "Fiyat bir dizedir. ileti, parametre</span><span class="sxs-lookup"><span data-stu-id="dea27-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="dea27-133">Vergi is $5,12" görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="dea27-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="dea27-134">`TaxAmount`ile adlı bir `Decimal` ikinci kez ve iletiyi değer, "Fiyat bir ondalık sayı.</span><span class="sxs-lookup"><span data-stu-id="dea27-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="dea27-135">Vergi is $5,12" görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="dea27-135">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea27-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dea27-136">See Also</span></span>  
 [<span data-ttu-id="dea27-137">Nesneler ve sınıflar</span><span class="sxs-lookup"><span data-stu-id="dea27-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="dea27-138">Visual Basic'de gölgeleme</span><span class="sxs-lookup"><span data-stu-id="dea27-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="dea27-139">Sub deyimi</span><span class="sxs-lookup"><span data-stu-id="dea27-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="dea27-140">Devralma temelleri</span><span class="sxs-lookup"><span data-stu-id="dea27-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="dea27-141">Gölgeleri</span><span class="sxs-lookup"><span data-stu-id="dea27-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="dea27-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="dea27-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [<span data-ttu-id="dea27-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="dea27-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [<span data-ttu-id="dea27-144">Aşırı yüklemeler</span><span class="sxs-lookup"><span data-stu-id="dea27-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="dea27-145">Gölgeleri</span><span class="sxs-lookup"><span data-stu-id="dea27-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)