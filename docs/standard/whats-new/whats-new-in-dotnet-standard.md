---
title: Co nowego na platformie .NET Standard
description: Ten artykuł zawiera podsumowanie nowych funkcji i ulepszeń znalezionych w każdej nowej wersji .NET Standard.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 36bd1f9a0dad06d11110b35e9a66f22140cee5ca
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557275"
---
# <a name="whats-new-in-net-standard"></a><span data-ttu-id="4d350-103">Co nowego na platformie .NET Standard</span><span class="sxs-lookup"><span data-stu-id="4d350-103">What's new in .NET Standard</span></span>

<span data-ttu-id="4d350-104">.NET Standard to formalna Specyfikacja, która definiuje zestaw interfejsów API, które muszą być dostępne w implementacjach platformy .NET, które są zgodne z tą wersją Standard.</span><span class="sxs-lookup"><span data-stu-id="4d350-104">.NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="4d350-105">.NET Standard jest przeznaczona dla deweloperów biblioteki.</span><span class="sxs-lookup"><span data-stu-id="4d350-105">.NET Standard is targeted at library developers.</span></span> <span data-ttu-id="4d350-106">Biblioteka, która jest przeznaczona dla wersji .NET Standard, może być używana w ramach implementacji .NET Framework, .NET Core lub Xamarin, która obsługuje tę wersję Standard.</span><span class="sxs-lookup"><span data-stu-id="4d350-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="4d350-107">.NET Standard jest dołączany do zestaw .NET Core SDK, a także z programem Visual Studio podczas wybierania obciążenia .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4d350-107">.NET Standard is included with the .NET Core SDK, as well as with Visual Studio when you select the .NET Core workload.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="4d350-108">Obsługiwane implementacje platformy .NET</span><span class="sxs-lookup"><span data-stu-id="4d350-108">Supported .NET implementations</span></span>

<span data-ttu-id="4d350-109">.NET Standard 2,0 jest obsługiwana przez następujące implementacje .NET:</span><span class="sxs-lookup"><span data-stu-id="4d350-109">.NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="4d350-110">.NET Core 2,0 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="4d350-110">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="4d350-111">.NET Framework 4.6.1 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="4d350-111">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="4d350-112">Mono 5,4 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="4d350-112">Mono 5.4 or later</span></span>
- <span data-ttu-id="4d350-113">Platforma Xamarin. iOS 10,14 lub nowsza</span><span class="sxs-lookup"><span data-stu-id="4d350-113">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="4d350-114">Platforma Xamarin. Mac 3,8 lub nowsza</span><span class="sxs-lookup"><span data-stu-id="4d350-114">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="4d350-115">Platforma Xamarin. Android 8,0 lub nowsza</span><span class="sxs-lookup"><span data-stu-id="4d350-115">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="4d350-116">Platforma uniwersalna systemu Windows 10.0.16299 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="4d350-116">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-net-standard-20"></a><span data-ttu-id="4d350-117">Co nowego w .NET Standard 2,0</span><span class="sxs-lookup"><span data-stu-id="4d350-117">What's new in .NET Standard 2.0</span></span>

<span data-ttu-id="4d350-118">.NET Standard 2,0 zawiera następujące nowe funkcje:</span><span class="sxs-lookup"><span data-stu-id="4d350-118">.NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="4d350-119">Zestaw interfejsów API o szerokim rozszerzeniu</span><span class="sxs-lookup"><span data-stu-id="4d350-119">A vastly expanded set of APIs</span></span>

<span data-ttu-id="4d350-120">W wersji 1,6, .NET Standard obejmowały niewielki podzbiór interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="4d350-120">Through version 1.6, .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="4d350-121">Wśród tych wykluczonych było wiele interfejsów API, które były często używane w .NET Framework lub Xamarin.</span><span class="sxs-lookup"><span data-stu-id="4d350-121">Among those excluded were many APIs that were commonly used in .NET Framework or Xamarin.</span></span> <span data-ttu-id="4d350-122">To komplikuje programowanie, ponieważ wymaga, aby deweloperzy znalazły odpowiednie zamienniki dla znanych interfejsów API podczas opracowywania aplikacji i bibliotek przeznaczonych dla wielu implementacji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="4d350-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="4d350-123">.NET Standard 2,0 dotyczy tego ograniczenia przez dodanie ponad 20 000 więcej interfejsów API niż w .NET Standard 1,6, poprzedniej wersji Standard.</span><span class="sxs-lookup"><span data-stu-id="4d350-123">.NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="4d350-124">Aby uzyskać listę interfejsów API, które zostały dodane do .NET Standard 2,0, zobacz [.NET Standard 2,0 vs 1,6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="4d350-124">For a list of the APIs that have been added to .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="4d350-125">Niektóre dodatki do <xref:System> przestrzeni nazw w .NET Standard 2,0 obejmują:</span><span class="sxs-lookup"><span data-stu-id="4d350-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="4d350-126">Obsługa <xref:System.AppDomain> klasy.</span><span class="sxs-lookup"><span data-stu-id="4d350-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="4d350-127">Lepsza obsługa pracy z tablicami z dodatkowych elementów członkowskich w <xref:System.Array> klasie.</span><span class="sxs-lookup"><span data-stu-id="4d350-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="4d350-128">Lepsza obsługa pracy z atrybutami z dodatkowych elementów członkowskich w <xref:System.Attribute> klasie.</span><span class="sxs-lookup"><span data-stu-id="4d350-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="4d350-129">Lepsza obsługa kalendarza i dodatkowe opcje formatowania dla <xref:System.DateTime> wartości.</span><span class="sxs-lookup"><span data-stu-id="4d350-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="4d350-130">Dodatkowe <xref:System.Decimal> funkcje zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="4d350-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="4d350-131">Dodatkowe funkcje w <xref:System.Environment> klasie.</span><span class="sxs-lookup"><span data-stu-id="4d350-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="4d350-132">Rozszerzona kontrola nad modułem wyrzucania elementów bezużytecznych za pośrednictwem <xref:System.GC> klasy.</span><span class="sxs-lookup"><span data-stu-id="4d350-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="4d350-133">Ulepszona obsługa porównywania ciągów, wyliczania i normalizacji w <xref:System.String> klasie.</span><span class="sxs-lookup"><span data-stu-id="4d350-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="4d350-134">Obsługa zmian czasu letnich i czasów przejścia w <xref:System.TimeZoneInfo.AdjustmentRule> <xref:System.TimeZoneInfo.TransitionTime> klasach i.</span><span class="sxs-lookup"><span data-stu-id="4d350-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="4d350-135">Znacznie ulepszone funkcje w <xref:System.Type> klasie.</span><span class="sxs-lookup"><span data-stu-id="4d350-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="4d350-136">Lepsza obsługa deserializacji obiektów wyjątków przez dodanie konstruktora wyjątków z <xref:System.Runtime.Serialization.SerializationInfo> <xref:System.Runtime.Serialization.StreamingContext> parametrami i.</span><span class="sxs-lookup"><span data-stu-id="4d350-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="4d350-137">Obsługa bibliotek .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4d350-137">Support for .NET Framework libraries</span></span>

<span data-ttu-id="4d350-138">Wiele obiektów docelowych bibliotek .NET Framework, a nie .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4d350-138">Many libraries target .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="4d350-139">Większość wywołań w tych bibliotekach obejmuje jednak interfejsy API, które znajdują się w .NET Standard 2,0.</span><span class="sxs-lookup"><span data-stu-id="4d350-139">However, most of the calls in those libraries are to APIs that are included in .NET Standard 2.0.</span></span> <span data-ttu-id="4d350-140">Począwszy od .NET Standard 2,0, można uzyskać dostęp do bibliotek .NET Framework z biblioteki .NET Standard za pomocą [podkładki zgodności](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="4d350-140">Starting with .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span></span> <span data-ttu-id="4d350-141">Ta warstwa zgodności jest niewidoczna dla deweloperów; nie trzeba wykonywać żadnych czynności, aby korzystać z bibliotek .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d350-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="4d350-142">Jedynym wymaganiem jest, że interfejsy API wywoływane przez bibliotekę klas .NET Framework muszą być dołączone do .NET Standard 2,0.</span><span class="sxs-lookup"><span data-stu-id="4d350-142">The single requirement is that the APIs called by the .NET Framework class library must be included in .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="4d350-143">Obsługa Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d350-143">Support for Visual Basic</span></span>

<span data-ttu-id="4d350-144">Teraz można opracowywać biblioteki .NET Standard w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4d350-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="4d350-145">Programy Visual Studio 2019 i Visual Studio 2017 w wersji 15,3 lub nowszej z zainstalowanym obciążeniem programu .NET Core zawierają szablon biblioteki klas .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4d350-145">Visual Studio 2019 and Visual Studio 2017 version 15.3 or later with the .NET Core workload installed include a .NET Standard Class Library template.</span></span> <span data-ttu-id="4d350-146">Dla Visual Basic deweloperów, którzy korzystają z innych narzędzi programistycznych i środowisk, można użyć polecenia [dotnet New](../../core/tools/dotnet-new.md) , aby utworzyć projekt biblioteki .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4d350-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="4d350-147">Aby uzyskać więcej informacji, zobacz [Obsługa narzędzi dla bibliotek .NET Standard](#tooling-support-for-net-standard-libraries).</span><span class="sxs-lookup"><span data-stu-id="4d350-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="4d350-148">Obsługa narzędzi dla bibliotek .NET Standard</span><span class="sxs-lookup"><span data-stu-id="4d350-148">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="4d350-149">W przypadku wersji programu .NET Core 2,0 i .NET Standard 2,0 zarówno program Visual Studio 2017, jak i [interfejs wiersza polecenia platformy .NET Core](../../core/tools/index.md) obejmują narzędzia obsługujące tworzenie bibliotek .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4d350-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core CLI](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="4d350-150">W przypadku instalowania programu Visual Studio z użyciem obciążenia **międzyplatformowego platformy .NET Core** można utworzyć projekt biblioteki .NET Standard 2,0 przy użyciu szablonu projektu, tak jak pokazano na poniższej ilustracji:</span><span class="sxs-lookup"><span data-stu-id="4d350-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="4d350-151">C#</span><span class="sxs-lookup"><span data-stu-id="4d350-151">C#</span></span>](#tab/csharp)

![Dodaj nowy projekt biblioteki .NET Standard](./media/std-project-cs.png)

<span data-ttu-id="4d350-153">Jeśli używasz interfejs wiersza polecenia platformy .NET Core, następujące polecenie [dotnet New](../../core/tools/dotnet-new.md) tworzy projekt biblioteki klas, który jest przeznaczony dla .NET Standard 2,0:</span><span class="sxs-lookup"><span data-stu-id="4d350-153">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib
```

# <a name="visual-basic"></a>[<span data-ttu-id="4d350-154">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d350-154">Visual Basic</span></span>](#tab/vb)

![Dodaj nowy projekt biblioteki .NET Standard](./media/std-project-vb.png)

<span data-ttu-id="4d350-156">Jeśli używasz interfejs wiersza polecenia platformy .NET Core, następujące polecenie [dotnet New](../../core/tools/dotnet-new.md) tworzy projekt biblioteki klas, który jest przeznaczony dla .NET Standard 2,0:</span><span class="sxs-lookup"><span data-stu-id="4d350-156">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="4d350-157">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4d350-157">See also</span></span>

- [<span data-ttu-id="4d350-158">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="4d350-158">.NET Standard</span></span>](../net-standard.md)
- [<span data-ttu-id="4d350-159">Wprowadzenie .NET Standard</span><span class="sxs-lookup"><span data-stu-id="4d350-159">Introducing .NET Standard</span></span>](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)
- [<span data-ttu-id="4d350-160">Pobierz zestaw .NET SDK</span><span class="sxs-lookup"><span data-stu-id="4d350-160">Download the .NET SDK</span></span>](https://dotnet.microsoft.com/download)
