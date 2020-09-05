---
ms.openlocfilehash: 8c593fa6490451c6236f0d4390f09d4e9e4f0cbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497729"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>Inna obsługa wyjątków dla metod ObjectContext. isdatabase i DbProviderServices. isdatabase

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, jeśli Tworzenie bazy danych nie powiedzie się, <code>CreateDatabase</code> metody będą próbować usunąć pustą bazę danych. Jeśli ta operacja zakończy się pomyślnie, oryginalny <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> zostanie rozpropagowany (zamiast elementu <xref:System.InvalidOperationException?displayProperty=fullName> , który został zawsze wygenerowany w .NET Framework 4,0)

#### <a name="suggestion"></a>Sugestia

Podczas przechwytywania <xref:System.InvalidOperationException?displayProperty=fullName> podczas wykonywania lub należy <xref:System.Data.Objects.ObjectContext.CreateDatabase> <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> również przechwycić wyjątek SqlExceptions.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>
- <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`
- `M:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)`

-->
