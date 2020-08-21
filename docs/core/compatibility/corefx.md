---
title: Podstawowe zmiany w bibliotece klas podstawowych
description: Wyświetla istotne zmiany w podstawowych bibliotekach programu .NET.
ms.date: 07/27/2020
ms.openlocfilehash: e0ebc054e0abccfe934b505a727060653fe313cd
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720209"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="2e8f6-103">Podstawowe zmiany w bibliotekach .NET</span><span class="sxs-lookup"><span data-stu-id="2e8f6-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="2e8f6-104">Podstawowe biblioteki .NET zapewniają pierwotne i inne typy ogólne używane przez platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e8f6-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="2e8f6-105">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="2e8f6-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="2e8f6-106">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="2e8f6-106">Breaking change</span></span> | <span data-ttu-id="2e8f6-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="2e8f6-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="2e8f6-108">Nazwy parametrów zostały zmienione w zestawach odwołań</span><span class="sxs-lookup"><span data-stu-id="2e8f6-108">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="2e8f6-109">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-109">5.0</span></span> |
| [<span data-ttu-id="2e8f6-110">Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="2e8f6-110">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="2e8f6-111">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-111">5.0</span></span> |
| [<span data-ttu-id="2e8f6-112">Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="2e8f6-112">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="2e8f6-113">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-113">5.0</span></span> |
| [<span data-ttu-id="2e8f6-114">Środowisko. OSVersion zwraca poprawną wersję systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="2e8f6-114">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="2e8f6-115">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-115">5.0</span></span> |
| [<span data-ttu-id="2e8f6-116">Złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł</span><span class="sxs-lookup"><span data-stu-id="2e8f6-116">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="2e8f6-117">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-117">5.0</span></span> |
| [<span data-ttu-id="2e8f6-118">IntPtr i UIntPtr Implementuj IFormattable</span><span class="sxs-lookup"><span data-stu-id="2e8f6-118">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="2e8f6-119">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-119">5.0</span></span> |
| [<span data-ttu-id="2e8f6-120">PrincipalPermissionAttribute jest przestarzały jako błąd</span><span class="sxs-lookup"><span data-stu-id="2e8f6-120">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="2e8f6-121">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-121">5.0</span></span> |
| [<span data-ttu-id="2e8f6-122">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2e8f6-122">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="2e8f6-123">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-123">5.0</span></span> |
| [<span data-ttu-id="2e8f6-124">Ścieżki kodu UTF-7 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="2e8f6-124">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="2e8f6-125">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-125">5.0</span></span> |
| [<span data-ttu-id="2e8f6-126">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="2e8f6-126">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="2e8f6-127">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-127">5.0</span></span> |
| [<span data-ttu-id="2e8f6-128">ActivityIdFormat domyślny to W3C</span><span class="sxs-lookup"><span data-stu-id="2e8f6-128">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="2e8f6-129">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-129">5.0</span></span> |
| [<span data-ttu-id="2e8f6-130">Zmiana zachowania dla Vector2. Lerp i Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="2e8f6-130">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="2e8f6-131">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-131">5.0</span></span> |
| [<span data-ttu-id="2e8f6-132">Metody SSE i SSE2 CompareGreaterThan prawidłowo obsługują dane wejściowe NaN</span><span class="sxs-lookup"><span data-stu-id="2e8f6-132">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="2e8f6-133">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-133">5.0</span></span> |
| [<span data-ttu-id="2e8f6-134">Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje</span><span class="sxs-lookup"><span data-stu-id="2e8f6-134">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="2e8f6-135">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-135">5.0</span></span> |
| [<span data-ttu-id="2e8f6-136">Usunięto pakiet Microsoft. DotNet. PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="2e8f6-136">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="2e8f6-137">5.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-137">5.0</span></span> |
| [<span data-ttu-id="2e8f6-138">Interfejsy API służące do raportowania wersji teraz produktu i nie wersji</span><span class="sxs-lookup"><span data-stu-id="2e8f6-138">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="2e8f6-139">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-139">3.0</span></span> |
| [<span data-ttu-id="2e8f6-140">Niestandardowe wystąpienia EncoderFallbackBuffer nie mogą podlegać rekursywnie</span><span class="sxs-lookup"><span data-stu-id="2e8f6-140">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="2e8f6-141">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-141">3.0</span></span> |
| [<span data-ttu-id="2e8f6-142">Zmiany zachowań formatowania zmiennoprzecinkowego i analizowania</span><span class="sxs-lookup"><span data-stu-id="2e8f6-142">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="2e8f6-143">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-143">3.0</span></span> |
| [<span data-ttu-id="2e8f6-144">Operacje analizowania zmiennoprzecinkowe nie będą już kończyć się niepowodzeniem lub nie generują wyjątku overflow</span><span class="sxs-lookup"><span data-stu-id="2e8f6-144">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="2e8f6-145">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-145">3.0</span></span> |
| [<span data-ttu-id="2e8f6-146">InvalidAsynchronousStateException — przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="2e8f6-146">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="2e8f6-147">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-147">3.0</span></span> |
| [<span data-ttu-id="2e8f6-148">Zastępowanie źle sformułowanych sekwencji bajtów w formacie UTF-8 następuje po wskazówkach dotyczących standardu Unicode</span><span class="sxs-lookup"><span data-stu-id="2e8f6-148">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="2e8f6-149">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-149">3.0</span></span> |
| [<span data-ttu-id="2e8f6-150">TypeDescriptionProviderAttribute przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="2e8f6-150">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="2e8f6-151">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-151">3.0</span></span> |
| [<span data-ttu-id="2e8f6-152">Element ZipArchiveEntry nie obsługuje już archiwów z niespójnymi rozmiarami wpisów</span><span class="sxs-lookup"><span data-stu-id="2e8f6-152">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="2e8f6-153">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-153">3.0</span></span> |
| [<span data-ttu-id="2e8f6-154">Element FieldInfo. SetValue zgłasza wyjątek dla pól static, tylko init</span><span class="sxs-lookup"><span data-stu-id="2e8f6-154">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="2e8f6-155">3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-155">3.0</span></span> |
| [<span data-ttu-id="2e8f6-156">Pola prywatne dodane do wbudowanych typów struktur</span><span class="sxs-lookup"><span data-stu-id="2e8f6-156">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="2e8f6-157">2.1</span><span class="sxs-lookup"><span data-stu-id="2e8f6-157">2.1</span></span> |
| [<span data-ttu-id="2e8f6-158">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="2e8f6-158">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="2e8f6-159">2.1</span><span class="sxs-lookup"><span data-stu-id="2e8f6-159">2.1</span></span> |
| [<span data-ttu-id="2e8f6-160">Wersje OpenSSL na macOS</span><span class="sxs-lookup"><span data-stu-id="2e8f6-160">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="2e8f6-161">2.1</span><span class="sxs-lookup"><span data-stu-id="2e8f6-161">2.1</span></span> |
| [<span data-ttu-id="2e8f6-162">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="2e8f6-162">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="2e8f6-163">1.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-163">1.0</span></span> |
| [<span data-ttu-id="2e8f6-164">Obsługa wyjątków uszkodzonego stanu procesu nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="2e8f6-164">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="2e8f6-165">1.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-165">1.0</span></span> |
| [<span data-ttu-id="2e8f6-166">Właściwości UriBuilder nie dołączają już znaków wiodących</span><span class="sxs-lookup"><span data-stu-id="2e8f6-166">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="2e8f6-167">1.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-167">1.0</span></span> |
| [<span data-ttu-id="2e8f6-168">Proces. element StartInfo zgłasza InvalidOperationException dla procesów, które nie zostały uruchomione</span><span class="sxs-lookup"><span data-stu-id="2e8f6-168">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="2e8f6-169">1.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-169">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="2e8f6-170">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-170">.NET 5.0</span></span>

[!INCLUDE [reference-assembly-parameter-names](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names.md)]

***

[!INCLUDE [non-ascii-chars-in-uri-parsed-correctly](../../../includes/core-changes/corefx/5.0/non-ascii-chars-in-uri-parsed-correctly.md)]

***

[!INCLUDE [unc-path-recognition-unix](../../../includes/core-changes/corefx/5.0/unc-path-recognition-unix.md)]

***

[!INCLUDE [environment-osversion-returns-correct-version](../../../includes/core-changes/corefx/5.0/environment-osversion-returns-correct-version.md)]

***

[!INCLUDE [orderby-firstordefault-complexity-increase](../../../includes/core-changes/corefx/5.0/orderby-firstordefault-complexity-increase.md)]

***

[!INCLUDE [intptr-uintptr-implement-iformattable](../../../includes/core-changes/corefx/5.0/intptr-uintptr-implement-iformattable.md)]

***

[!INCLUDE [principalpermissionattribute-obsolete](../../../includes/core-changes/corefx/5.0/principalpermissionattribute-obsolete.md)]

***

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE [utf-7-code-paths-obsolete](../../../includes/core-changes/corefx/5.0/utf-7-code-paths-obsolete.md)]

***

[!INCLUDE [vectort-throws-notsupportedexception](../../../includes/core-changes/corefx/5.0/vectort-throws-notsupportedexception.md)]

***

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

***

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

***

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="2e8f6-171">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-171">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="2e8f6-172">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2e8f6-172">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="2e8f6-173">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="2e8f6-173">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
