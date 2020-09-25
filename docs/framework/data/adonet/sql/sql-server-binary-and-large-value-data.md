---
title: Dane binarne i dużej wartości w programie SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183042"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="75395-102">Dane binarne i dużej wartości w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="75395-102">SQL Server Binary and Large-Value Data</span></span>

<span data-ttu-id="75395-103">SQL Server zawiera `max` specyfikator, który rozszerza pojemność magazynu dla `varchar` , `nvarchar` i `varbinary` typów danych.</span><span class="sxs-lookup"><span data-stu-id="75395-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="75395-104">`varchar(max)`, `nvarchar(max)` i `varbinary(max)` są nazywane zbiorczo *typami danych o dużej wartości*.</span><span class="sxs-lookup"><span data-stu-id="75395-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="75395-105">Możesz użyć typów danych o dużej wartości do przechowywania maksymalnie 2 ^ 31-1 bajtów danych.</span><span class="sxs-lookup"><span data-stu-id="75395-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="75395-106">SQL Server 2008 wprowadza atrybut FILESTREAM, który nie jest typem danych, ale raczej atrybut, który można zdefiniować w kolumnie, umożliwiając przechowywanie danych dużych wartości w systemie plików, a nie w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="75395-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75395-107">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="75395-107">In This Section</span></span>  

 [<span data-ttu-id="75395-108">Modyfikowanie dużej wartości (wartość maksymalna) danych w ADO.NET</span><span class="sxs-lookup"><span data-stu-id="75395-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="75395-109">Opisuje sposób pracy z typami danych o dużej wartości.</span><span class="sxs-lookup"><span data-stu-id="75395-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="75395-110">Dane FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="75395-110">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="75395-111">Opisuje sposób pracy z danymi o dużej wartości przechowywanych w SQL Server 2008 przy użyciu atrybutu FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="75395-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75395-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="75395-112">See also</span></span>

- [<span data-ttu-id="75395-113">Typy danych programu SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="75395-113">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="75395-114">Operacje danych serwera SQL w ADO.NET</span><span class="sxs-lookup"><span data-stu-id="75395-114">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="75395-115">Pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="75395-115">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="75395-116">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="75395-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
