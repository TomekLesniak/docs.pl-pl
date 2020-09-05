---
ms.openlocfilehash: 19be8a7755d9b238ab6507eaa73319bddf39faa3
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496846"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a>Dane zapisywane do PrintSystemJobInfo. strumienia zadań muszą być w formacie XPS

#### <a name="details"></a>Szczegóły

<xref:System.Printing.PrintSystemJobInfo.JobStream>Właściwość uwidacznia strumień zadania drukowania. Użytkownik może wysyłać pierwotne dane do podstawowych składników drukowania systemu operacyjnego przez zapis do tego strumienia. Począwszy od .NET Framework 4,5 w systemie Windows 8 i nowszych wersjach systemu operacyjnego Windows, dane zapisywane w tym strumieniu muszą być w formacie XPS jako strumień pakietu.

#### <a name="suggestion"></a>Sugestia

Aby wydrukować zawartość wyjściową, można wykonać jedną z następujących czynności:<ul><li>Użyj <xref:System.Windows.Xps.XpsDocumentWriter> klasy do wyjściowej zawartości wydruku. Jest to zalecana alternatywa.</li><li>Upewnij się, że dane wysyłane do strumienia zwróconego przez <xref:System.Printing.PrintSystemJobInfo.JobStream> Właściwość są w formacie XPS jako strumień pakietu.</li></ul>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Printing.PrintSystemJobInfo.JobStream`

-->
