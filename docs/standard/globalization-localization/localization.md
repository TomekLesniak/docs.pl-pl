---
title: Lokalizacja
ms.date: 03/30/2017
helpviewer_keywords:
- culture, localization
- application development [.NET], localization
- globalization [.NET], localization
- code blocks
- international applications [.NET], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 5d47d002c714ea80b6f94c810f2dca726c273134
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829833"
---
# <a name="localization"></a><span data-ttu-id="b8a25-102">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="b8a25-102">Localization</span></span>

<span data-ttu-id="b8a25-103">Lokalizacja jest procesem tłumaczenia zasobów aplikacji w zlokalizowane wersje dla każdej kultury obsługiwanej przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="b8a25-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="b8a25-104">Krok lokalizacji należy przejść dopiero po ukończeniu kroku [Przegląd możliwości zlokalizowania](localizability-review.md) , aby sprawdzić, czy aplikacja globalna jest gotowa do lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="b8a25-104">You should proceed to the localization step only after completing the [Localizability Review](localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>

<span data-ttu-id="b8a25-105">Aplikacja, która jest gotowa do lokalizacji, jest oddzielona na dwa bloki koncepcyjne: blok zawierający wszystkie elementy interfejsu użytkownika i blok zawierający kod wykonywalny.</span><span class="sxs-lookup"><span data-stu-id="b8a25-105">An application that is ready for localization is separated into two conceptual blocks: a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="b8a25-106">Blok interfejsu użytkownika zawiera tylko lokalizowalnych elementów interfejsu użytkownika, takich jak ciągi, komunikaty o błędach, okna dialogowe, menu, osadzone zasoby obiektów i tak dalej dla kultury neutralnej.</span><span class="sxs-lookup"><span data-stu-id="b8a25-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="b8a25-107">Blok kodu zawiera tylko kod aplikacji, który ma być używany przez wszystkie obsługiwane kultury.</span><span class="sxs-lookup"><span data-stu-id="b8a25-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="b8a25-108">Środowisko uruchomieniowe języka wspólnego obsługuje model zasobów zestawu satelickiego, który oddziela kod wykonywalny aplikacji od jego zasobów.</span><span class="sxs-lookup"><span data-stu-id="b8a25-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="b8a25-109">Aby uzyskać więcej informacji na temat implementowania tego modelu, zobacz [zasoby w programie .NET](../../framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="b8a25-109">For more information about implementing this model, see [Resources in .NET](../../framework/resources/index.md).</span></span>

<span data-ttu-id="b8a25-110">Dla każdej zlokalizowanej wersji aplikacji Dodaj nowy zestaw satelicki zawierający zlokalizowany blok interfejsu użytkownika przetłumaczony do odpowiedniego języka dla kultury docelowej.</span><span class="sxs-lookup"><span data-stu-id="b8a25-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="b8a25-111">Blok kodu dla wszystkich kultur powinien pozostać taki sam.</span><span class="sxs-lookup"><span data-stu-id="b8a25-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="b8a25-112">Kombinacja zlokalizowanej wersji bloku interfejsu użytkownika z blokiem kodu tworzy zlokalizowaną wersję aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b8a25-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>

<span data-ttu-id="b8a25-113">Zestaw Windows Software Development Kit (SDK) udostępnia Edytor zasobów Windows Forms (Winres.exe), który umożliwia szybkie lokalizowanie Windows Forms dla kultur docelowych.</span><span class="sxs-lookup"><span data-stu-id="b8a25-113">The Windows Software Development Kit (SDK) supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="b8a25-114">Aby uzyskać informacje dotyczące korzystania z tego narzędzia, zobacz [Winres.exe (Edytor zasobów Windows Forms)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b8a25-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8a25-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b8a25-115">See also</span></span>

- [<span data-ttu-id="b8a25-116">Globalizacja i lokalizacja</span><span class="sxs-lookup"><span data-stu-id="b8a25-116">Globalization and Localization</span></span>](index.md)
- [<span data-ttu-id="b8a25-117">Przegląd możliwości zlokalizowania</span><span class="sxs-lookup"><span data-stu-id="b8a25-117">Localizability Review</span></span>](localizability-review.md)
- [<span data-ttu-id="b8a25-118">Globalizacja</span><span class="sxs-lookup"><span data-stu-id="b8a25-118">Globalization</span></span>](globalization.md)
- [<span data-ttu-id="b8a25-119">Zasoby w aplikacjach klasycznych</span><span class="sxs-lookup"><span data-stu-id="b8a25-119">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
