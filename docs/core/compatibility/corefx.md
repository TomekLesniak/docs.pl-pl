---
title: Podstawowe zmiany w bibliotece klas podstawowych
description: Wyświetla istotne zmiany w podstawowych bibliotekach programu .NET.
ms.date: 07/27/2020
ms.openlocfilehash: c3207ac7630d794f77c793cc6d1d52e158c0c084
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738827"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="96d50-103">Podstawowe zmiany w bibliotekach .NET</span><span class="sxs-lookup"><span data-stu-id="96d50-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="96d50-104">Podstawowe biblioteki .NET zapewniają pierwotne i inne typy ogólne używane przez platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="96d50-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="96d50-105">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="96d50-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="96d50-106">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="96d50-106">Breaking change</span></span> | <span data-ttu-id="96d50-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="96d50-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="96d50-108">Nazwy parametrów zostały zmienione w wersji RC1</span><span class="sxs-lookup"><span data-stu-id="96d50-108">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="96d50-109">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-109">5.0</span></span> |
| [<span data-ttu-id="96d50-110">Atrybuty OSPlatform zostały zmienione lub usunięte</span><span class="sxs-lookup"><span data-stu-id="96d50-110">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="96d50-111">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-111">5.0</span></span> |
| [<span data-ttu-id="96d50-112">Wątek. Abort jest przestarzały</span><span class="sxs-lookup"><span data-stu-id="96d50-112">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="96d50-113">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-113">5.0</span></span> |
| [<span data-ttu-id="96d50-114">Przestarzałe właściwości w ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="96d50-114">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="96d50-115">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-115">5.0</span></span> |
| [<span data-ttu-id="96d50-116">Wewnętrzne testy nieobsługiwane sprzętowo mogą się różnić w zależności od typów zagnieżdżonych</span><span class="sxs-lookup"><span data-stu-id="96d50-116">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="96d50-117">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-117">5.0</span></span> |
| [<span data-ttu-id="96d50-118">Nazwy parametrów zostały zmienione w zestawach odwołań</span><span class="sxs-lookup"><span data-stu-id="96d50-118">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="96d50-119">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-119">5.0</span></span> |
| [<span data-ttu-id="96d50-120">Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="96d50-120">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="96d50-121">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-121">5.0</span></span> |
| [<span data-ttu-id="96d50-122">Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="96d50-122">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="96d50-123">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-123">5.0</span></span> |
| [<span data-ttu-id="96d50-124">Środowisko. OSVersion zwraca poprawną wersję systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="96d50-124">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="96d50-125">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-125">5.0</span></span> |
| [<span data-ttu-id="96d50-126">Złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł</span><span class="sxs-lookup"><span data-stu-id="96d50-126">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="96d50-127">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-127">5.0</span></span> |
| [<span data-ttu-id="96d50-128">IntPtr i UIntPtr Implementuj IFormattable</span><span class="sxs-lookup"><span data-stu-id="96d50-128">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="96d50-129">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-129">5.0</span></span> |
| [<span data-ttu-id="96d50-130">PrincipalPermissionAttribute jest przestarzały jako błąd</span><span class="sxs-lookup"><span data-stu-id="96d50-130">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="96d50-131">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-131">5.0</span></span> |
| [<span data-ttu-id="96d50-132">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="96d50-132">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="96d50-133">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-133">5.0</span></span> |
| [<span data-ttu-id="96d50-134">Ścieżki kodu UTF-7 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="96d50-134">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="96d50-135">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-135">5.0</span></span> |
| [<span data-ttu-id="96d50-136">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="96d50-136">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="96d50-137">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-137">5.0</span></span> |
| [<span data-ttu-id="96d50-138">ActivityIdFormat domyślny to W3C</span><span class="sxs-lookup"><span data-stu-id="96d50-138">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="96d50-139">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-139">5.0</span></span> |
| [<span data-ttu-id="96d50-140">Zmiana zachowania dla Vector2. Lerp i Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="96d50-140">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="96d50-141">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-141">5.0</span></span> |
| [<span data-ttu-id="96d50-142">Metody SSE i SSE2 CompareGreaterThan prawidłowo obsługują dane wejściowe NaN</span><span class="sxs-lookup"><span data-stu-id="96d50-142">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="96d50-143">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-143">5.0</span></span> |
| [<span data-ttu-id="96d50-144">Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje</span><span class="sxs-lookup"><span data-stu-id="96d50-144">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="96d50-145">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-145">5.0</span></span> |
| [<span data-ttu-id="96d50-146">Usunięto pakiet Microsoft. DotNet. PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="96d50-146">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="96d50-147">5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-147">5.0</span></span> |
| [<span data-ttu-id="96d50-148">Interfejsy API służące do raportowania wersji teraz produktu i nie wersji</span><span class="sxs-lookup"><span data-stu-id="96d50-148">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="96d50-149">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-149">3.0</span></span> |
| [<span data-ttu-id="96d50-150">Niestandardowe wystąpienia EncoderFallbackBuffer nie mogą podlegać rekursywnie</span><span class="sxs-lookup"><span data-stu-id="96d50-150">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="96d50-151">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-151">3.0</span></span> |
| [<span data-ttu-id="96d50-152">Zmiany zachowań formatowania zmiennoprzecinkowego i analizowania</span><span class="sxs-lookup"><span data-stu-id="96d50-152">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="96d50-153">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-153">3.0</span></span> |
| [<span data-ttu-id="96d50-154">Operacje analizowania zmiennoprzecinkowe nie będą już kończyć się niepowodzeniem lub nie generują wyjątku overflow</span><span class="sxs-lookup"><span data-stu-id="96d50-154">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="96d50-155">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-155">3.0</span></span> |
| [<span data-ttu-id="96d50-156">InvalidAsynchronousStateException — przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="96d50-156">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="96d50-157">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-157">3.0</span></span> |
| [<span data-ttu-id="96d50-158">Zastępowanie źle sformułowanych sekwencji bajtów w formacie UTF-8 następuje po wskazówkach dotyczących standardu Unicode</span><span class="sxs-lookup"><span data-stu-id="96d50-158">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="96d50-159">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-159">3.0</span></span> |
| [<span data-ttu-id="96d50-160">TypeDescriptionProviderAttribute przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="96d50-160">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="96d50-161">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-161">3.0</span></span> |
| [<span data-ttu-id="96d50-162">Element ZipArchiveEntry nie obsługuje już archiwów z niespójnymi rozmiarami wpisów</span><span class="sxs-lookup"><span data-stu-id="96d50-162">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="96d50-163">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-163">3.0</span></span> |
| [<span data-ttu-id="96d50-164">Element FieldInfo. SetValue zgłasza wyjątek dla pól static, tylko init</span><span class="sxs-lookup"><span data-stu-id="96d50-164">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="96d50-165">3,0</span><span class="sxs-lookup"><span data-stu-id="96d50-165">3.0</span></span> |
| [<span data-ttu-id="96d50-166">Pola prywatne dodane do wbudowanych typów struktur</span><span class="sxs-lookup"><span data-stu-id="96d50-166">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="96d50-167">2.1</span><span class="sxs-lookup"><span data-stu-id="96d50-167">2.1</span></span> |
| [<span data-ttu-id="96d50-168">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="96d50-168">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="96d50-169">2.1</span><span class="sxs-lookup"><span data-stu-id="96d50-169">2.1</span></span> |
| [<span data-ttu-id="96d50-170">Wersje OpenSSL na macOS</span><span class="sxs-lookup"><span data-stu-id="96d50-170">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="96d50-171">2.1</span><span class="sxs-lookup"><span data-stu-id="96d50-171">2.1</span></span> |
| [<span data-ttu-id="96d50-172">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="96d50-172">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="96d50-173">1,0</span><span class="sxs-lookup"><span data-stu-id="96d50-173">1.0</span></span> |
| [<span data-ttu-id="96d50-174">Obsługa wyjątków uszkodzonego stanu procesu nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="96d50-174">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="96d50-175">1,0</span><span class="sxs-lookup"><span data-stu-id="96d50-175">1.0</span></span> |
| [<span data-ttu-id="96d50-176">Właściwości UriBuilder nie dołączają już znaków wiodących</span><span class="sxs-lookup"><span data-stu-id="96d50-176">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="96d50-177">1,0</span><span class="sxs-lookup"><span data-stu-id="96d50-177">1.0</span></span> |
| [<span data-ttu-id="96d50-178">Proces. element StartInfo zgłasza InvalidOperationException dla procesów, które nie zostały uruchomione</span><span class="sxs-lookup"><span data-stu-id="96d50-178">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="96d50-179">1,0</span><span class="sxs-lookup"><span data-stu-id="96d50-179">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="96d50-180">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="96d50-180">.NET 5.0</span></span>

[!INCLUDE [reference-assembly-parameter-names-rc1](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names-rc1.md)]

***

[!INCLUDE [os-platform-attributes-renamed](../../../includes/core-changes/corefx/5.0/os-platform-attributes-renamed.md)]

***

[!INCLUDE [thread-abort-obsolete](../../../includes/core-changes/corefx/5.0/thread-abort-obsolete.md)]

***

[!INCLUDE [obsolete-consoleloggeroptions-properties](../../../includes/core-changes/corefx/5.0/obsolete-consoleloggeroptions-properties.md)]

***

[!INCLUDE [hardware-instrinsics-issupported-checks](../../../includes/core-changes/corefx/5.0/hardware-instrinsics-issupported-checks.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="96d50-181">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="96d50-181">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="96d50-182">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="96d50-182">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="96d50-183">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="96d50-183">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
