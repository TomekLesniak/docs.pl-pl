---
title: Konwertowanie typów .NET na ciągi
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: ca35af17a402dc901c02edf94099af1377e1160f
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687622"
---
# <a name="convert-net-types-to-strings"></a><span data-ttu-id="2dfcf-102">Konwertuj typy .NET na ciągi</span><span class="sxs-lookup"><span data-stu-id="2dfcf-102">Convert .NET types to strings</span></span>

<span data-ttu-id="2dfcf-103">Jeśli chcesz skonwertować typ .NET na ciąg, użyj metody **ToString** .</span><span class="sxs-lookup"><span data-stu-id="2dfcf-103">If you want to convert a .NET type to a string, use the **ToString** method.</span></span> <span data-ttu-id="2dfcf-104">Metoda **ToString** zwraca ciąg reprezentujący typ, który został przesłany.</span><span class="sxs-lookup"><span data-stu-id="2dfcf-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="2dfcf-105">Poniższa tabela zawiera listę typów .NET, które zwracają ciąg w formacie, który jest mapowany na specyfikacje schematu XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="2dfcf-105">The following table lists the .NET types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="2dfcf-106">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="2dfcf-106">.NET type</span></span>|<span data-ttu-id="2dfcf-107">Zwrócony typ ciągu</span><span class="sxs-lookup"><span data-stu-id="2dfcf-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="2dfcf-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="2dfcf-108">Boolean</span></span>|<span data-ttu-id="2dfcf-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="2dfcf-109">"true", "false"</span></span>|  
|<span data-ttu-id="2dfcf-110">Single. PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="2dfcf-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="2dfcf-111">INF</span><span class="sxs-lookup"><span data-stu-id="2dfcf-111">"INF"</span></span>|  
|<span data-ttu-id="2dfcf-112">Single. NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="2dfcf-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="2dfcf-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="2dfcf-113">"-INF"</span></span>|  
|<span data-ttu-id="2dfcf-114">Double. PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="2dfcf-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="2dfcf-115">INF</span><span class="sxs-lookup"><span data-stu-id="2dfcf-115">"INF"</span></span>|  
|<span data-ttu-id="2dfcf-116">Double. NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="2dfcf-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="2dfcf-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="2dfcf-117">"-INF"</span></span>|  
|<span data-ttu-id="2dfcf-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="2dfcf-118">DateTime</span></span>|<span data-ttu-id="2dfcf-119">Format to RRRR-MM-DDTgg: mm: sszzzzzz i jego podzestawy.</span><span class="sxs-lookup"><span data-stu-id="2dfcf-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="2dfcf-120">Zakres czasu</span><span class="sxs-lookup"><span data-stu-id="2dfcf-120">Timespan</span></span>|<span data-ttu-id="2dfcf-121">Format to PnYnMnTnHnMnS, na przykład, `P2Y10M15DT10H30M20S` wynosi okres 2 lat, 10 miesięcy, 15 dni, 10hours, 30 minut i 20 sekund.</span><span class="sxs-lookup"><span data-stu-id="2dfcf-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2dfcf-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2dfcf-122">See also</span></span>

- [<span data-ttu-id="2dfcf-123">Konwersja typów danych XML</span><span class="sxs-lookup"><span data-stu-id="2dfcf-123">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)
- [<span data-ttu-id="2dfcf-124">Konwertowanie ciągów na typy danych .NET</span><span class="sxs-lookup"><span data-stu-id="2dfcf-124">Converting Strings to .NET Data Types</span></span>](converting-strings-to-dotnet-data-types.md)
