---
title: Formułowanie projekcji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f0bc6dfcff7778ebc7156cbb039e13570c90467b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194404"
---
# <a name="formulate-projections"></a><span data-ttu-id="6df07-102">Formułowanie projekcji</span><span class="sxs-lookup"><span data-stu-id="6df07-102">Formulate Projections</span></span>

<span data-ttu-id="6df07-103">W poniższych przykładach pokazano, jak `select` można łączyć instrukcje w języku C# i `Select` instrukcji w Visual Basic z innymi funkcjami w celu tworzenia zapytań dotyczących projekcji.</span><span class="sxs-lookup"><span data-stu-id="6df07-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6df07-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-104">Example</span></span>  

 <span data-ttu-id="6df07-105">W poniższym przykładzie zastosowano `Select` klauzulę w Visual Basic ( `select` klauzula w języku C#) do zwrócenia sekwencji nazw kontaktów dla `Customers` .</span><span class="sxs-lookup"><span data-stu-id="6df07-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="6df07-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-106">Example</span></span>  

 <span data-ttu-id="6df07-107">W poniższym przykładzie zastosowano `Select` klauzulę w Visual Basic ( `select` klauzula w języku C#) i *Typy anonimowe* , aby zwrócić sekwencję nazw kontaktów i numerów telefonów dla programu `Customers` .</span><span class="sxs-lookup"><span data-stu-id="6df07-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="6df07-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-108">Example</span></span>  

 <span data-ttu-id="6df07-109">W poniższym przykładzie zastosowano `Select` klauzulę w Visual Basic ( `select` klauzula w języku C#) i *Typy anonimowe* , aby zwrócić sekwencję nazw i numerów telefonów dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="6df07-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="6df07-110">`FirstName`Pola i `LastName` są połączone w jedno pole ( `Name` ), a `HomePhone` Nazwa pola jest zmieniana na `Phone` w wyniku sekwencji.</span><span class="sxs-lookup"><span data-stu-id="6df07-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="6df07-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-111">Example</span></span>  

 <span data-ttu-id="6df07-112">W poniższym przykładzie zastosowano `Select` klauzulę w Visual Basic ( `select` klauzula w języku C#) i *Typy anonimowe* , aby zwrócić sekwencję wszystkich `ProductID` i wartości obliczeniowej o nazwie `HalfPrice` .</span><span class="sxs-lookup"><span data-stu-id="6df07-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="6df07-113">Ta wartość jest ustawiana na `UnitPrice` podzieloną przez 2.</span><span class="sxs-lookup"><span data-stu-id="6df07-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="6df07-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-114">Example</span></span>  

 <span data-ttu-id="6df07-115">W poniższym przykładzie jest używana `Select` klauzula w Visual Basic ( `select` klauzula w języku C#) i *Instrukcja warunkowa* zwracająca sekwencję nazw produktów i dostępności produktów.</span><span class="sxs-lookup"><span data-stu-id="6df07-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="6df07-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-116">Example</span></span>  

 <span data-ttu-id="6df07-117">W poniższym przykładzie jest używana `Select` klauzula Visual Basic ( `select` klauzula w języku C#) i *znany typ* (nazwa) do zwrócenia sekwencji nazw pracowników.</span><span class="sxs-lookup"><span data-stu-id="6df07-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="6df07-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-118">Example</span></span>  

 <span data-ttu-id="6df07-119">W poniższym przykładzie przedstawiono użycie `Select` i `Where` w Visual Basic ( `select` i `where` w języku C#) do zwrócenia *filtrowanej sekwencji* nazw kontaktów dla klientów w Londynie.</span><span class="sxs-lookup"><span data-stu-id="6df07-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="6df07-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-120">Example</span></span>  

 <span data-ttu-id="6df07-121">W poniższym przykładzie zastosowano `Select` klauzulę w Visual Basic ( `select` klauzula w języku C#) i *Typy anonimowe* , aby zwrócić *podzbiór* danych dotyczących klientów.</span><span class="sxs-lookup"><span data-stu-id="6df07-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="6df07-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="6df07-122">Example</span></span>  

 <span data-ttu-id="6df07-123">Poniższy przykład używa zagnieżdżonych zapytań, aby zwrócić następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="6df07-123">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="6df07-124">Sekwencja wszystkich zamówień i odpowiadających im elementów typu `OrderID` .</span><span class="sxs-lookup"><span data-stu-id="6df07-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="6df07-125">Podsekwencja elementów w kolejności, w której występuje rabat.</span><span class="sxs-lookup"><span data-stu-id="6df07-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="6df07-126">Ilość pieniędzy zapisana, jeśli koszt wysyłki nie jest uwzględniony.</span><span class="sxs-lookup"><span data-stu-id="6df07-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="6df07-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6df07-127">See also</span></span>

- [<span data-ttu-id="6df07-128">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="6df07-128">Query Examples</span></span>](query-examples.md)
