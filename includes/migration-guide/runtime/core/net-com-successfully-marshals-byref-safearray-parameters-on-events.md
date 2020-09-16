---
ms.openlocfilehash: aadf5eb85c8736c29639d49bc8baf21545d2467c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606945"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="02804-101">Platforma .NET COM pomyślnie organizowana parametry ByRef SafeArray dla zdarzeń</span><span class="sxs-lookup"><span data-stu-id="02804-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="02804-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="02804-102">Details</span></span>

<span data-ttu-id="02804-103">W .NET Framework 4.7.2 i starszych wersjach parametr ByRef [SAFEARRAY](/windows/desktop/api/oaidl/ns-oaidl-safearray) dla zdarzenia com nie będzie mógł zostać przekierowany z powrotem do kodu natywnego.</span><span class="sxs-lookup"><span data-stu-id="02804-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="02804-104">Po zmianie tej zmiany element [SAFEARRAY](/windows/desktop/api/oaidl/ns-oaidl-safearray) zostanie teraz skierowany pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="02804-104">With this change the [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="02804-105">[x] Quirked</span><span class="sxs-lookup"><span data-stu-id="02804-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="02804-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="02804-106">Suggestion</span></span>

<span data-ttu-id="02804-107">Jeśli poprawne kierowanie parametrów ByRef w zdarzeniach COM powoduje przerwanie wykonywania, można wyłączyć ten kod, dodając następujący przełącznik konfiguracji do konfiguracji aplikacji:</span><span class="sxs-lookup"><span data-stu-id="02804-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="02804-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="02804-108">Name</span></span>    | <span data-ttu-id="02804-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="02804-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="02804-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="02804-110">Scope</span></span>   |<span data-ttu-id="02804-111">Mały</span><span class="sxs-lookup"><span data-stu-id="02804-111">Minor</span></span>|
|<span data-ttu-id="02804-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="02804-112">Version</span></span>|<span data-ttu-id="02804-113">4,8</span><span class="sxs-lookup"><span data-stu-id="02804-113">4.8</span></span>|
|<span data-ttu-id="02804-114">Typ</span><span class="sxs-lookup"><span data-stu-id="02804-114">Type</span></span>|<span data-ttu-id="02804-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="02804-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="02804-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="02804-116">Affected APIs</span></span>

<span data-ttu-id="02804-117">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="02804-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
