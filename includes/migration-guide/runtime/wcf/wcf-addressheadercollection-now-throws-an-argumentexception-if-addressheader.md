---
ms.openlocfilehash: 3506653bfc749ae3d8002715ca72ca89de7a681b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "91024871"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="b9bc9-101">Funkcja WCF AddressHeaderCollection teraz generuje ArgumentException, jeśli element addressHeader ma wartość null</span><span class="sxs-lookup"><span data-stu-id="b9bc9-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="b9bc9-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b9bc9-102">Details</span></span>

<span data-ttu-id="b9bc9-103">Rozpoczynając od .NET Framework 4.7.1, <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> Konstruktor zgłasza, <xref:System.ArgumentException> Jeśli jeden z elementów jest `null` .</span><span class="sxs-lookup"><span data-stu-id="b9bc9-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is `null`.</span></span> <span data-ttu-id="b9bc9-104">W .NET Framework 4,7 i wcześniejszych wersjach nie jest zgłaszany żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="b9bc9-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b9bc9-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="b9bc9-105">Suggestion</span></span>

<span data-ttu-id="b9bc9-106">Jeśli wystąpią problemy ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszej wersji, możesz zrezygnować z niej, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="b9bc9-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="b9bc9-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b9bc9-107">Name</span></span>    | <span data-ttu-id="b9bc9-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="b9bc9-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="b9bc9-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="b9bc9-109">Scope</span></span>   | <span data-ttu-id="b9bc9-110">Mały</span><span class="sxs-lookup"><span data-stu-id="b9bc9-110">Minor</span></span>   |
| <span data-ttu-id="b9bc9-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="b9bc9-111">Version</span></span> | <span data-ttu-id="b9bc9-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b9bc9-112">4.7.1</span></span>   |
| <span data-ttu-id="b9bc9-113">Typ</span><span class="sxs-lookup"><span data-stu-id="b9bc9-113">Type</span></span>    | <span data-ttu-id="b9bc9-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="b9bc9-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b9bc9-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b9bc9-115">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
