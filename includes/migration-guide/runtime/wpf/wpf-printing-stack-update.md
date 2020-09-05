---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497049"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="f825a-101">Aktualizacja stosu drukowania WPF</span><span class="sxs-lookup"><span data-stu-id="f825a-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="f825a-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f825a-102">Details</span></span>

<span data-ttu-id="f825a-103">Interfejsy API drukowania platformy WPF korzystające z <xref:System.Printing.PrintQueue?displayProperty=fullName> interfejsu API Wywołaj teraz okna wywołującego na rzecz obecnie przestarzałego interfejsu API drukowania XPS.</span><span class="sxs-lookup"><span data-stu-id="f825a-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="f825a-104">Zmiany zostały wprowadzone z myślą o potrzebach. ani użytkownicy, ani deweloperzy nie powinni widzieć żadnych zmian w zachowaniu lub użyciu interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="f825a-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="f825a-105">Nowy stos drukowania jest domyślnie włączony podczas uruchamiania aktualizacji systemu Windows 10 dla twórców.</span><span class="sxs-lookup"><span data-stu-id="f825a-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="f825a-106">Stary stos drukowania nadal będzie działać tak samo jak wcześniej w starszych wersjach systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="f825a-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f825a-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="f825a-107">Suggestion</span></span>

<span data-ttu-id="f825a-108">Aby użyć starego stosu w aktualizacji systemu Windows 10 dla twórców, należy ustawić <code>UseXpsOMPrinting</code> wartość REG_DWORD <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> klucza rejestru na <code>1</code> .</span><span class="sxs-lookup"><span data-stu-id="f825a-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="f825a-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="f825a-109">Name</span></span>    | <span data-ttu-id="f825a-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="f825a-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f825a-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="f825a-111">Scope</span></span>   |<span data-ttu-id="f825a-112">Edge</span><span class="sxs-lookup"><span data-stu-id="f825a-112">Edge</span></span>|
|<span data-ttu-id="f825a-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="f825a-113">Version</span></span>|<span data-ttu-id="f825a-114">4,7</span><span class="sxs-lookup"><span data-stu-id="f825a-114">4.7</span></span>|
|<span data-ttu-id="f825a-115">Typ</span><span class="sxs-lookup"><span data-stu-id="f825a-115">Type</span></span>|<span data-ttu-id="f825a-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="f825a-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f825a-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f825a-117">Affected APIs</span></span>

<span data-ttu-id="f825a-118">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="f825a-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
