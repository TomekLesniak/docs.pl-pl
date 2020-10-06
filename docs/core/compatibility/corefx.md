---
title: Podstawowe zmiany w bibliotece klas podstawowych
description: Wyświetla istotne zmiany w podstawowych bibliotekach programu .NET.
ms.date: 07/27/2020
ms.openlocfilehash: b86ceab784fd295acf500986f7e64731eb8ed0a3
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756117"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="f1f12-103">Podstawowe zmiany w bibliotekach .NET</span><span class="sxs-lookup"><span data-stu-id="f1f12-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="f1f12-104">Podstawowe biblioteki .NET zapewniają pierwotne i inne typy ogólne używane przez platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1f12-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="f1f12-105">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="f1f12-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="f1f12-106">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="f1f12-106">Breaking change</span></span> | <span data-ttu-id="f1f12-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="f1f12-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="f1f12-108">Kolejność tagów w działaniu. Tagi są odwrócone</span><span class="sxs-lookup"><span data-stu-id="f1f12-108">Order of tags in Activity.Tags is reversed</span></span>](#order-of-tags-in-activitytags-is-reversed) | <span data-ttu-id="f1f12-109">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-109">5.0</span></span> |
| [<span data-ttu-id="f1f12-110">Nazwy parametrów zostały zmienione w wersji RC1</span><span class="sxs-lookup"><span data-stu-id="f1f12-110">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="f1f12-111">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-111">5.0</span></span> |
| [<span data-ttu-id="f1f12-112">Atrybuty OSPlatform zostały zmienione lub usunięte</span><span class="sxs-lookup"><span data-stu-id="f1f12-112">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="f1f12-113">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-113">5.0</span></span> |
| [<span data-ttu-id="f1f12-114">Wątek. Abort jest przestarzały</span><span class="sxs-lookup"><span data-stu-id="f1f12-114">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="f1f12-115">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-115">5.0</span></span> |
| [<span data-ttu-id="f1f12-116">Przestarzałe właściwości w ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="f1f12-116">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="f1f12-117">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-117">5.0</span></span> |
| [<span data-ttu-id="f1f12-118">Wewnętrzne testy nieobsługiwane sprzętowo mogą się różnić w zależności od typów zagnieżdżonych</span><span class="sxs-lookup"><span data-stu-id="f1f12-118">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="f1f12-119">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-119">5.0</span></span> |
| [<span data-ttu-id="f1f12-120">Nazwy parametrów zostały zmienione w zestawach odwołań</span><span class="sxs-lookup"><span data-stu-id="f1f12-120">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="f1f12-121">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-121">5.0</span></span> |
| [<span data-ttu-id="f1f12-122">Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="f1f12-122">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="f1f12-123">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-123">5.0</span></span> |
| [<span data-ttu-id="f1f12-124">Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="f1f12-124">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="f1f12-125">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-125">5.0</span></span> |
| [<span data-ttu-id="f1f12-126">Środowisko. OSVersion zwraca poprawną wersję systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="f1f12-126">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="f1f12-127">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-127">5.0</span></span> |
| [<span data-ttu-id="f1f12-128">Złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł</span><span class="sxs-lookup"><span data-stu-id="f1f12-128">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="f1f12-129">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-129">5.0</span></span> |
| [<span data-ttu-id="f1f12-130">IntPtr i UIntPtr Implementuj IFormattable</span><span class="sxs-lookup"><span data-stu-id="f1f12-130">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="f1f12-131">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-131">5.0</span></span> |
| [<span data-ttu-id="f1f12-132">PrincipalPermissionAttribute jest przestarzały jako błąd</span><span class="sxs-lookup"><span data-stu-id="f1f12-132">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="f1f12-133">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-133">5.0</span></span> |
| [<span data-ttu-id="f1f12-134">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f1f12-134">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="f1f12-135">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-135">5.0</span></span> |
| [<span data-ttu-id="f1f12-136">Ścieżki kodu UTF-7 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="f1f12-136">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="f1f12-137">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-137">5.0</span></span> |
| [<span data-ttu-id="f1f12-138">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="f1f12-138">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="f1f12-139">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-139">5.0</span></span> |
| [<span data-ttu-id="f1f12-140">ActivityIdFormat domyślny to W3C</span><span class="sxs-lookup"><span data-stu-id="f1f12-140">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="f1f12-141">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-141">5.0</span></span> |
| [<span data-ttu-id="f1f12-142">Zmiana zachowania dla Vector2. Lerp i Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="f1f12-142">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="f1f12-143">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-143">5.0</span></span> |
| [<span data-ttu-id="f1f12-144">Metody SSE i SSE2 CompareGreaterThan prawidłowo obsługują dane wejściowe NaN</span><span class="sxs-lookup"><span data-stu-id="f1f12-144">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="f1f12-145">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-145">5.0</span></span> |
| [<span data-ttu-id="f1f12-146">Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje</span><span class="sxs-lookup"><span data-stu-id="f1f12-146">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="f1f12-147">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-147">5.0</span></span> |
| [<span data-ttu-id="f1f12-148">Usunięto pakiet Microsoft. DotNet. PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="f1f12-148">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="f1f12-149">5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-149">5.0</span></span> |
| [<span data-ttu-id="f1f12-150">Interfejsy API służące do raportowania wersji teraz produktu i nie wersji</span><span class="sxs-lookup"><span data-stu-id="f1f12-150">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="f1f12-151">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-151">3.0</span></span> |
| [<span data-ttu-id="f1f12-152">Niestandardowe wystąpienia EncoderFallbackBuffer nie mogą podlegać rekursywnie</span><span class="sxs-lookup"><span data-stu-id="f1f12-152">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="f1f12-153">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-153">3.0</span></span> |
| [<span data-ttu-id="f1f12-154">Zmiany zachowań formatowania zmiennoprzecinkowego i analizowania</span><span class="sxs-lookup"><span data-stu-id="f1f12-154">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="f1f12-155">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-155">3.0</span></span> |
| [<span data-ttu-id="f1f12-156">Operacje analizowania zmiennoprzecinkowe nie będą już kończyć się niepowodzeniem lub nie generują wyjątku overflow</span><span class="sxs-lookup"><span data-stu-id="f1f12-156">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="f1f12-157">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-157">3.0</span></span> |
| [<span data-ttu-id="f1f12-158">InvalidAsynchronousStateException — przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="f1f12-158">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="f1f12-159">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-159">3.0</span></span> |
| [<span data-ttu-id="f1f12-160">Zastępowanie źle sformułowanych sekwencji bajtów w formacie UTF-8 następuje po wskazówkach dotyczących standardu Unicode</span><span class="sxs-lookup"><span data-stu-id="f1f12-160">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="f1f12-161">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-161">3.0</span></span> |
| [<span data-ttu-id="f1f12-162">TypeDescriptionProviderAttribute przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="f1f12-162">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="f1f12-163">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-163">3.0</span></span> |
| [<span data-ttu-id="f1f12-164">Element ZipArchiveEntry nie obsługuje już archiwów z niespójnymi rozmiarami wpisów</span><span class="sxs-lookup"><span data-stu-id="f1f12-164">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="f1f12-165">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-165">3.0</span></span> |
| [<span data-ttu-id="f1f12-166">Element FieldInfo. SetValue zgłasza wyjątek dla pól static, tylko init</span><span class="sxs-lookup"><span data-stu-id="f1f12-166">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="f1f12-167">3,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-167">3.0</span></span> |
| [<span data-ttu-id="f1f12-168">Pola prywatne dodane do wbudowanych typów struktur</span><span class="sxs-lookup"><span data-stu-id="f1f12-168">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="f1f12-169">2.1</span><span class="sxs-lookup"><span data-stu-id="f1f12-169">2.1</span></span> |
| [<span data-ttu-id="f1f12-170">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="f1f12-170">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="f1f12-171">2.1</span><span class="sxs-lookup"><span data-stu-id="f1f12-171">2.1</span></span> |
| [<span data-ttu-id="f1f12-172">Wersje OpenSSL na macOS</span><span class="sxs-lookup"><span data-stu-id="f1f12-172">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="f1f12-173">2.1</span><span class="sxs-lookup"><span data-stu-id="f1f12-173">2.1</span></span> |
| [<span data-ttu-id="f1f12-174">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="f1f12-174">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="f1f12-175">1.0</span><span class="sxs-lookup"><span data-stu-id="f1f12-175">1.0</span></span> |
| [<span data-ttu-id="f1f12-176">Obsługa wyjątków uszkodzonego stanu procesu nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="f1f12-176">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="f1f12-177">1.0</span><span class="sxs-lookup"><span data-stu-id="f1f12-177">1.0</span></span> |
| [<span data-ttu-id="f1f12-178">Właściwości UriBuilder nie dołączają już znaków wiodących</span><span class="sxs-lookup"><span data-stu-id="f1f12-178">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="f1f12-179">1.0</span><span class="sxs-lookup"><span data-stu-id="f1f12-179">1.0</span></span> |
| [<span data-ttu-id="f1f12-180">Proces. element StartInfo zgłasza InvalidOperationException dla procesów, które nie zostały uruchomione</span><span class="sxs-lookup"><span data-stu-id="f1f12-180">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="f1f12-181">1.0</span><span class="sxs-lookup"><span data-stu-id="f1f12-181">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="f1f12-182">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-182">.NET 5.0</span></span>

[!INCLUDE [reverse-order-of-tags-in-activity-property](../../../includes/core-changes/corefx/5.0/reverse-order-of-tags-in-activity-property.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="f1f12-183">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f1f12-183">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="f1f12-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f1f12-184">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="f1f12-185">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="f1f12-185">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
