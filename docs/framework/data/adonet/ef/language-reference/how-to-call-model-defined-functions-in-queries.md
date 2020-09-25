---
title: 'Instrukcje: Wywoływanie funkcji definiowanych przez model w zapytaniach'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: b142ef820e964eaf5f1afed53a6b12a9344c7dda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189334"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="80571-102">Instrukcje: Wywoływanie funkcji definiowanych przez model w zapytaniach</span><span class="sxs-lookup"><span data-stu-id="80571-102">How to: Call Model-Defined Functions in Queries</span></span>

<span data-ttu-id="80571-103">W tym temacie opisano, jak wywoływać funkcje, które są zdefiniowane w modelu koncepcyjnym z zapytań LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="80571-103">This topic describes how to call functions that are defined in the conceptual model from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="80571-104">Poniższa procedura zawiera konspekt wysokiego poziomu służący do wywoływania funkcji zdefiniowanej przez model z poziomu zapytania LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="80571-104">The procedure below provides a high-level outline for calling a model-defined function from within a LINQ to Entities query.</span></span> <span data-ttu-id="80571-105">Poniższy przykład zawiera bardziej szczegółowe informacje na temat kroków w procedurze.</span><span class="sxs-lookup"><span data-stu-id="80571-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="80571-106">W procedurze przyjęto założenie, że zdefiniowano funkcję w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="80571-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="80571-107">Aby uzyskać więcej informacji, zobacz [How to: define Custom Functions w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="80571-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="80571-108">Aby wywołać funkcję zdefiniowaną w modelu koncepcyjnym</span><span class="sxs-lookup"><span data-stu-id="80571-108">To call a function defined in the conceptual model</span></span>  
  
1. <span data-ttu-id="80571-109">Dodaj do aplikacji metodę środowiska uruchomieniowego języka wspólnego (CLR), która jest mapowana na funkcję zdefiniowaną w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="80571-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="80571-110">Aby zmapować metodę, należy zastosować <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> do metody.</span><span class="sxs-lookup"><span data-stu-id="80571-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="80571-111">Należy zauważyć, <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> że <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> Parametry i atrybutu są nazwą przestrzeni nazw modelu koncepcyjnego i nazwą funkcji w modelu koncepcyjnym odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="80571-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="80571-112">Rozpoznawanie nazw funkcji dla LINQ jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="80571-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2. <span data-ttu-id="80571-113">Wywołaj funkcję w kwerendzie LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="80571-113">Call the function in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80571-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="80571-114">Example</span></span>  

 <span data-ttu-id="80571-115">Poniższy przykład ilustruje sposób wywołania funkcji zdefiniowanej w modelu koncepcyjnym z poziomu zapytania LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="80571-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a LINQ to Entities query.</span></span> <span data-ttu-id="80571-116">W przykładzie zastosowano model szkoły.</span><span class="sxs-lookup"><span data-stu-id="80571-116">The example uses the School model.</span></span> <span data-ttu-id="80571-117">Aby uzyskać informacje o modelu szkoły, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) i [generowanie pliku szkoły. edmx](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="80571-117">For information about the School model, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>  
  
 <span data-ttu-id="80571-118">Poniższa funkcja modelu koncepcyjnego zwraca liczbę lat od momentu zatrudnienia instruktora.</span><span class="sxs-lookup"><span data-stu-id="80571-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="80571-119">Informacje o dodawaniu funkcji do modelu koncepcyjnego znajdują się [w temacie How to: define Custom Functions w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="80571-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="80571-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="80571-120">Example</span></span>  

 <span data-ttu-id="80571-121">Następnie Dodaj następującą metodę do aplikacji i użyj metody, <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> Aby zamapować ją na funkcję modelu koncepcyjnego:</span><span class="sxs-lookup"><span data-stu-id="80571-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="80571-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="80571-122">Example</span></span>  

 <span data-ttu-id="80571-123">Teraz można wywołać funkcję modelu koncepcyjnego z poziomu zapytania LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="80571-123">Now you can call the conceptual model function from within a LINQ to Entities query.</span></span> <span data-ttu-id="80571-124">Poniższy kod wywołuje metodę w celu wyświetlenia wszystkich instruktorów, którzy zostali zatrudnieni ponad dziesięć lat temu:</span><span class="sxs-lookup"><span data-stu-id="80571-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="80571-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="80571-125">See also</span></span>

- <span data-ttu-id="80571-126">[Plik. edmx — Omówienie](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="80571-126">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="80571-127">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="80571-127">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="80571-128">Wywoływanie funkcji w zapytaniach składnika LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="80571-128">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="80571-129">Instrukcje: Wywoływanie funkcji definiowanych przez model jako metod obiektu</span><span class="sxs-lookup"><span data-stu-id="80571-129">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)
