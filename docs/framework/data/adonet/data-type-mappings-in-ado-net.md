---
title: Mapowanie typu danych
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 52e64714a17448cd94723bdc216d8ea069fc5eef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177751"
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="1b9fa-102">Mapowanie typu danych w ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b9fa-102">Data Type Mappings in ADO.NET</span></span>

<span data-ttu-id="1b9fa-103">.NET Framework opiera się na wspólnym typie systemu, który definiuje, w jaki sposób typy są zadeklarowane, używane i zarządzane w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="1b9fa-104">Składa się z obu typów wartości i typów referencyjnych, które pochodzą z <xref:System.Object> typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="1b9fa-105">Podczas pracy ze źródłem danych typ danych jest wnioskowany od dostawcy danych, jeśli nie został jawnie określony.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="1b9fa-106">Na przykład <xref:System.Data.DataSet> obiekt jest niezależny od określonego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="1b9fa-107">Dane z programu `DataSet` są pobierane ze źródła danych, a zmiany są utrwalane w źródle danych przy użyciu `DataAdapter` .</span><span class="sxs-lookup"><span data-stu-id="1b9fa-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="1b9fa-108">Oznacza to, że `DataAdapter` w przypadku wypełniania <xref:System.Data.DataTable> wartości z `DataSet` wartościami ze źródła danych, typy danych w kolumnach `DataTable` są .NET Framework typy, a nie typy specyficzne dla .NET Framework dostawcy danych, który jest używany do nawiązywania połączenia ze źródłem danych.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are .NET Framework types, instead of types specific to the .NET Framework data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="1b9fa-109">Podobnie, gdy `DataReader` zwraca wartość ze źródła danych, wynikowa wartość jest przechowywana w zmiennej lokalnej, która ma typ .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a .NET Framework type.</span></span> <span data-ttu-id="1b9fa-110">Dla `Fill` operacji `DataAdapter` i `Get` metod `DataReader` , typ .NET Framework jest wywnioskowany na podstawie wartości zwróconej przez dostawcę danych .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the value returned from the .NET Framework data provider.</span></span>  
  
 <span data-ttu-id="1b9fa-111">Zamiast polegać na wywnioskowanym typie danych, można użyć typów metod dostępu typu w `DataReader` przypadku, gdy wiadomo, że określony typ zwracanej wartości.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="1b9fa-112">Wpisywane metody dostępu zapewniają lepszą wydajność, zwracając wartość jako określony typ .NET Framework, co eliminuje konieczność stosowania dodatkowej konwersji typu.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-112">Typed accessor methods give you better performance by returning a value as a specific .NET Framework type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b9fa-113">Wartości null dla typów danych .NET Framework dostawcy danych są reprezentowane przez `DBNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="1b9fa-113">Null values for .NET Framework data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b9fa-114">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="1b9fa-114">In This Section</span></span>  

 [<span data-ttu-id="1b9fa-115">Mapowanie typu danych serwera SQL</span><span class="sxs-lookup"><span data-stu-id="1b9fa-115">SQL Server Data Type Mappings</span></span>](sql-server-data-type-mappings.md)  
 <span data-ttu-id="1b9fa-116">Wyświetla listę odroczonych mapowań typu danych i metod dostępu do danych dla programu <xref:System.Data.SqlClient> .</span><span class="sxs-lookup"><span data-stu-id="1b9fa-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="1b9fa-117">Mapowanie typu danych OLE DB</span><span class="sxs-lookup"><span data-stu-id="1b9fa-117">OLE DB Data Type Mappings</span></span>](ole-db-data-type-mappings.md)  
 <span data-ttu-id="1b9fa-118">Wyświetla listę odroczonych mapowań typu danych i metod dostępu do danych dla programu <xref:System.Data.OleDb> .</span><span class="sxs-lookup"><span data-stu-id="1b9fa-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="1b9fa-119">Mapowanie typu danych ODBC</span><span class="sxs-lookup"><span data-stu-id="1b9fa-119">ODBC Data Type Mappings</span></span>](odbc-data-type-mappings.md)  
 <span data-ttu-id="1b9fa-120">Wyświetla listę odroczonych mapowań typu danych i metod dostępu do danych dla programu <xref:System.Data.Odbc> .</span><span class="sxs-lookup"><span data-stu-id="1b9fa-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="1b9fa-121">Mapowanie typu danych Oracle</span><span class="sxs-lookup"><span data-stu-id="1b9fa-121">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="1b9fa-122">Wyświetla listę odroczonych mapowań typu danych i metod dostępu do danych dla programu <xref:System.Data.OracleClient> .</span><span class="sxs-lookup"><span data-stu-id="1b9fa-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="1b9fa-123">Liczby zmiennoprzecinkowe</span><span class="sxs-lookup"><span data-stu-id="1b9fa-123">Floating-Point Numbers</span></span>](floating-point-numbers.md)  
 <span data-ttu-id="1b9fa-124">Opisuje problemy, które deweloperzy często napotykają podczas pracy z liczbami zmiennoprzecinkowymi.</span><span class="sxs-lookup"><span data-stu-id="1b9fa-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9fa-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1b9fa-125">See also</span></span>

- [<span data-ttu-id="1b9fa-126">Typy danych programu SQL Server i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b9fa-126">SQL Server Data Types and ADO.NET</span></span>](./sql/sql-server-data-types.md)
- [<span data-ttu-id="1b9fa-127">Konfigurowanie parametrów i typów danych parametrów</span><span class="sxs-lookup"><span data-stu-id="1b9fa-127">Configuring Parameters and Parameter Data Types</span></span>](configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="1b9fa-128">Pobieranie informacji o schemacie bazy danych</span><span class="sxs-lookup"><span data-stu-id="1b9fa-128">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="1b9fa-129">Wspólny system typów</span><span class="sxs-lookup"><span data-stu-id="1b9fa-129">Common Type System</span></span>](../../../standard/base-types/common-type-system.md)
- <span data-ttu-id="1b9fa-130">[Konwertowanie typów](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1b9fa-130">[Converting Types](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))</span></span>
- [<span data-ttu-id="1b9fa-131">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b9fa-131">ADO.NET Overview</span></span>](ado-net-overview.md)
