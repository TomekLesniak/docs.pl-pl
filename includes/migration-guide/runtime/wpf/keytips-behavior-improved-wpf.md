---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496184"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="4234a-101">Ulepszone zachowanie podpowiedzi w WPF</span><span class="sxs-lookup"><span data-stu-id="4234a-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="4234a-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="4234a-102">Details</span></span>

<span data-ttu-id="4234a-103">W celu zachowania zgodności z zachowaniem programu Microsoft Word i Eksploratora Windows należy zmodyfikować zachowanie podpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4234a-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="4234a-104">Sprawdzając, czy stan poradę dotyczącą klawiszy jest włączony lub nie jest w przypadku <xref:System.Windows.Input.KeyEventArgs.SystemKey> naciśnięcia (w szczególności <xref:System.Windows.Input.Key> lub <xref:System.Windows.Input.Key.F11> ), WPF odpowiednio obsługuje klucze poradę dotyczącą klawiszy.</span><span class="sxs-lookup"><span data-stu-id="4234a-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="4234a-105">Porady dotyczące klawisza umożliwiają teraz odrzucanie menu nawet wtedy, gdy jest ono otwierane za pomocą myszy.</span><span class="sxs-lookup"><span data-stu-id="4234a-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4234a-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="4234a-106">Suggestion</span></span>

<span data-ttu-id="4234a-107">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="4234a-107">N/A</span></span>

| <span data-ttu-id="4234a-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="4234a-108">Name</span></span>    | <span data-ttu-id="4234a-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="4234a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4234a-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="4234a-110">Scope</span></span>   |<span data-ttu-id="4234a-111">Edge</span><span class="sxs-lookup"><span data-stu-id="4234a-111">Edge</span></span>|
|<span data-ttu-id="4234a-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="4234a-112">Version</span></span>|<span data-ttu-id="4234a-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="4234a-113">4.7.2</span></span>|
|<span data-ttu-id="4234a-114">Typ</span><span class="sxs-lookup"><span data-stu-id="4234a-114">Type</span></span>|<span data-ttu-id="4234a-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="4234a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4234a-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="4234a-116">Affected APIs</span></span>

<span data-ttu-id="4234a-117">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="4234a-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
