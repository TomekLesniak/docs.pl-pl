---
title: Wywoływania metody lokalnej
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: 25aded1aa961e182e8d2d472fca4c5a84b501af1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166173"
---
# <a name="local-method-calls"></a><span data-ttu-id="9e1ca-102">Wywoływania metody lokalnej</span><span class="sxs-lookup"><span data-stu-id="9e1ca-102">Local Method Calls</span></span>

<span data-ttu-id="9e1ca-103">Wywołanie metody lokalnej to takie, które jest wykonywane w modelu obiektów.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-103">A local method call is one that is executed within the object model.</span></span> <span data-ttu-id="9e1ca-104">Wywołanie metody zdalnej to takie, które [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczy na SQL i przesyła do aparatu bazy danych w celu wykonania.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-104">A remote method call is one that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates to SQL and transmits to the database engine for execution.</span></span> <span data-ttu-id="9e1ca-105">Wywołania metody lokalnej są konieczne, gdy [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nie można przetłumaczyć wywołania na SQL.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-105">Local method calls are needed when [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot translate the call into SQL.</span></span> <span data-ttu-id="9e1ca-106">W przeciwnym razie <xref:System.InvalidOperationException> jest zgłaszany.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-106">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="9e1ca-107">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="9e1ca-107">Example 1</span></span>  

 <span data-ttu-id="9e1ca-108">W poniższym przykładzie `Order` Klasa jest mapowana na tabelę Orders w przykładowej bazie danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-108">In the following example, an `Order` class is mapped to the Orders table in the Northwind sample database.</span></span> <span data-ttu-id="9e1ca-109">Lokalna metoda wystąpienia została dodana do klasy.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-109">A local instance method has been added to the class.</span></span>  
  
 <span data-ttu-id="9e1ca-110">W zapytaniu 1 Konstruktor dla `Order` klasy jest wykonywany lokalnie.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-110">In Query 1, the constructor for the `Order` class is executed locally.</span></span> <span data-ttu-id="9e1ca-111">W zapytaniu 2, jeśli próba [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] przetłumaczenia `LocalInstanceMethod()` na SQL, próba nie powiedzie się i <xref:System.InvalidOperationException> zostanie zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-111">In Query 2, if [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tried to translate `LocalInstanceMethod()`into SQL, the attempt would fail and an <xref:System.InvalidOperationException> exception would be thrown.</span></span> <span data-ttu-id="9e1ca-112">Ale ponieważ [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapewnia obsługę wywołań metod lokalnych, Query2 nie zgłosi wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9e1ca-112">But because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides support for local method calls, Query2 will not throw an exception.</span></span>  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9e1ca-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9e1ca-113">See also</span></span>

- [<span data-ttu-id="9e1ca-114">Informacje uzupełniające</span><span class="sxs-lookup"><span data-stu-id="9e1ca-114">Background Information</span></span>](background-information.md)
