---
ms.openlocfilehash: 9f5f238e3d4222af1da3a1713e1b3e65de6e6f49
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "91024900"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="733be-101">Funkcja WCF PipeConnection. GetHashAlgorithm używa teraz SHA256</span><span class="sxs-lookup"><span data-stu-id="733be-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="733be-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="733be-102">Details</span></span>

<span data-ttu-id="733be-103">Rozpoczynając od .NET Framework 4.7.1, Windows Communication Foundation używa skrótu SHA256 do generowania losowych nazw dla nazwanych potoków.</span><span class="sxs-lookup"><span data-stu-id="733be-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="733be-104">W .NET Framework 4,7 i starszych wersjach użyto skrótu SHA1.</span><span class="sxs-lookup"><span data-stu-id="733be-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="733be-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="733be-105">Suggestion</span></span>

<span data-ttu-id="733be-106">Jeśli wystąpi problem ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszym, możesz go wycofać, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="733be-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="733be-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="733be-107">Name</span></span>    | <span data-ttu-id="733be-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="733be-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="733be-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="733be-109">Scope</span></span>   | <span data-ttu-id="733be-110">Mały</span><span class="sxs-lookup"><span data-stu-id="733be-110">Minor</span></span>   |
| <span data-ttu-id="733be-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="733be-111">Version</span></span> | <span data-ttu-id="733be-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="733be-112">4.7.1</span></span>   |
| <span data-ttu-id="733be-113">Typ</span><span class="sxs-lookup"><span data-stu-id="733be-113">Type</span></span>    | <span data-ttu-id="733be-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="733be-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="733be-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="733be-115">Affected APIs</span></span>

<span data-ttu-id="733be-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="733be-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
