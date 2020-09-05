---
ms.openlocfilehash: 200c22a1b83149d833a083365ebb65d0e80bc31a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497480"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="032c4-101">Funkcja WCF AddressHeaderCollection teraz generuje ArgumentException, jeśli element addressHeader ma wartość null</span><span class="sxs-lookup"><span data-stu-id="032c4-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="032c4-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="032c4-102">Details</span></span>

<span data-ttu-id="032c4-103">Rozpoczynając od .NET Framework 4.7.1, <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> Konstruktor zgłasza, <xref:System.ArgumentException> Jeśli jeden z elementów jest <code>null</code> .</span><span class="sxs-lookup"><span data-stu-id="032c4-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="032c4-104">W .NET Framework 4,7 i wcześniejszych wersjach nie jest zgłaszany żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="032c4-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="032c4-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="032c4-105">Suggestion</span></span>

<span data-ttu-id="032c4-106">Jeśli wystąpią problemy ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszej wersji, możesz zrezygnować z niej, dodając następujący wiersz do <code>&lt;runtime&gt;</code> sekcji pliku app.config::</span><span class="sxs-lookup"><span data-stu-id="032c4-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="032c4-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="032c4-107">Name</span></span>    | <span data-ttu-id="032c4-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="032c4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="032c4-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="032c4-109">Scope</span></span>   |<span data-ttu-id="032c4-110">Mały</span><span class="sxs-lookup"><span data-stu-id="032c4-110">Minor</span></span>|
|<span data-ttu-id="032c4-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="032c4-111">Version</span></span>|<span data-ttu-id="032c4-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="032c4-112">4.7.1</span></span>|
|<span data-ttu-id="032c4-113">Typ</span><span class="sxs-lookup"><span data-stu-id="032c4-113">Type</span></span>|<span data-ttu-id="032c4-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="032c4-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="032c4-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="032c4-115">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
