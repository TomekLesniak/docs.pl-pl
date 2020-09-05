---
ms.openlocfilehash: 6d7f998cda6326e1f584713576a0aa27b3a68655
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497847"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="fe1d1-101">Sprawdzanie pisowni WPF w kontrolkach z obsługą tekstu nie będzie działało w systemie Windows 10 dla języków, które nie są na liście języków wejściowych systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="fe1d1-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

#### <a name="details"></a><span data-ttu-id="fe1d1-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="fe1d1-102">Details</span></span>

<span data-ttu-id="fe1d1-103">W przypadku uruchamiania w systemie Windows 10 sprawdzanie pisowni może nie działać w przypadku kontrolek z obsługą tekstu WPF, ponieważ możliwości sprawdzania pisowni platformy są dostępne tylko dla języków znajdujących się na liście języków wejściowych. W systemie Windows 10 po dodaniu języka do listy dostępnych klawiatur system Windows automatycznie pobiera i instaluje odpowiedni pakiet funkcji na żądanie (FDZ), który zapewnia możliwości sprawdzania pisowni.</span><span class="sxs-lookup"><span data-stu-id="fe1d1-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="fe1d1-104">Po dodaniu języka do listy języków wejściowych sprawdzanie pisowni będzie obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="fe1d1-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fe1d1-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="fe1d1-105">Suggestion</span></span>

<span data-ttu-id="fe1d1-106">Należy pamiętać, że język lub tekst do sprawdzenia pisowni należy dodać jako język wejściowy do sprawdzania pisowni w systemie Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fe1d1-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>

| <span data-ttu-id="fe1d1-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="fe1d1-107">Name</span></span>    | <span data-ttu-id="fe1d1-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe1d1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fe1d1-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="fe1d1-109">Scope</span></span>   |<span data-ttu-id="fe1d1-110">Edge</span><span class="sxs-lookup"><span data-stu-id="fe1d1-110">Edge</span></span>|
|<span data-ttu-id="fe1d1-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="fe1d1-111">Version</span></span>|<span data-ttu-id="fe1d1-112">4,6</span><span class="sxs-lookup"><span data-stu-id="fe1d1-112">4.6</span></span>|
|<span data-ttu-id="fe1d1-113">Typ</span><span class="sxs-lookup"><span data-stu-id="fe1d1-113">Type</span></span>|<span data-ttu-id="fe1d1-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="fe1d1-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="fe1d1-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="fe1d1-115">Affected APIs</span></span>

<span data-ttu-id="fe1d1-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="fe1d1-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
