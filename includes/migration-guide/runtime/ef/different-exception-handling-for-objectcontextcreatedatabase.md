---
ms.openlocfilehash: 8c593fa6490451c6236f0d4390f09d4e9e4f0cbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497729"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="020d5-101">Inna obsługa wyjątków dla metod ObjectContext. isdatabase i DbProviderServices. isdatabase</span><span class="sxs-lookup"><span data-stu-id="020d5-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

#### <a name="details"></a><span data-ttu-id="020d5-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="020d5-102">Details</span></span>

<span data-ttu-id="020d5-103">Począwszy od .NET Framework 4,5, jeśli Tworzenie bazy danych nie powiedzie się, <code>CreateDatabase</code> metody będą próbować usunąć pustą bazę danych.</span><span class="sxs-lookup"><span data-stu-id="020d5-103">Beginning in .NET Framework 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="020d5-104">Jeśli ta operacja zakończy się pomyślnie, oryginalny <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> zostanie rozpropagowany (zamiast elementu <xref:System.InvalidOperationException?displayProperty=fullName> , który został zawsze wygenerowany w .NET Framework 4,0)</span><span class="sxs-lookup"><span data-stu-id="020d5-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=fullName> that was always thrown in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="020d5-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="020d5-105">Suggestion</span></span>

<span data-ttu-id="020d5-106">Podczas przechwytywania <xref:System.InvalidOperationException?displayProperty=fullName> podczas wykonywania lub należy <xref:System.Data.Objects.ObjectContext.CreateDatabase> <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> również przechwycić wyjątek SqlExceptions.</span><span class="sxs-lookup"><span data-stu-id="020d5-106">When catching an <xref:System.InvalidOperationException?displayProperty=fullName> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>

| <span data-ttu-id="020d5-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="020d5-107">Name</span></span>    | <span data-ttu-id="020d5-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="020d5-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="020d5-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="020d5-109">Scope</span></span>   |<span data-ttu-id="020d5-110">Mały</span><span class="sxs-lookup"><span data-stu-id="020d5-110">Minor</span></span>|
|<span data-ttu-id="020d5-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="020d5-111">Version</span></span>|<span data-ttu-id="020d5-112">4.5</span><span class="sxs-lookup"><span data-stu-id="020d5-112">4.5</span></span>|
|<span data-ttu-id="020d5-113">Typ</span><span class="sxs-lookup"><span data-stu-id="020d5-113">Type</span></span>|<span data-ttu-id="020d5-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="020d5-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="020d5-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="020d5-115">Affected APIs</span></span>

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>
- <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`
- `M:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)`

-->
