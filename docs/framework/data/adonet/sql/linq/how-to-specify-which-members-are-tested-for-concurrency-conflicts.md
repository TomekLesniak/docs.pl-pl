---
title: 'Instrukcje: Określanie, które elementy członkowskie są sprawdzane pod kątem konfliktów współbieżności'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: e774935827934ae73873247def049b4045535272
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197147"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="b9b28-102">Instrukcje: Określanie, które elementy członkowskie są sprawdzane pod kątem konfliktów współbieżności</span><span class="sxs-lookup"><span data-stu-id="b9b28-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>

<span data-ttu-id="b9b28-103">Zastosuj jeden z trzech typów wyliczeniowych do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> właściwości <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu, aby określić, które składowe mają być uwzględnione w testach aktualizacji w celu wykrywania optymistycznych konfliktów współbieżności.</span><span class="sxs-lookup"><span data-stu-id="b9b28-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="b9b28-104"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>Właściwość (zamapowana w czasie projektowania) jest używana razem z funkcjami współbieżności w czasie wykonywania w systemie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9b28-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="b9b28-105">Aby uzyskać więcej informacji, zobacz [optymistyczne współbieżność: Omówienie](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b9b28-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9b28-106">Pierwotne wartości elementów członkowskich są porównywane z bieżącym stanem bazy danych, o ile nie wyznaczono żadnego elementu członkowskiego `IsVersion=true` .</span><span class="sxs-lookup"><span data-stu-id="b9b28-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="b9b28-107">Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="b9b28-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="b9b28-108">Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> .</span><span class="sxs-lookup"><span data-stu-id="b9b28-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="b9b28-109">Aby zawsze używać tego elementu członkowskiego do wykrywania konfliktów</span><span class="sxs-lookup"><span data-stu-id="b9b28-109">To always use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="b9b28-110">Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="b9b28-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b9b28-111">Ustaw <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> wartość właściwości na `Always` .</span><span class="sxs-lookup"><span data-stu-id="b9b28-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="b9b28-112">Aby nigdy nie używać tego elementu członkowskiego do wykrywania konfliktów</span><span class="sxs-lookup"><span data-stu-id="b9b28-112">To never use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="b9b28-113">Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="b9b28-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b9b28-114">Ustaw <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> wartość właściwości na `Never` .</span><span class="sxs-lookup"><span data-stu-id="b9b28-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="b9b28-115">Aby użyć tego elementu członkowskiego do wykrywania konfliktów tylko wtedy, gdy aplikacja zmieniła wartość elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="b9b28-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1. <span data-ttu-id="b9b28-116">Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="b9b28-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b9b28-117">Ustaw <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> wartość właściwości na `WhenChanged` .</span><span class="sxs-lookup"><span data-stu-id="b9b28-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9b28-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="b9b28-118">Example</span></span>  

 <span data-ttu-id="b9b28-119">W poniższym przykładzie określono, że `HomePage` obiekty nigdy nie powinny być testowane podczas sprawdzania aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="b9b28-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="b9b28-120">Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="b9b28-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b9b28-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b9b28-121">See also</span></span>

- [<span data-ttu-id="b9b28-122">Instrukcje: Zarządzanie konfliktami zmian</span><span class="sxs-lookup"><span data-stu-id="b9b28-122">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="b9b28-123">Tworzenie i przesyłanie zmian danych</span><span class="sxs-lookup"><span data-stu-id="b9b28-123">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
