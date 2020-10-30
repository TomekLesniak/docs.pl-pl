---
title: Sprawdzenie możliwości lokalizacji
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET], localization
- localizability [.NET]
- international applications [.NET], localizability
- globalization [.NET], localizability
- culture, localizability
- localization [.NET], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
ms.openlocfilehash: 6aa0588ea4baa00be476a05c335cf2abaa22aab4
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064161"
---
# <a name="localizability-review"></a><span data-ttu-id="1e270-102">Sprawdzenie możliwości lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1e270-102">Localizability review</span></span>

<span data-ttu-id="1e270-103">Przegląd możliwości lokalizowania jest pośrednim krokiem w rozwoju aplikacji gotowej do użycia na całym świecie.</span><span class="sxs-lookup"><span data-stu-id="1e270-103">The localizability review is an intermediate step in the development of a world-ready application.</span></span> <span data-ttu-id="1e270-104">Sprawdza, czy aplikacja globalna jest gotowa do lokalizacji i identyfikuje każdy kod lub wszelkie aspekty interfejsu użytkownika, które wymagają specjalnej obsługi.</span><span class="sxs-lookup"><span data-stu-id="1e270-104">It verifies that a globalized application is ready for localization and identifies any code or any aspects of the user interface that require special handling.</span></span> <span data-ttu-id="1e270-105">Ten krok pomaga również upewnić się, że proces lokalizacji nie spowoduje wprowadzenia żadnych usterek funkcjonalnych do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1e270-105">This step also helps ensure that the localization process will not introduce any functional defects into your application.</span></span> <span data-ttu-id="1e270-106">Po rozpatrzeniu wszystkich problemów zgłoszonych przez przegląd zlokalizowania aplikacja jest gotowa do lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1e270-106">When all the issues raised by the localizability review have been addressed, your application is ready for localization.</span></span> <span data-ttu-id="1e270-107">Jeśli przegląd możliwości zlokalizowania jest dokładny, nie należy modyfikować kodu źródłowego w procesie lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1e270-107">If the localizability review is thorough, you should not have to modify any source code during the localization process.</span></span>

<span data-ttu-id="1e270-108">Przegląd możliwości zlokalizowania składa się z trzech następujących testów:</span><span class="sxs-lookup"><span data-stu-id="1e270-108">The localizability review consists of the following three checks:</span></span>

- [<span data-ttu-id="1e270-109">Czy zaimplementowano zalecenia dotyczące globalizacji?</span><span class="sxs-lookup"><span data-stu-id="1e270-109">Are the globalization recommendations implemented?</span></span>](#global)

- [<span data-ttu-id="1e270-110">Czy funkcje uwzględniające kulturę są prawidłowo obsługiwane?</span><span class="sxs-lookup"><span data-stu-id="1e270-110">Are culture-sensitive features handled correctly?</span></span>](#culture)

- [<span data-ttu-id="1e270-111">Czy aplikacja została przetestowana z danymi międzynarodowymi?</span><span class="sxs-lookup"><span data-stu-id="1e270-111">Have you tested your application with international data?</span></span>](#test)

<a name="global"></a>
## <a name="implement-globalization-recommendations"></a><span data-ttu-id="1e270-112">Implementowanie zaleceń globalizacji</span><span class="sxs-lookup"><span data-stu-id="1e270-112">Implement globalization recommendations</span></span>

<span data-ttu-id="1e270-113">Jeśli aplikacja została zaprojektowana i opracowana z myślą o lokalizacji, a po wykonaniu zaleceń omówionych w artykule [globalizacja](globalization.md) , przegląd możliwości zlokalizowania będzie miał duże gwarancje jakości.</span><span class="sxs-lookup"><span data-stu-id="1e270-113">If you have designed and developed your application with localization in mind, and if you have followed the recommendations discussed in the [Globalization](globalization.md) article, the localizability review will largely be a quality assurance pass.</span></span> <span data-ttu-id="1e270-114">W przeciwnym razie na tym etapie należy przejrzeć i zaimplementować zalecenia dotyczące [globalizacji](globalization.md) oraz usunąć błędy w kodzie źródłowym, które uniemożliwiają lokalizację.</span><span class="sxs-lookup"><span data-stu-id="1e270-114">Otherwise, during this stage you should review and implement the recommendations for [globalization](globalization.md) and fix the errors in source code that prevent localization.</span></span>

<a name="culture"></a>
## <a name="handle-culture-sensitive-features"></a><span data-ttu-id="1e270-115">Obsługa funkcji zależnych od kultury</span><span class="sxs-lookup"><span data-stu-id="1e270-115">Handle culture-sensitive features</span></span>

<span data-ttu-id="1e270-116">Platforma .NET nie zapewnia programistycznej pomocy technicznej w wielu obszarach, które różnią się w zależności od kultury.</span><span class="sxs-lookup"><span data-stu-id="1e270-116">.NET does not provide programmatic support in a number of areas that vary widely by culture.</span></span> <span data-ttu-id="1e270-117">W większości przypadków należy napisać niestandardowy kod do obsługi obszarów funkcji, takich jak następujące:</span><span class="sxs-lookup"><span data-stu-id="1e270-117">In most cases, you have to write custom code to handle feature areas like the following:</span></span>

- <span data-ttu-id="1e270-118">Adresy</span><span class="sxs-lookup"><span data-stu-id="1e270-118">Addresses</span></span>

- <span data-ttu-id="1e270-119">Numery telefonów</span><span class="sxs-lookup"><span data-stu-id="1e270-119">Telephone numbers</span></span>

- <span data-ttu-id="1e270-120">Rozmiary papieru</span><span class="sxs-lookup"><span data-stu-id="1e270-120">Paper sizes</span></span>

- <span data-ttu-id="1e270-121">Jednostki miary używane dla długości, wagi, obszaru, objętości i temperatury</span><span class="sxs-lookup"><span data-stu-id="1e270-121">Units of measure used for lengths, weights, area, volume, and temperatures</span></span>

   <span data-ttu-id="1e270-122">Chociaż platforma .NET nie oferuje wbudowanej obsługi konwersji między jednostkami miary, można użyć <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> właściwości, aby określić, czy określony kraj lub region używa systemu metrycznego, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="1e270-122">Although .NET does not offer built-in support for converting between units of measure, you can use the <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> property to determine whether a particular country or region uses the metric system, as the following example illustrates.</span></span>

   [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
   [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]

<a name="test"></a>
## <a name="test-your-application"></a><span data-ttu-id="1e270-123">Testowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="1e270-123">Test your application</span></span>

<span data-ttu-id="1e270-124">Przed zlokalizowaniem aplikacji należy ją przetestować przy użyciu danych międzynarodowych w międzynarodowych wersjach systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="1e270-124">Before you localize your application, you should test it by using international data on international versions of the operating system.</span></span> <span data-ttu-id="1e270-125">Chociaż większość interfejsu użytkownika nie zostanie zlokalizowana w tym momencie, będzie można wykryć następujące problemy:</span><span class="sxs-lookup"><span data-stu-id="1e270-125">Although most of the user interface will not be localized at this point, you will be able to detect problems such as the following:</span></span>

- <span data-ttu-id="1e270-126">Serializowane dane, które nie są poprawnie deserializacji w różnych wersjach systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="1e270-126">Serialized data that does not deserialize correctly across operating system versions.</span></span>

- <span data-ttu-id="1e270-127">Dane liczbowe, które nie odzwierciedlają Konwencji bieżącej kultury.</span><span class="sxs-lookup"><span data-stu-id="1e270-127">Numeric data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="1e270-128">Na przykład liczby mogą być wyświetlane z nieprawidłowymi separatorami grup, separatorami dziesiętnymi lub symbolami waluty.</span><span class="sxs-lookup"><span data-stu-id="1e270-128">For example, numbers may be displayed with inaccurate group separators, decimal separators, or currency symbols.</span></span>

- <span data-ttu-id="1e270-129">Dane daty i godziny, które nie odzwierciedlają Konwencji bieżącej kultury.</span><span class="sxs-lookup"><span data-stu-id="1e270-129">Date and time data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="1e270-130">Na przykład liczby reprezentujące miesiąc i dzień mogą występować w niewłaściwej kolejności, separatory dat mogą być niepoprawne lub informacje o strefie czasowej mogą być nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="1e270-130">For example, numbers that represent the month and day may appear in the wrong order, date separators may be incorrect, or time zone information may be incorrect.</span></span>

- <span data-ttu-id="1e270-131">Zasoby, których nie można znaleźć, ponieważ nie zidentyfikowano domyślnej kultury dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1e270-131">Resources that cannot be found because you have not identified a default culture for your application.</span></span>

- <span data-ttu-id="1e270-132">Ciągi, które są wyświetlane w nietypowej kolejności dla określonej kultury.</span><span class="sxs-lookup"><span data-stu-id="1e270-132">Strings that are displayed in an unusual order for the specific culture.</span></span>

- <span data-ttu-id="1e270-133">Porównania ciągów lub porównania dla równości, które zwracają nieoczekiwane wyniki.</span><span class="sxs-lookup"><span data-stu-id="1e270-133">String comparisons or comparisons for equality that return unexpected results.</span></span>

<span data-ttu-id="1e270-134">Jeśli zastosowano zalecenia dotyczące globalizacji podczas tworzenia aplikacji, obsługiwane są funkcje zależne od kultury i zidentyfikowane i rozwiązane z problemami z lokalizacją, które powstały podczas testowania, można przejść do następnego kroku, [lokalizacji](localization.md).</span><span class="sxs-lookup"><span data-stu-id="1e270-134">If you've followed the globalization recommendations when developing your application, handled culture-sensitive features correctly, and identified and addressed the localization issues that arose during testing, you can proceed to the next step, [Localization](localization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e270-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1e270-135">See also</span></span>

- [<span data-ttu-id="1e270-136">Globalizacja i lokalizacja</span><span class="sxs-lookup"><span data-stu-id="1e270-136">Globalization and Localization</span></span>](index.md)
- [<span data-ttu-id="1e270-137">Localization</span><span class="sxs-lookup"><span data-stu-id="1e270-137">Localization</span></span>](localization.md)
- [<span data-ttu-id="1e270-138">Globalizacja</span><span class="sxs-lookup"><span data-stu-id="1e270-138">Globalization</span></span>](globalization.md)
- [<span data-ttu-id="1e270-139">Zasoby w aplikacjach klasycznych</span><span class="sxs-lookup"><span data-stu-id="1e270-139">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
