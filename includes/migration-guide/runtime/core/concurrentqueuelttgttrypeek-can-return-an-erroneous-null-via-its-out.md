---
ms.openlocfilehash: 004e2d1883b631e88ab5e164b1120c3b081b7041
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497481"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue &lt; T &gt; . TryPeek może zwrócić błędną wartość null za pośrednictwem jego parametru out

#### <a name="details"></a>Szczegóły

W niektórych scenariuszach wielowątkowych <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> można zwrócić wartość true, ale wypełnić parametr out wartością null (zamiast poprawnej wartości z możliwością wglądu).

#### <a name="suggestion"></a>Sugestia

Ten problem został rozwiązany w .NET Framework 4.5.1. Uaktualnienie do tego środowiska spowoduje rozwiązanie tego problemu.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Duży|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.ConcurrentQueue`1.TryPeek(`0@)``

-->
