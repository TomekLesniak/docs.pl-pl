---
title: Procedury składowane
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 57420d95ec27af3b572940202fb6bc288c6888da
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203517"
---
# <a name="stored-procedures"></a><span data-ttu-id="3711a-102">Procedury składowane</span><span class="sxs-lookup"><span data-stu-id="3711a-102">Stored Procedures</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3711a-103">używa metod w modelu obiektu do reprezentowania procedur składowanych w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="3711a-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="3711a-104">Należy wyznaczyć metody jako procedury składowane, stosując <xref:System.Data.Linq.Mapping.FunctionAttribute> atrybut i, w razie potrzeby, <xref:System.Data.Linq.Mapping.ParameterAttribute> atrybut.</span><span class="sxs-lookup"><span data-stu-id="3711a-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="3711a-105">Aby uzyskać więcej informacji, zobacz [model obiektów LINQ to SQL](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="3711a-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="3711a-106">Deweloperzy korzystający z programu Visual Studio zwykle używają Object Relational Designer, aby mapować procedury składowane.</span><span class="sxs-lookup"><span data-stu-id="3711a-106">Developers using Visual Studio would typically use the Object Relational Designer to map stored procedures.</span></span> <span data-ttu-id="3711a-107">W tematach w tej sekcji pokazano, jak tworzyć i wywoływać te metody w aplikacji, jeśli piszesz kod samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="3711a-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3711a-108">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="3711a-108">In This Section</span></span>  

 [<span data-ttu-id="3711a-109">Instrukcje: Zwracane zestawy wierszy</span><span class="sxs-lookup"><span data-stu-id="3711a-109">How to: Return Rowsets</span></span>](how-to-return-rowsets.md)  
 <span data-ttu-id="3711a-110">Opisuje sposób zwracania wierszy danych i pokazuje, jak używać parametru wejściowego.</span><span class="sxs-lookup"><span data-stu-id="3711a-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="3711a-111">Instrukcje: Używanie procedur składowanych, które przyjmują parametry</span><span class="sxs-lookup"><span data-stu-id="3711a-111">How to: Use Stored Procedures that Take Parameters</span></span>](how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="3711a-112">Opisuje sposób używania parametrów wejściowych i wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="3711a-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="3711a-113">Instrukcje: Używanie procedur składowanych zamapowanych na wiele kształtów wyników</span><span class="sxs-lookup"><span data-stu-id="3711a-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="3711a-114">Opisuje, jak zapewnić zwroty wielu kształtów w tej samej procedurze składowanej.</span><span class="sxs-lookup"><span data-stu-id="3711a-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="3711a-115">Instrukcje: Używanie procedur składowanych zamapowanych na sekwencyjne kształty wyników</span><span class="sxs-lookup"><span data-stu-id="3711a-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="3711a-116">Opisuje, w jaki sposób zapewnić wiele kształtów, w których jest znana sekwencja powrotu.</span><span class="sxs-lookup"><span data-stu-id="3711a-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="3711a-117">Dostosowywanie operacji przy użyciu procedur składowanych</span><span class="sxs-lookup"><span data-stu-id="3711a-117">Customizing Operations By Using Stored Procedures</span></span>](customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="3711a-118">Opisuje, jak używać procedur składowanych do implementowania operacji INSERT, Update i DELETE.</span><span class="sxs-lookup"><span data-stu-id="3711a-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="3711a-119">Dostosowywanie operacji przy użyciu wyłącznie procedur składowanych</span><span class="sxs-lookup"><span data-stu-id="3711a-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="3711a-120">Opisuje, jak używać niczego, ale procedury składowane do implementowania operacji INSERT, Update i DELETE.</span><span class="sxs-lookup"><span data-stu-id="3711a-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3711a-121">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="3711a-121">Related Sections</span></span>  

 [<span data-ttu-id="3711a-122">Przewodnik programowania</span><span class="sxs-lookup"><span data-stu-id="3711a-122">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="3711a-123">Zawiera informacje o sposobach tworzenia i używania [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelu obiektów.</span><span class="sxs-lookup"><span data-stu-id="3711a-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="3711a-124">Przewodnik: Używanie tylko procedur składowanych (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3711a-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="3711a-125">Obejmuje procedury, które ilustrują sposób korzystania z procedur składowanych w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3711a-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="3711a-126">Przewodnik: Używanie tylko procedur składowanych (C#)</span><span class="sxs-lookup"><span data-stu-id="3711a-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="3711a-127">Obejmuje procedury, które ilustrują sposób korzystania z procedur składowanych w języku C#.</span><span class="sxs-lookup"><span data-stu-id="3711a-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
