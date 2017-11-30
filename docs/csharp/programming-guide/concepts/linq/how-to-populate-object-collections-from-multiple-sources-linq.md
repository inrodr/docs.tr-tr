---
title: "Nasıl yapılır: (LINQ) (C#) birden fazla kaynaktan nesne koleksiyonları doldurma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 8ad7d480-b46c-4ccc-8c57-76f2d04ccc6d
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a3d3f0f9380e13addac38e32d4cc095d60e19bcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-c"></a><span data-ttu-id="ff89a-102">Nasıl yapılır: (LINQ) (C#) birden fazla kaynaktan nesne koleksiyonları doldurma</span><span class="sxs-lookup"><span data-stu-id="ff89a-102">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>
<span data-ttu-id="ff89a-103">Bu örnek, verilerin farklı kaynaklardan yeni türleri dizisi nasıl birleştirileceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="ff89a-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff89a-104">Bir veritabanı hala verilerle dosya sistemindeki bellek içi veri ya da veri katılmaya çalışmayın.</span><span class="sxs-lookup"><span data-stu-id="ff89a-104">Do not try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="ff89a-105">Bu tür etki alanları arası birleşimler, birleştirme işlemleri veritabanı sorguları ve diğer kaynakları türleri için tanımlanabilir farklı yolları nedeniyle tanımsız sonuçlara yol açabilir.</span><span class="sxs-lookup"><span data-stu-id="ff89a-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="ff89a-106">Ayrıca, veritabanındaki veri miktarını yeterince büyük ise böyle bir işlem, bellek yetersiz özel durum neden olabilecek bir risk vardır.</span><span class="sxs-lookup"><span data-stu-id="ff89a-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="ff89a-107">Bellek içi veri bir veritabanından veri katılmak için ilk çağrı `ToList` veya `ToArray` veritabanında sorgu ve birleştirme döndürülen koleksiyonda gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="ff89a-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="ff89a-108">Veri dosyası oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="ff89a-108">To create the data file</span></span>  
  
-   <span data-ttu-id="ff89a-109">Bölümünde açıklandığı gibi names.csv ve scores.csv dosyalarını proje klasörünüze kopyalayın [nasıl yapılır: içerik katılma öğesinden farklı dosyaları (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span><span class="sxs-lookup"><span data-stu-id="ff89a-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff89a-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="ff89a-110">Example</span></span>  
 <span data-ttu-id="ff89a-111">Aşağıdaki örnekte bir adlandırılmış türü kullanmayı gösterir `Student` elektronik tablo verileri .csv biçiminde benzetimini dizeleri iki bellek içi koleksiyonundan birleştirilmiş verileri depolamak için.</span><span class="sxs-lookup"><span data-stu-id="ff89a-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="ff89a-112">Dizeleri ilk koleksiyonu Öğrenci adları ve kimlikleri ve ikinci koleksiyon Öğrenci Kimliğini (ilk sütun) ve dört incelemesi puanlarını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ff89a-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="ff89a-113">Yabancı anahtar olarak kullanılan kimliği.</span><span class="sxs-lookup"><span data-stu-id="ff89a-113">The ID is used as the foreign key.</span></span>  
  
```csharp  
class Student  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int ID { get; set; }  
    public List<int> ExamScores { get; set; }  
}  
  
class PopulateCollection  
{  
    static void Main()  
    {  
        // These data files are defined in How to: Join Content from   
        // Dissimilar Files (LINQ).  
  
        // Each line of names.csv consists of a last name, a first name, and an  
        // ID number, separated by commas. For example, Omelchenko,Svetlana,111  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
  
        // Each line of scores.csv consists of an ID number and four test   
        // scores, separated by commas. For example, 111, 97, 92, 81, 60  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Merge the data sources using a named type.  
        // var could be used instead of an explicit type. Note the dynamic  
        // creation of a list of ints for the ExamScores member. We skip   
        // the first item in the split string because it is the student ID,   
        // not an exam score.  
        IEnumerable<Student> queryNamesScores =  
            from nameLine in names  
            let splitName = nameLine.Split(',')  
            from scoreLine in scores  
            let splitScoreLine = scoreLine.Split(',')  
            where splitName[2] == splitScoreLine[0]  
            select new Student()  
            {  
                FirstName = splitName[0],  
                LastName = splitName[1],  
                ID = Convert.ToInt32(splitName[2]),  
                ExamScores = (from scoreAsText in splitScoreLine.Skip(1)  
                              select Convert.ToInt32(scoreAsText)).  
                              ToList()  
            };  
  
        // Optional. Store the newly created student objects in memory  
        // for faster access in future queries. This could be useful with  
        // very large data files.  
        List<Student> students = queryNamesScores.ToList();  
  
        // Display each student's name and exam score average.  
        foreach (var student in students)  
        {  
            Console.WriteLine("The average score of {0} {1} is {2}.",  
                student.FirstName, student.LastName,  
                student.ExamScores.Average());  
        }  
  
        //Keep console window open in debug mode  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
}  
/* Output:   
    The average score of Omelchenko Svetlana is 82.5.  
    The average score of O'Donnell Claire is 72.25.  
    The average score of Mortensen Sven is 84.5.  
    The average score of Garcia Cesar is 88.25.  
    The average score of Garcia Debra is 67.  
    The average score of Fakhouri Fadi is 92.25.  
    The average score of Feng Hanying is 88.  
    The average score of Garcia Hugo is 85.75.  
    The average score of Tucker Lance is 81.75.  
    The average score of Adams Terry is 85.25.  
    The average score of Zabokritski Eugene is 83.  
    The average score of Tucker Michael is 92.  
 */  
```  
  
 <span data-ttu-id="ff89a-114">İçinde [seçin](../../../../csharp/language-reference/keywords/select-clause.md) yan tümcesi, nesne Başlatıcı her yeni örneğini oluşturmak için kullanılan `Student` iki kaynaktan verileri kullanarak nesne.</span><span class="sxs-lookup"><span data-stu-id="ff89a-114">In the [select](../../../../csharp/language-reference/keywords/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>  
  
 <span data-ttu-id="ff89a-115">Bir sorgunun sonuçlarını depolamak yoksa anonim türler adlandırılmış türlerinden daha daha kullanışlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="ff89a-115">If you do not have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="ff89a-116">Sorgu sonuçları sorgu yürütüldüğü yöntemi dışında geçirirseniz adlandırılmış türler gereklidir.</span><span class="sxs-lookup"><span data-stu-id="ff89a-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="ff89a-117">Aşağıdaki örnek önceki örnekteki gibi aynı görevi gerçekleştirir, ancak yerine adlandırılmış türler anonim türler kullanır:</span><span class="sxs-lookup"><span data-stu-id="ff89a-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>  
  
```csharp  
// Merge the data sources by using an anonymous type.  
// Note the dynamic creation of a list of ints for the  
// ExamScores member. We skip 1 because the first string  
// in the array is the student ID, not an exam score.  
var queryNamesScores2 =  
    from nameLine in names  
    let splitName = nameLine.Split(',')  
    from scoreLine in scores  
    let splitScoreLine = scoreLine.Split(',')  
    where splitName[2] == splitScoreLine[0]  
    select new  
    {  
        First = splitName[0],  
        Last = splitName[1],  
        ExamScores = (from scoreAsText in splitScoreLine.Skip(1)  
                      select Convert.ToInt32(scoreAsText))  
                      .ToList()  
    };  
  
// Display each student's name and exam score average.  
foreach (var student in queryNamesScores2)  
{  
    Console.WriteLine("The average score of {0} {1} is {2}.",  
        student.First, student.Last, student.ExamScores.Average());  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff89a-118">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="ff89a-118">Compiling the Code</span></span>  
 <span data-ttu-id="ff89a-119">.NET Framework sürüm 3.5 veya daha yüksek System.Core.dll başvuru hedefleyen bir proje oluşturun ve `using` System.Linq ve System.IO ad alanları için yönergeleri.</span><span class="sxs-lookup"><span data-stu-id="ff89a-119">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff89a-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ff89a-120">See Also</span></span>  
 [<span data-ttu-id="ff89a-121">LINQ ve dizeler (C#)</span><span class="sxs-lookup"><span data-stu-id="ff89a-121">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="ff89a-122">Nesne ve koleksiyon başlatıcıları</span><span class="sxs-lookup"><span data-stu-id="ff89a-122">Object and Collection Initializers</span></span>](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [<span data-ttu-id="ff89a-123">Anonim türler</span><span class="sxs-lookup"><span data-stu-id="ff89a-123">Anonymous Types</span></span>](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)