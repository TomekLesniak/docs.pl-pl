---
title: Modyfikowanie elementów DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 8e3a3f92fe8ecc94a041fbcb1540bae18a41dbef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203686"
---
# <a name="modifying-dataviews"></a><span data-ttu-id="b6ff8-102">Modyfikowanie elementów DataView</span><span class="sxs-lookup"><span data-stu-id="b6ff8-102">Modifying DataViews</span></span>

<span data-ttu-id="b6ff8-103">Można użyć <xref:System.Data.DataView> do dodawania, usuwania lub modyfikowania wierszy danych w tabeli źródłowej.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="b6ff8-104">Możliwość używania elementu **DataView** do modyfikowania danych w źródłowej tabeli jest kontrolowana przez ustawienie jednej z trzech właściwości logicznych elementu **DataView**.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="b6ff8-105">Te właściwości to <xref:System.Data.DataView.AllowNew%2A> , <xref:System.Data.DataView.AllowEdit%2A> i <xref:System.Data.DataView.AllowDelete%2A> .</span><span class="sxs-lookup"><span data-stu-id="b6ff8-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="b6ff8-106">Domyślnie ustawiono **wartość true** .</span><span class="sxs-lookup"><span data-stu-id="b6ff8-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="b6ff8-107">Jeśli **AllowNew** ma **wartość true**, można użyć <xref:System.Data.DataView.AddNew%2A> metody **widoku** danych, aby utworzyć nowy <xref:System.Data.DataRowView> .</span><span class="sxs-lookup"><span data-stu-id="b6ff8-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="b6ff8-108">Należy zauważyć, że nowy wiersz nie jest faktycznie dodawany do elementu bazowego <xref:System.Data.DataTable> do momentu <xref:System.Data.DataRowView.EndEdit%2A> wywołania metody **DataRowView** .</span><span class="sxs-lookup"><span data-stu-id="b6ff8-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="b6ff8-109">Jeśli <xref:System.Data.DataRowView.CancelEdit%2A> wywoływana jest metoda **DataRowView** , nowy wiersz jest odrzucany.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="b6ff8-110">Należy zauważyć, że można edytować tylko jeden **DataRowView** w danym momencie.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="b6ff8-111">W przypadku wywołania metody **AddNew** lub **elementu BeginEdit** **DataRowView** , gdy istnieje oczekujący wiersz, **EndEdit** jest wywoływana niejawnie w oczekującym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="b6ff8-112">Gdy **EndEdit** jest wywoływana, zmiany są stosowane do bazowego **elementu DataTable** i później mogą być zatwierdzane lub odrzucane przy użyciu metod **AcceptChanges** lub **RejectChanges** obiektu **DataTable**, **DataSet**lub **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="b6ff8-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="b6ff8-113">Jeśli **AllowNew** ma **wartość false**, wyjątek jest zgłaszany w przypadku wywołania metody **AddNew** elementu **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="b6ff8-114">Jeśli **AllowEdit** ma **wartość true**, można zmodyfikować zawartość obiektu **DataRow** za pośrednictwem **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="b6ff8-115">Można potwierdzić zmiany w wierszu źródłowym przy użyciu **DataRowView. EndEdit** lub odrzucić zmiany przy użyciu **DataRowView. CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="b6ff8-116">Należy zauważyć, że w danym momencie można edytować tylko jeden wiersz.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="b6ff8-117">W przypadku wywołania metody **AddNew** lub **elementu BeginEdit** **DataRowView** , gdy istnieje oczekujący wiersz, **EndEdit** jest wywoływana niejawnie w oczekującym wierszu.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="b6ff8-118">Gdy **EndEdit** jest wywoływana, proponowane zmiany są umieszczane w **bieżącej** wersji wiersza bazowego elementu **DataRow** i mogą być później zatwierdzane lub odrzucane przy użyciu metod **AcceptChanges** lub **RejectChanges** obiektu **DataTable**, **DataSet**lub **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="b6ff8-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="b6ff8-119">Jeśli **AllowEdit** ma **wartość false**, wyjątek jest zgłaszany w przypadku próby zmodyfikowania wartości w **widoku**danych.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="b6ff8-120">Podczas edytowania istniejącej **DataRowView** zdarzenia powiązanej **tabeli DataTable** będą nadal zgłaszane z proponowanymi zmianami.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="b6ff8-121">Należy pamiętać, że jeśli wywołasz **EndEdit** lub **CancelEdit** na bazowym elemencie **DataRow**, oczekujące zmiany zostaną zastosowane lub anulowane niezależnie od tego, czy **EndEdit** lub **CancelEdit** są wywoływane na **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="b6ff8-122">Jeśli **AllowDelete** ma **wartość true**, można usunąć wiersze z **widoku** danych za pomocą metody **delete** obiektu **DataView** lub **DataRowView** , a wiersze są usuwane z bazowego **elementu DataTable**.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="b6ff8-123">Można później zatwierdzać lub odrzucać usunięcia przy użyciu metody **AcceptChanges** lub **RejectChanges** .</span><span class="sxs-lookup"><span data-stu-id="b6ff8-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="b6ff8-124">Jeśli **AllowDelete** ma **wartość false**, wyjątek jest zgłaszany w przypadku wywołania metody **delete** elementu **DataView** lub **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="b6ff8-125">Poniższy przykład kodu wyłącza używanie elementu **DataView** do usuwania wierszy i dodaje nowy wiersz do źródłowej tabeli przy użyciu **widoku**danych.</span><span class="sxs-lookup"><span data-stu-id="b6ff8-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6ff8-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b6ff8-126">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="b6ff8-127">Elementy DataView</span><span class="sxs-lookup"><span data-stu-id="b6ff8-127">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="b6ff8-128">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b6ff8-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
