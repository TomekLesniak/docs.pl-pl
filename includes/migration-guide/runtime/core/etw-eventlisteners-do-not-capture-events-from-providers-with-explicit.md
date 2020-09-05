---
ms.openlocfilehash: 5a96b40e5e0df6a47415acecab410444a713632b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497646"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a><span data-ttu-id="8e0a1-101">EventListeners ETW nie przechwytuje zdarzeń z dostawców z jawnymi słowami kluczowymi (takimi jak dostawca TPL)</span><span class="sxs-lookup"><span data-stu-id="8e0a1-101">ETW EventListeners do not capture events from providers with explicit keywords (like the TPL provider)</span></span>

#### <a name="details"></a><span data-ttu-id="8e0a1-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="8e0a1-102">Details</span></span>

<span data-ttu-id="8e0a1-103">EventListeners ETW z pustą maską słowa kluczowego niepoprawnie przechwytuje zdarzenia z dostawców z jawnymi słowami kluczowymi.</span><span class="sxs-lookup"><span data-stu-id="8e0a1-103">ETW EventListeners with a blank keyword mask do not properly capture events from providers with explicit keywords.</span></span> <span data-ttu-id="8e0a1-104">W .NET Framework 4,5 dostawca TPL rozpoczął dostarczanie jawnych słów kluczowych i wyzwolił ten problem.</span><span class="sxs-lookup"><span data-stu-id="8e0a1-104">In the .NET Framework 4.5, the TPL provider began providing explicit keywords and triggered this issue.</span></span> <span data-ttu-id="8e0a1-105">W .NET Framework 4,6 EventListeners zostały zaktualizowane, aby nie miały już tego problemu.</span><span class="sxs-lookup"><span data-stu-id="8e0a1-105">In the .NET Framework 4.6, EventListeners have been updated to no longer have this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8e0a1-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="8e0a1-106">Suggestion</span></span>

<span data-ttu-id="8e0a1-107">Aby obejść ten problem, Zastąp wywołania wywołaniami <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> przeciążenia EnableEvents, które jawnie określa &quot; maskę słów kluczowych &quot; do użycia: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code> . Alternatywnie ten problem został rozwiązany w .NET Framework 4,6 i może zostać rozwiązany przez uaktualnienie do tej wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e0a1-107">To work around this problem, replace calls to <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> with calls to the EnableEvents overload that explicitly specifies the &quot;any keywords&quot; mask to use: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>.Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="8e0a1-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="8e0a1-108">Name</span></span>    | <span data-ttu-id="8e0a1-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="8e0a1-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8e0a1-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="8e0a1-110">Scope</span></span>   |<span data-ttu-id="8e0a1-111">Edge</span><span class="sxs-lookup"><span data-stu-id="8e0a1-111">Edge</span></span>|
|<span data-ttu-id="8e0a1-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="8e0a1-112">Version</span></span>|<span data-ttu-id="8e0a1-113">4.5</span><span class="sxs-lookup"><span data-stu-id="8e0a1-113">4.5</span></span>|
|<span data-ttu-id="8e0a1-114">Typ</span><span class="sxs-lookup"><span data-stu-id="8e0a1-114">Type</span></span>|<span data-ttu-id="8e0a1-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="8e0a1-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8e0a1-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8e0a1-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`

-->
