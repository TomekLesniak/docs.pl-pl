---
ms.openlocfilehash: d4e60f2a59980263916718ebcc71cc359952c031
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497266"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="e7d7e-101">Sprawdzanie pisowni WPF kończy się niepowodzeniem na nieoczekiwany sposób</span><span class="sxs-lookup"><span data-stu-id="e7d7e-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="e7d7e-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="e7d7e-102">Details</span></span>

<span data-ttu-id="e7d7e-103">Obejmuje to wiele problemów z modułem sprawdzania pisowni WPF:</span><span class="sxs-lookup"><span data-stu-id="e7d7e-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="e7d7e-104">Moduł sprawdzania pisowni WPF czasami zgłasza <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e7d7e-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="e7d7e-105">Sprawdzanie pisowni WPF kończy się niepowodzeniem, <xref:System.UnauthorizedAccessException> gdy aplikacje są uruchamiane za pomocą polecenia "Uruchom jako inny użytkownik"</span><span class="sxs-lookup"><span data-stu-id="e7d7e-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="e7d7e-106">Moduł sprawdzania pisowni WPF nieprawidłowo identyfikuje błędy pisowni w wyrazach złożonych, takich jak "Hausnummer" w języku niemieckim.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="e7d7e-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="e7d7e-107">Suggestion</span></span>

<span data-ttu-id="e7d7e-108">Problem #1 — ten problem został rozwiązany w programie .NET Framework 4.6.2 #2 — funkcja sprawdzania pisowni WPF nie jest już obsługiwana, gdy aplikacje są uruchamiane za pomocą polecenia "Uruchom jako inny użytkownik".</span><span class="sxs-lookup"><span data-stu-id="e7d7e-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="e7d7e-109">Uruchamianie .NET Framework 4.6.2, aplikacje uruchomione w ten sposób nie przestaną działać w sposób nieoczekiwany — zamiast tego sprawdzanie pisowni zostanie wyłączone w trybie dyskretnym.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="e7d7e-110">#3 problemu — ten problem został rozwiązany w .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="e7d7e-111">Nazwa</span><span class="sxs-lookup"><span data-stu-id="e7d7e-111">Name</span></span>    | <span data-ttu-id="e7d7e-112">Wartość</span><span class="sxs-lookup"><span data-stu-id="e7d7e-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e7d7e-113">Zakres</span><span class="sxs-lookup"><span data-stu-id="e7d7e-113">Scope</span></span>   |<span data-ttu-id="e7d7e-114">Edge</span><span class="sxs-lookup"><span data-stu-id="e7d7e-114">Edge</span></span>|
|<span data-ttu-id="e7d7e-115">Wersja</span><span class="sxs-lookup"><span data-stu-id="e7d7e-115">Version</span></span>|<span data-ttu-id="e7d7e-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e7d7e-116">4.6.1</span></span>|
|<span data-ttu-id="e7d7e-117">Typ</span><span class="sxs-lookup"><span data-stu-id="e7d7e-117">Type</span></span>|<span data-ttu-id="e7d7e-118">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="e7d7e-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e7d7e-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="e7d7e-119">Affected APIs</span></span>

<span data-ttu-id="e7d7e-120">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="e7d7e-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
