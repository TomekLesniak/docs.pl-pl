---
title: Przegląd bibliotek środowiska uruchomieniowego
description: Dowiedz się, co znajduje się w sekcji biblioteki środowiska uruchomieniowego spisu treści.
author: tdykstra
ms.date: 11/10/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 64bbc13f8c3df3c0c9a02fee4560c9ee3fcc5d62
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507612"
---
# <a name="runtime-libraries-overview"></a><span data-ttu-id="11aa2-103">Przegląd bibliotek środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="11aa2-103">Runtime libraries overview</span></span>

<span data-ttu-id="11aa2-104">[Środowisko uruchomieniowe platformy .NET](../core/introduction.md#sdk-and-runtimes), które jest zainstalowane na maszynie do użytku przez [aplikacje zależne od platformy](../core/introduction.md#deployment-models), ma standardowy zestaw klas rozległych:</span><span class="sxs-lookup"><span data-stu-id="11aa2-104">The [.NET runtime](../core/introduction.md#sdk-and-runtimes), which is installed on a machine for use by [framework-dependent apps](../core/introduction.md#deployment-models), has an expansive standard set of class libraries:</span></span>

* <span data-ttu-id="11aa2-105">Zestaw podstawowy, uwzględniony w czasie wykonywania i znany jako [biblioteki klas bazowych (BCL)](glossary.md#bcl).</span><span class="sxs-lookup"><span data-stu-id="11aa2-105">The core set, included in the runtime and known as the [base class libraries (BCL)](glossary.md#bcl).</span></span>
* <span data-ttu-id="11aa2-106">Kompletny zestaw obejmujący środowisko uruchomieniowe i znane jako biblioteki [środowiska uruchomieniowego](glossary.md#runtime) lub [biblioteki struktury](glossary.md#framework).</span><span class="sxs-lookup"><span data-stu-id="11aa2-106">The complete set, included in the runtime and known as the [runtime libraries](glossary.md#runtime) or [framework libraries](glossary.md#framework).</span></span>
* <span data-ttu-id="11aa2-107">Rozszerzenia bibliotek środowiska uruchomieniowego, które znajdują się w pakietach NuGet.</span><span class="sxs-lookup"><span data-stu-id="11aa2-107">Extensions to the runtime libraries, provided in NuGet packages.</span></span>

<span data-ttu-id="11aa2-108">Te biblioteki zapewniają implementacje dla wielu typów ogólnych i specyficznych dla aplikacji, algorytmów i funkcji narzędzi.</span><span class="sxs-lookup"><span data-stu-id="11aa2-108">These libraries provide implementations for many general and app-specific types, algorithms, and utility functionality.</span></span>

## <a name="base-class-libraries"></a><span data-ttu-id="11aa2-109">Biblioteki klas bazowych</span><span class="sxs-lookup"><span data-stu-id="11aa2-109">Base class libraries</span></span>

<span data-ttu-id="11aa2-110">BCL udostępnia podstawowe typy i funkcje narzędziowe, a także jest podstawą wszystkich innych bibliotek klas platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="11aa2-110">The BCL provides the foundational types and utility functionality and is the base of all other .NET class libraries.</span></span> <span data-ttu-id="11aa2-111">Przykładem jest <xref:System.String?displayProperty=nameWithType> Klasa, która udostępnia interfejsy API do pracy z ciągami.</span><span class="sxs-lookup"><span data-stu-id="11aa2-111">An example is the <xref:System.String?displayProperty=nameWithType> class, which provides APIs for working with strings.</span></span>

## <a name="runtime-libraries"></a><span data-ttu-id="11aa2-112">Biblioteki środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="11aa2-112">Runtime libraries</span></span>

<span data-ttu-id="11aa2-113">Znane również jako biblioteki środowiskowe, biblioteki środowiska uruchomieniowego kompilują się w BCL, aby zapewnić interfejsy API narzędzi dla typowych zadań.</span><span class="sxs-lookup"><span data-stu-id="11aa2-113">Also known as the framework libraries, the runtime libraries build on the BCL to provide utility APIs for common tasks.</span></span> <span data-ttu-id="11aa2-114">Przykładem są [biblioteki serializacji](serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="11aa2-114">An example is the [serialization libraries](serialization/index.md).</span></span>

## <a name="extensions-to-the-runtime-libraries"></a><span data-ttu-id="11aa2-115">Rozszerzenia bibliotek środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="11aa2-115">Extensions to the runtime libraries</span></span>

<span data-ttu-id="11aa2-116">Niektóre biblioteki środowiska uruchomieniowego są udostępniane w pakietach NuGet, a nie wbudowane w środowisko uruchomieniowe, które jest instalowane dla aplikacji zależnych od platformy.</span><span class="sxs-lookup"><span data-stu-id="11aa2-116">Some of the runtime libraries are provided in NuGet packages rather than built-in to the runtime that is installed for framework-dependent apps.</span></span> <span data-ttu-id="11aa2-117">Przykładem jest [interfejs API rejestrowania programu .NET](../core/extensions/logging.md).</span><span class="sxs-lookup"><span data-stu-id="11aa2-117">An example is the [.NET Logging API](../core/extensions/logging.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="11aa2-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="11aa2-118">See also</span></span>

* [<span data-ttu-id="11aa2-119">Wprowadzenie do platformy .NET</span><span class="sxs-lookup"><span data-stu-id="11aa2-119">Introduction to .NET</span></span>](../core/introduction.md)
* [<span data-ttu-id="11aa2-120">Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="11aa2-120">Install .NET SDK or runtime</span></span>](../core/install/index.yml)
* [<span data-ttu-id="11aa2-121">Wybierz zainstalowany zestaw .NET SDK lub wersję środowiska uruchomieniowego do użycia</span><span class="sxs-lookup"><span data-stu-id="11aa2-121">Select the installed .NET SDK or runtime version to use</span></span>](../core/versions/selection.md)
* [<span data-ttu-id="11aa2-122">Publikowanie aplikacji zależnych od platformy</span><span class="sxs-lookup"><span data-stu-id="11aa2-122">Publish framework-dependent apps</span></span>](../core/deploying/index.md#publish-framework-dependent)
