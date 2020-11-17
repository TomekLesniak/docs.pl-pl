---
title: Przegląd bibliotek środowiska uruchomieniowego
description: Dowiedz się, co znajduje się w sekcji biblioteki środowiska uruchomieniowego spisu treści.
author: tdykstra
ms.date: 11/12/2020
ms.openlocfilehash: 5a8f888e1778553e2968277738cfef5134f11589
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687895"
---
# <a name="runtime-libraries-overview"></a><span data-ttu-id="c8d1a-103">Przegląd bibliotek środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="c8d1a-103">Runtime libraries overview</span></span>

<span data-ttu-id="c8d1a-104">[Środowisko uruchomieniowe platformy .NET](../core/introduction.md#sdk-and-runtimes), które jest zainstalowane na maszynie do użytku [przez aplikacje zależne od platformy](../core/introduction.md#deployment-models), ma standardowy zestaw klas rozległych, znane jako [biblioteki środowiska uruchomieniowego](glossary.md#runtime), [biblioteki struktury](glossary.md#framework-libraries)lub [Biblioteka klas bazowych (BCL)](glossary.md#bcl).</span><span class="sxs-lookup"><span data-stu-id="c8d1a-104">The [.NET runtime](../core/introduction.md#sdk-and-runtimes), which is installed on a machine for use by [framework-dependent apps](../core/introduction.md#deployment-models), has an expansive standard set of class libraries, known as [runtime libraries](glossary.md#runtime), [framework libraries](glossary.md#framework-libraries), or the [base class library (BCL)](glossary.md#bcl).</span></span> <span data-ttu-id="c8d1a-105">Ponadto istnieją rozszerzenia bibliotek środowiska uruchomieniowego udostępniane w pakietach NuGet.</span><span class="sxs-lookup"><span data-stu-id="c8d1a-105">In addition, there are extensions to the runtime libraries, provided in NuGet packages.</span></span>

<span data-ttu-id="c8d1a-106">Te biblioteki zapewniają implementacje dla wielu typów ogólnych i specyficznych dla aplikacji, algorytmów i funkcji narzędzi.</span><span class="sxs-lookup"><span data-stu-id="c8d1a-106">These libraries provide implementations for many general and app-specific types, algorithms, and utility functionality.</span></span>

## <a name="runtime-libraries"></a><span data-ttu-id="c8d1a-107">Biblioteki środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="c8d1a-107">Runtime libraries</span></span>

<span data-ttu-id="c8d1a-108">Te biblioteki zapewniają podstawowe typy i funkcje narzędziowe, a stanowią podstawę wszystkich innych bibliotek klas platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c8d1a-108">These libraries provide the foundational types and utility functionality and are the base of all other .NET class libraries.</span></span> <span data-ttu-id="c8d1a-109">Przykładem jest <xref:System.String?displayProperty=nameWithType> Klasa, która udostępnia interfejsy API do pracy z ciągami.</span><span class="sxs-lookup"><span data-stu-id="c8d1a-109">An example is the <xref:System.String?displayProperty=nameWithType> class, which provides APIs for working with strings.</span></span> <span data-ttu-id="c8d1a-110">Innym przykładem są [biblioteki serializacji](serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="c8d1a-110">Another example is the [serialization libraries](serialization/index.md).</span></span>

## <a name="extensions-to-the-runtime-libraries"></a><span data-ttu-id="c8d1a-111">Rozszerzenia bibliotek środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="c8d1a-111">Extensions to the runtime libraries</span></span>

<span data-ttu-id="c8d1a-112">Niektóre biblioteki są udostępniane w pakietach NuGet, a nie dołączone do [udostępnionej struktury](glossary.md#shared-framework)środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c8d1a-112">Some libraries are provided in NuGet packages rather than included in the runtime's [shared framework](glossary.md#shared-framework).</span></span> <span data-ttu-id="c8d1a-113">Przykład:</span><span class="sxs-lookup"><span data-stu-id="c8d1a-113">For example:</span></span>

* [<span data-ttu-id="c8d1a-114">Rejestrowanie</span><span class="sxs-lookup"><span data-stu-id="c8d1a-114">Logging</span></span>](../core/extensions/logging.md)
* [<span data-ttu-id="c8d1a-115">Wstrzykiwanie zależności</span><span class="sxs-lookup"><span data-stu-id="c8d1a-115">Dependency injection</span></span>](../core/extensions/dependency-injection.md)
* [<span data-ttu-id="c8d1a-116">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="c8d1a-116">Configuration</span></span>](../core/extensions/configuration.md)

## <a name="see-also"></a><span data-ttu-id="c8d1a-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c8d1a-117">See also</span></span>

* [<span data-ttu-id="c8d1a-118">Wprowadzenie do platformy .NET</span><span class="sxs-lookup"><span data-stu-id="c8d1a-118">Introduction to .NET</span></span>](../core/introduction.md)
* [<span data-ttu-id="c8d1a-119">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="c8d1a-119">Install .NET SDK or runtime</span></span>](../core/install/index.yml)
* [<span data-ttu-id="c8d1a-120">Wybierz zainstalowany zestaw .NET SDK lub wersję środowiska uruchomieniowego do użycia</span><span class="sxs-lookup"><span data-stu-id="c8d1a-120">Select the installed .NET SDK or runtime version to use</span></span>](../core/versions/selection.md)
* [<span data-ttu-id="c8d1a-121">Publikowanie aplikacji zależnych od platformy</span><span class="sxs-lookup"><span data-stu-id="c8d1a-121">Publish framework-dependent apps</span></span>](../core/deploying/index.md#publish-framework-dependent)
