---
ms.openlocfilehash: 81992e57d7e92b4df92ce68870c0272d6cd5b220
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496261"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>Obiekt ObjectContext. tłumaczenia i ObjectContext.ExecuteStoreQuery teraz obsługują typ wyliczeniowy

#### <a name="details"></a>Szczegóły

W .NET Framework 4,0 parametr generyczny <code>T</code> <code>ObjectContext.Translate</code> i metody nie <code>ObjectContext.ExecuteStoreQuery</code> mogą być wyliczeniem. Ten scenariusz jest teraz obsługiwany.

#### <a name="suggestion"></a>Sugestia

Jeśli polecenie Przetłumacz lub ExecuteStoreQuery zostało wywołane w typie wyliczeniowym w .NET Framework 4,0, zwrócono wartość "0". W przypadku pożądanego zachowania, wywołania powinny być zastępowane stałą 0 (lub równoważnej wyliczeniu).

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|

<!--

#### Affected APIs

- ``M:System.Data.Objects.ObjectContext.Translate``1(System.Data.Common.DbDataReader)``
- ``M:System.Data.Objects.ObjectContext.Translate``1(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)``
- ``M:System.Data.Objects.ObjectContext.ExecuteStoreQuery``1(System.String,System.Object[])``
- ``M:System.Data.Objects.ObjectContext.ExecuteStoreQuery``1(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])``

-->
