---
title: 'Instrukcje: Wywoływanie funkcji definiowanych przez model jako metod obiektu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
ms.openlocfilehash: 5e5ae2fd838a34d7f665b23a14db2a599367e801
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197797"
---
# <a name="how-to-call-model-defined-functions-as-object-methods"></a><span data-ttu-id="ad952-102">Instrukcje: Wywoływanie funkcji definiowanych przez model jako metod obiektu</span><span class="sxs-lookup"><span data-stu-id="ad952-102">How to: Call Model-Defined Functions as Object Methods</span></span>

<span data-ttu-id="ad952-103">W tym temacie opisano sposób wywoływania funkcji zdefiniowanej przez model jako metody na <xref:System.Data.Objects.ObjectContext> obiekcie lub jako metody statycznej klasy niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="ad952-103">This topic describes how to call a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object or as a static method on a custom class.</span></span> <span data-ttu-id="ad952-104">*Funkcja zdefiniowana przez model* jest funkcją zdefiniowaną w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="ad952-104">A *model-defined function* is a function that is defined in the conceptual model.</span></span> <span data-ttu-id="ad952-105">Procedury w temacie opisują sposób wywołania tych funkcji bezpośrednio zamiast wywoływania ich z LINQ to Entities zapytań.</span><span class="sxs-lookup"><span data-stu-id="ad952-105">The procedures in the topic describe how to call these functions directly instead of calling them from LINQ to Entities queries.</span></span> <span data-ttu-id="ad952-106">Aby uzyskać informacje o wywoływaniu funkcji zdefiniowanych przez model w zapytaniach LINQ to Entities, zobacz [How to: Call defined model Functions in zapytania](how-to-call-model-defined-functions-in-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ad952-106">For information about calling model-defined functions in LINQ to Entities queries, see [How to: Call Model-Defined Functions in Queries](how-to-call-model-defined-functions-in-queries.md).</span></span>  
  
 <span data-ttu-id="ad952-107">Niezależnie od tego, czy wywoływana jest funkcja zdefiniowana przez model jako <xref:System.Data.Objects.ObjectContext> Metoda, czy jako metoda statyczna klasy niestandardowej, należy najpierw zmapować metodę do funkcji zdefiniowanej przez model przy użyciu <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> .</span><span class="sxs-lookup"><span data-stu-id="ad952-107">Whether you call a model-defined function as an <xref:System.Data.Objects.ObjectContext> method or as a static method on a custom class, you must first map the method to the model-defined function with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="ad952-108">Jednak podczas definiowania metody <xref:System.Data.Objects.ObjectContext> klasy należy użyć <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> właściwości, aby uwidocznić dostawcę LINQ, podczas gdy definiujemy metodę statyczną dla klasy niestandardowej, należy użyć <xref:System.Linq.IQueryable.Provider%2A> właściwości, aby uwidocznić dostawcę LINQ.</span><span class="sxs-lookup"><span data-stu-id="ad952-108">However, when you define a method on the <xref:System.Data.Objects.ObjectContext> class, you must use the <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> property to expose the LINQ provider, whereas when you define a static method on a custom class, you must use the <xref:System.Linq.IQueryable.Provider%2A> property to expose the LINQ provider.</span></span> <span data-ttu-id="ad952-109">Aby uzyskać więcej informacji, zobacz przykłady, które postępują zgodnie z poniższymi procedurami.</span><span class="sxs-lookup"><span data-stu-id="ad952-109">For more information, see the examples that follow the procedures below.</span></span>  
  
 <span data-ttu-id="ad952-110">Poniższe procedury zapewniają konspekt wysokiego poziomu na potrzeby wywoływania funkcji zdefiniowanej przez model jako metody na <xref:System.Data.Objects.ObjectContext> obiekcie oraz jako metody statycznej klasy niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="ad952-110">The procedures below provide high-level outlines for calling a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object and as a static method on a custom class.</span></span> <span data-ttu-id="ad952-111">Poniższe przykłady zawierają więcej szczegółów na temat kroków w procedurach.</span><span class="sxs-lookup"><span data-stu-id="ad952-111">The examples that follow provide more detail about the steps in the procedures.</span></span> <span data-ttu-id="ad952-112">W procedurach przyjęto założenie, że zdefiniowano funkcję w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="ad952-112">The procedures assume that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="ad952-113">Aby uzyskać więcej informacji, zobacz [How to: define Custom Functions w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ad952-113">For more information, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-model-defined-function-as-a-method-on-an-objectcontext-object"></a><span data-ttu-id="ad952-114">Wywoływanie funkcji zdefiniowanej przez model jako metody obiektu ObjectContext</span><span class="sxs-lookup"><span data-stu-id="ad952-114">To call a model-defined function as a method on an ObjectContext object</span></span>  
  
1. <span data-ttu-id="ad952-115">Dodaj plik źródłowy, aby zwiększyć klasę częściową pochodną <xref:System.Data.Objects.ObjectContext> klasy, automatycznie wygenerowaną przez narzędzia Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ad952-115">Add a source file to extend the partial class derived from the <xref:System.Data.Objects.ObjectContext> class, auto-generated by the Entity Framework tools.</span></span> <span data-ttu-id="ad952-116">Zdefiniowanie klasy zastępczej środowiska CLR w osobnym pliku źródłowym uniemożliwi utratę zmian po ponownym wygenerowanym pliku.</span><span class="sxs-lookup"><span data-stu-id="ad952-116">Defining the CLR stub in a separate source file will prevent the changes from being lost when the file is regenerated.</span></span>  
  
2. <span data-ttu-id="ad952-117">Dodaj do klasy metodę środowiska uruchomieniowego języka wspólnego (CLR) <xref:System.Data.Objects.ObjectContext> , która wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="ad952-117">Add a common language runtime (CLR) method to your <xref:System.Data.Objects.ObjectContext> class that does the following:</span></span>  
  
    - <span data-ttu-id="ad952-118">Mapuje do funkcji zdefiniowanej w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="ad952-118">Maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="ad952-119">Aby zmapować metodę, należy zastosować <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> do metody.</span><span class="sxs-lookup"><span data-stu-id="ad952-119">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="ad952-120">Należy zauważyć, <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> że <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> Parametry i atrybutu są nazwą przestrzeni nazw modelu koncepcyjnego i nazwą funkcji w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="ad952-120">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model, respectively.</span></span> <span data-ttu-id="ad952-121">Rozpoznawanie nazw funkcji dla LINQ jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="ad952-121">Function name resolution for LINQ is case sensitive.</span></span>  
  
    - <span data-ttu-id="ad952-122">Zwraca wyniki <xref:System.Linq.IQueryProvider.Execute%2A> metody, która jest zwracana przez <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="ad952-122">Returns the results of the <xref:System.Linq.IQueryProvider.Execute%2A> method that is returned by the <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> property.</span></span>  
  
3. <span data-ttu-id="ad952-123">Wywołaj metodę jako element członkowski w wystąpieniu <xref:System.Data.Objects.ObjectContext> klasy.</span><span class="sxs-lookup"><span data-stu-id="ad952-123">Call the method as a member on an instance of the <xref:System.Data.Objects.ObjectContext> class.</span></span>  
  
### <a name="to-call-a-model-defined-function-as-static-method-on-a-custom-class"></a><span data-ttu-id="ad952-124">Wywoływanie funkcji zdefiniowanej przez model jako metody statycznej w klasie niestandardowej</span><span class="sxs-lookup"><span data-stu-id="ad952-124">To call a model-defined function as static method on a custom class</span></span>  
  
1. <span data-ttu-id="ad952-125">Dodaj klasę do aplikacji za pomocą metody statycznej, która wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="ad952-125">Add a class to your application with a static method that does the following:</span></span>  
  
    - <span data-ttu-id="ad952-126">Mapuje do funkcji zdefiniowanej w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="ad952-126">Maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="ad952-127">Aby zmapować metodę, należy zastosować <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> do metody.</span><span class="sxs-lookup"><span data-stu-id="ad952-127">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="ad952-128">Należy zauważyć, <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> że <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> Parametry i atrybutu są nazwą przestrzeni nazw modelu koncepcyjnego i nazwą funkcji w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="ad952-128">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model, respectively.</span></span>  
  
    - <span data-ttu-id="ad952-129">Akceptuje <xref:System.Linq.IQueryable> argument.</span><span class="sxs-lookup"><span data-stu-id="ad952-129">Accepts an <xref:System.Linq.IQueryable> argument.</span></span>  
  
    - <span data-ttu-id="ad952-130">Zwraca wyniki <xref:System.Linq.IQueryProvider.Execute%2A> metody, która jest zwracana przez <xref:System.Linq.IQueryable.Provider%2A> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="ad952-130">Returns the results of the <xref:System.Linq.IQueryProvider.Execute%2A> method that is returned by the <xref:System.Linq.IQueryable.Provider%2A> property.</span></span>  
  
2. <span data-ttu-id="ad952-131">Wywołaj metodę jako składową metodę statyczną w klasie niestandardowej</span><span class="sxs-lookup"><span data-stu-id="ad952-131">Call the method as a member a static method on the custom class</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad952-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-132">Example</span></span>  

 <span data-ttu-id="ad952-133">**Wywoływanie funkcji zdefiniowanej przez model jako metody dla obiektu ObjectContext**</span><span class="sxs-lookup"><span data-stu-id="ad952-133">**Calling a Model-Defined Function as a Method on an ObjectContext Object**</span></span>  
  
 <span data-ttu-id="ad952-134">Poniższy przykład ilustruje sposób wywołania funkcji zdefiniowanej przez model jako metody w <xref:System.Data.Objects.ObjectContext> obiekcie.</span><span class="sxs-lookup"><span data-stu-id="ad952-134">The following example demonstrates how to call a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object.</span></span> <span data-ttu-id="ad952-135">W przykładzie zastosowano [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="ad952-135">The example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
 <span data-ttu-id="ad952-136">Rozważmy poniższe funkcje modelu koncepcyjnego, które zwracają przychód produktu dla określonego produktu.</span><span class="sxs-lookup"><span data-stu-id="ad952-136">Consider the conceptual model function below that returns product revenue for a specified product.</span></span> <span data-ttu-id="ad952-137">(Aby uzyskać informacje na temat dodawania funkcji do modelu koncepcyjnego, zobacz [How to: define Custom Functions w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="ad952-137">(For information about adding the function to your conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  

## <a name="example"></a><span data-ttu-id="ad952-138">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-138">Example</span></span>  

 <span data-ttu-id="ad952-139">Poniższy kod dodaje metodę do `AdventureWorksEntities` klasy, która jest mapowana na powyższą funkcję modelu koncepcyjnego.</span><span class="sxs-lookup"><span data-stu-id="ad952-139">The following code adds a method to the `AdventureWorksEntities` class that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="ad952-140">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-140">Example</span></span>  

 <span data-ttu-id="ad952-141">Poniższy kod wywołuje metodę powyżej, aby wyświetlić przychód produktu dla określonego produktu:</span><span class="sxs-lookup"><span data-stu-id="ad952-141">The following code calls the method above to display the product revenue for a specified product:</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="ad952-142">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-142">Example</span></span>  

 <span data-ttu-id="ad952-143">Poniższy przykład ilustruje sposób wywoływania funkcji zdefiniowanej przez model, która zwraca kolekcję (jako <xref:System.Linq.IQueryable%601> obiekt).</span><span class="sxs-lookup"><span data-stu-id="ad952-143">The following example demonstrates how to call a model-defined function that returns a collection (as an <xref:System.Linq.IQueryable%601> object).</span></span> <span data-ttu-id="ad952-144">Rozważmy poniższe funkcje modelu koncepcyjnego, które zwracają wszystkie `SalesOrderDetails` dla danego identyfikatora produktu.</span><span class="sxs-lookup"><span data-stu-id="ad952-144">Consider the conceptual model function below that returns all the `SalesOrderDetails` for a given product ID.</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## <a name="example"></a><span data-ttu-id="ad952-145">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-145">Example</span></span>  

 <span data-ttu-id="ad952-146">Poniższy kod dodaje metodę do `AdventureWorksEntities` klasy, która jest mapowana na powyższą funkcję modelu koncepcyjnego.</span><span class="sxs-lookup"><span data-stu-id="ad952-146">The following code adds a method to the `AdventureWorksEntities` class that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="ad952-147">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-147">Example</span></span>  

 <span data-ttu-id="ad952-148">Poniższy kod wywołuje metodę.</span><span class="sxs-lookup"><span data-stu-id="ad952-148">The following code calls the method.</span></span> <span data-ttu-id="ad952-149">Zwróć uwagę, że zwrócone <xref:System.Linq.IQueryable%601> zapytanie jest bardziej udoskonalane w celu zwrócenia sum wierszy dla każdego z nich `SalesOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="ad952-149">Note that the returned <xref:System.Linq.IQueryable%601> query is further refined to return line totals for each `SalesOrderDetail`.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="ad952-150">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-150">Example</span></span>  

 <span data-ttu-id="ad952-151">**Wywoływanie funkcji zdefiniowanej przez model jako metody statycznej w klasie niestandardowej**</span><span class="sxs-lookup"><span data-stu-id="ad952-151">**Calling a Model-Defined Function as a Static Method on a Custom Class**</span></span>  
  
 <span data-ttu-id="ad952-152">W następnym przykładzie pokazano sposób wywołania funkcji zdefiniowanej przez model jako metody statycznej klasy niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="ad952-152">The next example demonstrates how to call a model-defined function as a static method on a custom class.</span></span> <span data-ttu-id="ad952-153">W przykładzie zastosowano [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="ad952-153">The example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad952-154">W przypadku wywołania funkcji zdefiniowanej przez model jako metody statycznej klasy niestandardowej funkcja zdefiniowana przez model musi akceptować kolekcję i zwracać agregację wartości w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ad952-154">When you call a model-defined function as a static method on a custom class, the model-defined function must accept a collection and return an aggregation of values in the collection.</span></span>  
  
 <span data-ttu-id="ad952-155">Rozważmy poniższe funkcje modelu koncepcyjnego zwracające przychód produktu dla kolekcji SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="ad952-155">Consider the conceptual model function below that returns product revenue for a SalesOrderDetail collection.</span></span> <span data-ttu-id="ad952-156">(Aby uzyskać informacje na temat dodawania funkcji do modelu koncepcyjnego, zobacz [How to: define Custom Functions w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="ad952-156">(For information about adding the function to your conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).).</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="ad952-157">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-157">Example</span></span>  

 <span data-ttu-id="ad952-158">Poniższy kod dodaje klasę do aplikacji, która zawiera statyczną metodę, która jest mapowana na powyższą funkcję modelu koncepcyjnego.</span><span class="sxs-lookup"><span data-stu-id="ad952-158">The following code adds a class to your application that contains a static method that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ad952-159">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad952-159">Example</span></span>  

 <span data-ttu-id="ad952-160">Poniższy kod wywołuje metodę powyżej, aby wyświetlić przychód produktu dla kolekcji SalesOrderDetail:</span><span class="sxs-lookup"><span data-stu-id="ad952-160">The following code calls the method above to display the product revenue for a SalesOrderDetail collection:</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ad952-161">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ad952-161">See also</span></span>

- <span data-ttu-id="ad952-162">[Plik. edmx — Omówienie](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ad952-162">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="ad952-163">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ad952-163">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="ad952-164">Wywoływanie funkcji w zapytaniach składnika LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ad952-164">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
