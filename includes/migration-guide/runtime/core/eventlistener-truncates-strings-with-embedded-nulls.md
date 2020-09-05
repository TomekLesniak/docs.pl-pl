---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497055"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="41658-101">Odbiornika obcina ciągi z osadzonymi wartościami null</span><span class="sxs-lookup"><span data-stu-id="41658-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="41658-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="41658-102">Details</span></span>

<span data-ttu-id="41658-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> obcina ciągi z osadzonymi wartościami null.</span><span class="sxs-lookup"><span data-stu-id="41658-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="41658-104">Klasa nie obsługuje znaków o wartości null <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="41658-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="41658-105">Zmiana ta dotyczy tylko aplikacji, które używają <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> do odczytu <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> danych w procesie i używania znaków null jako ograniczników.</span><span class="sxs-lookup"><span data-stu-id="41658-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="41658-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="41658-106">Suggestion</span></span>

<span data-ttu-id="41658-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> dane powinny być aktualizowane, jeśli jest to możliwe, nie mogą być używane w osadzonych znakach null.</span><span class="sxs-lookup"><span data-stu-id="41658-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="41658-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="41658-108">Name</span></span>    | <span data-ttu-id="41658-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="41658-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="41658-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="41658-110">Scope</span></span>   |<span data-ttu-id="41658-111">Edge</span><span class="sxs-lookup"><span data-stu-id="41658-111">Edge</span></span>|
|<span data-ttu-id="41658-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="41658-112">Version</span></span>|<span data-ttu-id="41658-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="41658-113">4.5.1</span></span>|
|<span data-ttu-id="41658-114">Typ</span><span class="sxs-lookup"><span data-stu-id="41658-114">Type</span></span>|<span data-ttu-id="41658-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="41658-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="41658-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="41658-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
