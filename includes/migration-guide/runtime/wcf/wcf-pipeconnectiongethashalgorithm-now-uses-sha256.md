---
ms.openlocfilehash: 3cf1740565343558a85fdfa68957773468c28231
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770771"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="74c78-101">Funkcja WCF PipeConnection. GetHashAlgorithm używa teraz SHA256</span><span class="sxs-lookup"><span data-stu-id="74c78-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="74c78-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="74c78-102">Details</span></span>

<span data-ttu-id="74c78-103">Rozpoczynając od .NET Framework 4.7.1, Windows Communication Foundation używa skrótu SHA256 do generowania losowych nazw dla nazwanych potoków.</span><span class="sxs-lookup"><span data-stu-id="74c78-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="74c78-104">W .NET Framework 4,7 i starszych wersjach użyto skrótu SHA1.</span><span class="sxs-lookup"><span data-stu-id="74c78-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="74c78-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="74c78-105">Suggestion</span></span>

<span data-ttu-id="74c78-106">Jeśli wystąpi problem ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszym, możesz go wycofać, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="74c78-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>

| Name    | Value   |
|:--------|:--------|
| Scope   | Minor   |
| Version | 4.7.1   |
| Type    | Runtime |

#### Affected APIs

Not detectable via API analysis.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
