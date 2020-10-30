---
title: Niezależne od kultury operacje na ciągach
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET], culture-insensitive string operations
- strings [.NET], culture-insensitive string operations
- localization [.NET], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
ms.openlocfilehash: 3a6085d15dbaa30144436b163a6ecb777698f4f1
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064005"
---
# <a name="culture-insensitive-string-operations"></a><span data-ttu-id="27fd8-102">Niezależne od kultury operacje na ciągach</span><span class="sxs-lookup"><span data-stu-id="27fd8-102">Culture-insensitive string operations</span></span>

<span data-ttu-id="27fd8-103">Operacje na ciągach, w których jest uwzględniana kultura, mogą okazać się przydatne w przypadku tworzenia aplikacji, które mają wyświetlać wyniki użytkownikom na podstawie kultury.</span><span class="sxs-lookup"><span data-stu-id="27fd8-103">Culture-sensitive string operations can be an advantage if you are creating applications designed to display results to users on a per-culture basis.</span></span> <span data-ttu-id="27fd8-104">Domyślnie metody uwzględniające kulturę uzyskują kulturę do użycia z <xref:System.Globalization.CultureInfo.CurrentCulture%2A> właściwości bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="27fd8-104">By default, culture-sensitive methods obtain the culture to use from the <xref:System.Globalization.CultureInfo.CurrentCulture%2A> property for the current thread.</span></span>

<span data-ttu-id="27fd8-105">Czasami Operacje na ciągach zależnych od kultury nie są pożądane.</span><span class="sxs-lookup"><span data-stu-id="27fd8-105">Sometimes, culture-sensitive string operations are not the desired behavior.</span></span> <span data-ttu-id="27fd8-106">Używanie operacji, w których jest uwzględniana kultura, gdy wyniki powinny być niezależne od kultury, może spowodować, że kod aplikacji przestanie działać w przypadku kultur z niestandardowymi mapowaniami wielkości liter i regułami sortowania.</span><span class="sxs-lookup"><span data-stu-id="27fd8-106">Using culture-sensitive operations when results should be independent of culture can cause application code to fail on cultures with custom case mappings and sorting rules.</span></span> <span data-ttu-id="27fd8-107">Aby zapoznać się z przykładem, zobacz sekcję ["porównania ciągów, które używają bieżącej kultury"](../base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture) w artykule [najlepsze rozwiązania dotyczące używania ciągów](../base-types/best-practices-strings.md) .</span><span class="sxs-lookup"><span data-stu-id="27fd8-107">For an example, see the ["String Comparisons that Use the Current Culture"](../base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture) section in the [Best Practices for Using Strings](../base-types/best-practices-strings.md) article.</span></span>

<span data-ttu-id="27fd8-108">To, czy w operacjach na ciągach powinna być uwzględniana kultura, zależy od tego, jak aplikacja używa wyników.</span><span class="sxs-lookup"><span data-stu-id="27fd8-108">Whether string operations should be culture-sensitive or culture-insensitive depends on how your application uses the results.</span></span> <span data-ttu-id="27fd8-109">W operacjach na ciągach, które wyświetlają wyniki użytkownikowi, zazwyczaj powinna być uwzględniana kultura.</span><span class="sxs-lookup"><span data-stu-id="27fd8-109">String operations that display results to the user should typically be culture-sensitive.</span></span> <span data-ttu-id="27fd8-110">Na przykład jeśli aplikacja wyświetla posortowaną listę zlokalizowanych ciągów w polu listy, aplikacja powinna wykonać sortowanie z uwzględnieniem kultury.</span><span class="sxs-lookup"><span data-stu-id="27fd8-110">For example, if an application displays a sorted list of localized strings in a list box, the application should perform a culture-sensitive sort.</span></span>

<span data-ttu-id="27fd8-111">W wynikach operacji na ciągach, które są używane wewnętrznie, zazwyczaj nie powinna być uwzględniana kultura.</span><span class="sxs-lookup"><span data-stu-id="27fd8-111">Results of string operations that are used internally should typically be culture-insensitive.</span></span> <span data-ttu-id="27fd8-112">Ogólnie, jeśli aplikacja wykonuje operacje na nazwach plików, formatach trwałości lub informacjach symbolicznych, które nie są wyświetlane użytkownikowi, wyniki operacji na ciągach nie powinny ulegać zmianie w zależności od kultury.</span><span class="sxs-lookup"><span data-stu-id="27fd8-112">In general, if the application is working with file names, persistence formats, or symbolic information that is not displayed to the user, results of string operations should not vary by culture.</span></span> <span data-ttu-id="27fd8-113">Na przykład jeśli aplikacja porównuje ciąg w celu ustalenia, czy jest on rozpoznawanym tagiem XML, w porównaniu nie powinna być uwzględniana kultura.</span><span class="sxs-lookup"><span data-stu-id="27fd8-113">For example, if an application compares a string to determine whether it is a recognized XML tag, the comparison should not be culture-sensitive.</span></span> <span data-ttu-id="27fd8-114">Ponadto, jeśli decyzja dotycząca zabezpieczeń opiera się na wyniku porównania ciągów lub operacji zmiany wielkości liter, operacja powinna być niezależna od kultury, aby zapewnić, że wynik nie będzie miał wpływ na wartość <xref:System.Globalization.CultureInfo.CurrentCulture%2A> .</span><span class="sxs-lookup"><span data-stu-id="27fd8-114">In addition, if a security decision is based on the result of a string comparison or case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.</span></span>

<span data-ttu-id="27fd8-115">Bez względu na to, czy tworzysz aplikację, która zawiera kod do obsługi problemów dotyczących lokalizacji i globalizacji, należy pamiętać o metodach .NET, które domyślnie pobierają dane zależne od kultury.</span><span class="sxs-lookup"><span data-stu-id="27fd8-115">Whether or not you're developing an application that includes code to handle localization and globalization issues, you should be aware of the .NET methods that retrieve culture-sensitive results by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="27fd8-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="27fd8-116">See also</span></span>

- [<span data-ttu-id="27fd8-117">Globalizacja i lokalizacja</span><span class="sxs-lookup"><span data-stu-id="27fd8-117">Globalization and Localization</span></span>](index.md)
