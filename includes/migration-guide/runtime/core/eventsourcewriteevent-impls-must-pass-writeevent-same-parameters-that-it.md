---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496496"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="ec00a-101">Element EventSource. metody WriteEvent Impls musi przekazać metody WriteEvent te same parametry, które otrzymały (plus ID)</span><span class="sxs-lookup"><span data-stu-id="ec00a-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="ec00a-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ec00a-102">Details</span></span>

<span data-ttu-id="ec00a-103">Środowisko wykonawcze wymusza teraz kontrakt, który określa następujące elementy: Klasa pochodna <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> , która definiuje metodę zdarzenia ETW, musi wywołać metodę klasy bazowej <code>EventSource.WriteEvent</code> z identyfikatorem zdarzenia, po którym następują te same argumenty, które zostały przekazane przez metodę zdarzenia ETW.</span><span class="sxs-lookup"><span data-stu-id="ec00a-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ec00a-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="ec00a-104">Suggestion</span></span>

<span data-ttu-id="ec00a-105"><xref:System.IndexOutOfRangeException?displayProperty=fullName>Wyjątek jest generowany, jeśli <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> dane są odczytywane <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> w procesie dla źródła zdarzenia, które narusza ten kontrakt.</span><span class="sxs-lookup"><span data-stu-id="ec00a-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="ec00a-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="ec00a-106">Name</span></span>    | <span data-ttu-id="ec00a-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="ec00a-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ec00a-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="ec00a-108">Scope</span></span>   |<span data-ttu-id="ec00a-109">Mały</span><span class="sxs-lookup"><span data-stu-id="ec00a-109">Minor</span></span>|
|<span data-ttu-id="ec00a-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="ec00a-110">Version</span></span>|<span data-ttu-id="ec00a-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="ec00a-111">4.5.1</span></span>|
|<span data-ttu-id="ec00a-112">Typ</span><span class="sxs-lookup"><span data-stu-id="ec00a-112">Type</span></span>|<span data-ttu-id="ec00a-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="ec00a-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ec00a-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ec00a-114">Affected APIs</span></span>

<span data-ttu-id="ec00a-115">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="ec00a-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
