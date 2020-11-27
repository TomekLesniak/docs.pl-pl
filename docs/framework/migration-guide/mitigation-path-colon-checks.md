---
title: 'Środki zaradcze: sprawdzanie dwukropka ścieżki'
description: Dowiedz się więcej o zmianach wprowadzonych w .NET Framework 4.6.2 do obsługi sprawdzania odpowiedniej składni separatora dysku (dwukropek).
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: 03f1c7249549aae7e3bef986c97fb5f320fbeb2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283461"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="5dd2c-103">Środki zaradcze: sprawdzanie dwukropka ścieżki</span><span class="sxs-lookup"><span data-stu-id="5dd2c-103">Mitigation: Path Colon Checks</span></span>

<span data-ttu-id="5dd2c-104">Począwszy od aplikacji odnoszących się do .NET Framework 4.6.2, wprowadzono wiele zmian do obsługi poprzednio nieobsługiwanych ścieżek (zarówno pod względem długości, jak i formatu).</span><span class="sxs-lookup"><span data-stu-id="5dd2c-104">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="5dd2c-105">W szczególności sprawdza poprawność składni separatora dysku (dwukropek).</span><span class="sxs-lookup"><span data-stu-id="5dd2c-105">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="5dd2c-106">Wpływ</span><span class="sxs-lookup"><span data-stu-id="5dd2c-106">Impact</span></span>  

 <span data-ttu-id="5dd2c-107">Te zmiany blokują niektóre ścieżki URI <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> i <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> metody, które wcześniej były obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="5dd2c-107">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="5dd2c-108">Ograniczanie ryzyka</span><span class="sxs-lookup"><span data-stu-id="5dd2c-108">Mitigation</span></span>  

 <span data-ttu-id="5dd2c-109">Aby obejść problem z wcześniej akceptowalną ścieżką, która nie jest już obsługiwana przez <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> metody i, można wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="5dd2c-109">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="5dd2c-110">Ręcznie usuń schemat z adresu URL.</span><span class="sxs-lookup"><span data-stu-id="5dd2c-110">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="5dd2c-111">Na przykład Usuń `file://` adres URL.</span><span class="sxs-lookup"><span data-stu-id="5dd2c-111">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="5dd2c-112">Przekaż identyfikator URI do <xref:System.Uri> konstruktora i Pobierz wartość <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="5dd2c-112">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="5dd2c-113">Zrezygnuj z nowej normalizacji ścieżki, ustawiając `Switch.System.IO.UseLegacyPathHandling` <xref:System.AppContext> przełącznik na `true` .</span><span class="sxs-lookup"><span data-stu-id="5dd2c-113">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5dd2c-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5dd2c-114">See also</span></span>

- [<span data-ttu-id="5dd2c-115">Zgodność aplikacji</span><span class="sxs-lookup"><span data-stu-id="5dd2c-115">Application compatibility</span></span>](application-compatibility.md)
