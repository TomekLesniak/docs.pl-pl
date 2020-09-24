---
title: Nawigowanie w elementach DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 9b7ed4ef1dbe141d8f6a1b6c6b9af2fd89e6c7af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148311"
---
# <a name="navigating-datatables"></a><span data-ttu-id="37c94-102">Nawigowanie w elementach DataTable</span><span class="sxs-lookup"><span data-stu-id="37c94-102">Navigating DataTables</span></span>

<span data-ttu-id="37c94-103"><xref:System.Data.DataTableReader>Uzyskuje zawartość co najmniej jednego <xref:System.Data.DataTable> obiektu w postaci co najmniej jednego zestawu wyników tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="37c94-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="37c94-104">Obiekt <xref:System.Data.DataTableReader> może zawierać wiele zestawów wyników, jeśli jest tworzony przy użyciu <xref:System.Data.DataSet.CreateDataReader%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="37c94-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="37c94-105">Jeśli istnieje więcej niż jeden zestaw wyników, <xref:System.Data.DataTableReader.NextResult%2A> Metoda przesuwa kursor do następnego zestawu wyników.</span><span class="sxs-lookup"><span data-stu-id="37c94-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="37c94-106">Jest to proces tylko do przesyłania dalej.</span><span class="sxs-lookup"><span data-stu-id="37c94-106">This is a forward-only process.</span></span> <span data-ttu-id="37c94-107">Nie można powrócić do poprzedniego zestawu wyników.</span><span class="sxs-lookup"><span data-stu-id="37c94-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37c94-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="37c94-108">Example</span></span>  

 <span data-ttu-id="37c94-109">W poniższym przykładzie `TestConstructor` Metoda tworzy dwa <xref:System.Data.DataTable> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="37c94-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="37c94-110">Aby przedstawić ten Konstruktor dla <xref:System.Data.DataTableReader> klasy, przykład tworzy nowy **DataTableReader** na podstawie tablicy zawierającej dwie **tabele DataTables**i wykonuje prostą operację, drukując zawartość z pierwszych kilku kolumn do okna konsoli.</span><span class="sxs-lookup"><span data-stu-id="37c94-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="37c94-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="37c94-111">See also</span></span>

- [<span data-ttu-id="37c94-112">Elementy DataTableReader</span><span class="sxs-lookup"><span data-stu-id="37c94-112">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="37c94-113">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="37c94-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
