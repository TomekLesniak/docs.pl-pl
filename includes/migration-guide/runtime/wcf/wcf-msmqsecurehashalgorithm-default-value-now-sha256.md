---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770848"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="b1118-101">Wartość domyślna MsmqSecureHashAlgorithm WCF jest teraz SHA256</span><span class="sxs-lookup"><span data-stu-id="b1118-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="b1118-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b1118-102">Details</span></span>

<span data-ttu-id="b1118-103">Począwszy od .NET Framework 4.7.1, domyślny algorytm podpisywania komunikatów w programie WCF dla komunikatów usługi MSMQ to SHA256.</span><span class="sxs-lookup"><span data-stu-id="b1118-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="b1118-104">W .NET Framework 4,7 i wcześniejszych wersjach domyślny algorytm podpisywania wiadomości to SHA1.</span><span class="sxs-lookup"><span data-stu-id="b1118-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b1118-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="b1118-105">Suggestion</span></span>

<span data-ttu-id="b1118-106">W przypadku wystąpienia problemów ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszym można zrezygnować z zmiany, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="b1118-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| <span data-ttu-id="b1118-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b1118-107">Name</span></span>    | <span data-ttu-id="b1118-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="b1118-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="b1118-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="b1118-109">Scope</span></span>   | <span data-ttu-id="b1118-110">Mały</span><span class="sxs-lookup"><span data-stu-id="b1118-110">Minor</span></span>   |
| <span data-ttu-id="b1118-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="b1118-111">Version</span></span> | <span data-ttu-id="b1118-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b1118-112">4.7.1</span></span>   |
| <span data-ttu-id="b1118-113">Typ</span><span class="sxs-lookup"><span data-stu-id="b1118-113">Type</span></span>    | <span data-ttu-id="b1118-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="b1118-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b1118-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b1118-115">Affected APIs</span></span>

<span data-ttu-id="b1118-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="b1118-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
