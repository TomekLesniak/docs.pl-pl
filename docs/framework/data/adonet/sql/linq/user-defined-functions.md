---
title: Funkcje zdefiniowane przez użytkownika
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 061e07ba91a1742c90a594bf42f12e64172b2481
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164119"
---
# <a name="user-defined-functions"></a><span data-ttu-id="6463f-102">Funkcje zdefiniowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="6463f-102">User-Defined Functions</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6463f-103">używa metod w modelu obiektu do reprezentowania funkcji zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6463f-103">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="6463f-104">Należy wyznaczyć metody jako funkcje, stosując <xref:System.Data.Linq.Mapping.FunctionAttribute> atrybut i, w razie potrzeby, <xref:System.Data.Linq.Mapping.ParameterAttribute> atrybut.</span><span class="sxs-lookup"><span data-stu-id="6463f-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="6463f-105">Aby uzyskać więcej informacji, zobacz [model obiektów LINQ to SQL](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="6463f-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="6463f-106">Aby uniknąć <xref:System.InvalidOperationException> , funkcje zdefiniowane przez użytkownika w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] muszą mieć jedną z następujących form:</span><span class="sxs-lookup"><span data-stu-id="6463f-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="6463f-107">Funkcja opakowana jako wywołanie metody ma poprawne atrybuty mapowania.</span><span class="sxs-lookup"><span data-stu-id="6463f-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="6463f-108">Aby uzyskać więcej informacji, zobacz [Mapowanie oparte na atrybutach](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="6463f-108">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="6463f-109">Statyczna metoda SQL specyficzna dla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6463f-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="6463f-110">Funkcja obsługiwana przez metodę .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6463f-110">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="6463f-111">W tematach w tej sekcji pokazano, jak tworzyć i wywoływać te metody w aplikacji, jeśli piszesz kod samodzielnie.</span><span class="sxs-lookup"><span data-stu-id="6463f-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="6463f-112">Deweloperzy korzystający z programu Visual Studio zwykle używają Object Relational Designer do mapowania funkcji zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6463f-112">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6463f-113">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="6463f-113">In This Section</span></span>  

 [<span data-ttu-id="6463f-114">Instrukcje: Używanie funkcji skalarnej zdefiniowanej przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="6463f-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="6463f-115">Opisuje sposób implementowania funkcji zwracającej wartości skalarne.</span><span class="sxs-lookup"><span data-stu-id="6463f-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="6463f-116">Instrukcje: Używanie funkcji tabelarycznej zdefiniowanej przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="6463f-116">How to: Use Table-Valued User-Defined Functions</span></span>](how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="6463f-117">Opisuje sposób implementowania funkcji zwracającej wartości tabeli.</span><span class="sxs-lookup"><span data-stu-id="6463f-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="6463f-118">Instrukcje: Wywoływanie wbudowanych funkcji zdefiniowanych przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="6463f-118">How to: Call User-Defined Functions Inline</span></span>](how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="6463f-119">Opisuje sposób wykonywania wywołań wbudowanych do funkcji i różnic w wykonywaniu, gdy wywołanie jest wykonywane w tekście.</span><span class="sxs-lookup"><span data-stu-id="6463f-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
