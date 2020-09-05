---
ms.openlocfilehash: 26539011f0650c7a3bac9e1c41847561905fff58
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496346"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="43707-101">Kontrolki hostingu zarządzanej przeglądarki z .NET Framework 1,1 i 2,0 są blokowane</span><span class="sxs-lookup"><span data-stu-id="43707-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="43707-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="43707-102">Details</span></span>

<span data-ttu-id="43707-103">Obsługa tych formantów jest zablokowana w programie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="43707-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="43707-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="43707-104">Suggestion</span></span>

<span data-ttu-id="43707-105">Program Internet Explorer nie będzie mógł uruchomić aplikacji, która używa formantów zarządzanego hostingu w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="43707-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="43707-106">Poprzednie zachowanie można przywrócić, ustawiając wartość EnableIEHosting podklucza rejestru dla <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> <code>1</code> systemów x86 i dla procesów 32-bitowych w systemach x64 oraz ustawiając <code>EnableIEHosting</code> wartość podklucza rejestru dla <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> <code>1</code> procesów 64-bitowych w systemach x64.</span><span class="sxs-lookup"><span data-stu-id="43707-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="43707-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="43707-107">Name</span></span>    | <span data-ttu-id="43707-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="43707-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="43707-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="43707-109">Scope</span></span>   |<span data-ttu-id="43707-110">Mały</span><span class="sxs-lookup"><span data-stu-id="43707-110">Minor</span></span>|
|<span data-ttu-id="43707-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="43707-111">Version</span></span>|<span data-ttu-id="43707-112">4.5</span><span class="sxs-lookup"><span data-stu-id="43707-112">4.5</span></span>|
|<span data-ttu-id="43707-113">Typ</span><span class="sxs-lookup"><span data-stu-id="43707-113">Type</span></span>|<span data-ttu-id="43707-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="43707-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="43707-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="43707-115">Affected APIs</span></span>

<span data-ttu-id="43707-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="43707-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
