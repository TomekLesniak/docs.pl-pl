---
title: Podstawowe zmiany w bibliotece klas podstawowych
description: Wyświetla istotne zmiany w podstawowych bibliotekach programu .NET.
ms.date: 07/27/2020
ms.openlocfilehash: 35192ae078c6025b9b399d6638ea8b4f426aceda
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332936"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="e8d10-103">Podstawowe zmiany w bibliotekach .NET</span><span class="sxs-lookup"><span data-stu-id="e8d10-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="e8d10-104">Podstawowe biblioteki .NET zapewniają pierwotne i inne typy ogólne używane przez platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e8d10-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="e8d10-105">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="e8d10-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="e8d10-106">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="e8d10-106">Breaking change</span></span> | <span data-ttu-id="e8d10-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="e8d10-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="e8d10-108">Interfejs API Obsoletions z identyfikatorami diagnostycznymi innymi niż domyślne</span><span class="sxs-lookup"><span data-stu-id="e8d10-108">API obsoletions with non-default diagnostic IDs</span></span>](#api-obsoletions-with-non-default-diagnostic-ids) | <span data-ttu-id="e8d10-109">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-109">5.0</span></span> |
| [<span data-ttu-id="e8d10-110">FrameworkDescription jest wartością .NET zamiast .NET Core</span><span class="sxs-lookup"><span data-stu-id="e8d10-110">FrameworkDescription's value is .NET instead of .NET Core</span></span>](#frameworkdescriptions-value-is-net-instead-of-net-core) | <span data-ttu-id="e8d10-111">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-111">5.0</span></span> |
| [<span data-ttu-id="e8d10-112">Zmiany zachowania interfejsu API związane z zestawem dla formatu publikowania pojedynczego pliku</span><span class="sxs-lookup"><span data-stu-id="e8d10-112">Assembly-related API behavior changes for single-file publishing format</span></span>](#assembly-related-api-behavior-changes-for-single-file-publishing-format) | <span data-ttu-id="e8d10-113">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-113">5.0</span></span> |
| [<span data-ttu-id="e8d10-114">Kolejność tagów w działaniu. Tagi są odwrócone</span><span class="sxs-lookup"><span data-stu-id="e8d10-114">Order of tags in Activity.Tags is reversed</span></span>](#order-of-tags-in-activitytags-is-reversed) | <span data-ttu-id="e8d10-115">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-115">5.0</span></span> |
| [<span data-ttu-id="e8d10-116">Nazwy parametrów zostały zmienione w wersji RC1</span><span class="sxs-lookup"><span data-stu-id="e8d10-116">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="e8d10-117">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-117">5.0</span></span> |
| [<span data-ttu-id="e8d10-118">Atrybuty OSPlatform zostały zmienione lub usunięte</span><span class="sxs-lookup"><span data-stu-id="e8d10-118">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="e8d10-119">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-119">5.0</span></span> |
| [<span data-ttu-id="e8d10-120">Wątek. Abort jest przestarzały</span><span class="sxs-lookup"><span data-stu-id="e8d10-120">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="e8d10-121">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-121">5.0</span></span> |
| [<span data-ttu-id="e8d10-122">Przestarzałe właściwości w ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="e8d10-122">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="e8d10-123">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-123">5.0</span></span> |
| [<span data-ttu-id="e8d10-124">Wewnętrzne testy nieobsługiwane sprzętowo mogą się różnić w zależności od typów zagnieżdżonych</span><span class="sxs-lookup"><span data-stu-id="e8d10-124">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="e8d10-125">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-125">5.0</span></span> |
| [<span data-ttu-id="e8d10-126">Nazwy parametrów zostały zmienione w zestawach odwołań</span><span class="sxs-lookup"><span data-stu-id="e8d10-126">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="e8d10-127">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-127">5.0</span></span> |
| [<span data-ttu-id="e8d10-128">Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="e8d10-128">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="e8d10-129">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-129">5.0</span></span> |
| [<span data-ttu-id="e8d10-130">Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="e8d10-130">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="e8d10-131">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-131">5.0</span></span> |
| [<span data-ttu-id="e8d10-132">Środowisko. OSVersion zwraca poprawną wersję systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="e8d10-132">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="e8d10-133">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-133">5.0</span></span> |
| [<span data-ttu-id="e8d10-134">Złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł</span><span class="sxs-lookup"><span data-stu-id="e8d10-134">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="e8d10-135">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-135">5.0</span></span> |
| [<span data-ttu-id="e8d10-136">IntPtr i UIntPtr Implementuj IFormattable</span><span class="sxs-lookup"><span data-stu-id="e8d10-136">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="e8d10-137">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-137">5.0</span></span> |
| [<span data-ttu-id="e8d10-138">PrincipalPermissionAttribute jest przestarzały jako błąd</span><span class="sxs-lookup"><span data-stu-id="e8d10-138">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="e8d10-139">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-139">5.0</span></span> |
| [<span data-ttu-id="e8d10-140">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e8d10-140">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="e8d10-141">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-141">5.0</span></span> |
| [<span data-ttu-id="e8d10-142">Ścieżki kodu UTF-7 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="e8d10-142">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="e8d10-143">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-143">5.0</span></span> |
| [<span data-ttu-id="e8d10-144">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="e8d10-144">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="e8d10-145">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-145">5.0</span></span> |
| [<span data-ttu-id="e8d10-146">ActivityIdFormat domyślny to W3C</span><span class="sxs-lookup"><span data-stu-id="e8d10-146">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="e8d10-147">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-147">5.0</span></span> |
| [<span data-ttu-id="e8d10-148">Zmiana zachowania dla Vector2. Lerp i Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="e8d10-148">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="e8d10-149">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-149">5.0</span></span> |
| [<span data-ttu-id="e8d10-150">Metody SSE i SSE2 CompareGreaterThan prawidłowo obsługują dane wejściowe NaN</span><span class="sxs-lookup"><span data-stu-id="e8d10-150">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="e8d10-151">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-151">5.0</span></span> |
| [<span data-ttu-id="e8d10-152">Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje</span><span class="sxs-lookup"><span data-stu-id="e8d10-152">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="e8d10-153">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-153">5.0</span></span> |
| [<span data-ttu-id="e8d10-154">Usunięto pakiet Microsoft. DotNet. PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="e8d10-154">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="e8d10-155">5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-155">5.0</span></span> |
| [<span data-ttu-id="e8d10-156">Interfejsy API służące do raportowania wersji teraz produktu i nie wersji</span><span class="sxs-lookup"><span data-stu-id="e8d10-156">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="e8d10-157">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-157">3.0</span></span> |
| [<span data-ttu-id="e8d10-158">Niestandardowe wystąpienia EncoderFallbackBuffer nie mogą podlegać rekursywnie</span><span class="sxs-lookup"><span data-stu-id="e8d10-158">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="e8d10-159">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-159">3.0</span></span> |
| [<span data-ttu-id="e8d10-160">Zmiany zachowań formatowania zmiennoprzecinkowego i analizowania</span><span class="sxs-lookup"><span data-stu-id="e8d10-160">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="e8d10-161">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-161">3.0</span></span> |
| [<span data-ttu-id="e8d10-162">Operacje analizowania zmiennoprzecinkowe nie będą już kończyć się niepowodzeniem lub nie generują wyjątku overflow</span><span class="sxs-lookup"><span data-stu-id="e8d10-162">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="e8d10-163">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-163">3.0</span></span> |
| [<span data-ttu-id="e8d10-164">InvalidAsynchronousStateException — przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="e8d10-164">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="e8d10-165">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-165">3.0</span></span> |
| [<span data-ttu-id="e8d10-166">Zastępowanie źle sformułowanych sekwencji bajtów w formacie UTF-8 następuje po wskazówkach dotyczących standardu Unicode</span><span class="sxs-lookup"><span data-stu-id="e8d10-166">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="e8d10-167">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-167">3.0</span></span> |
| [<span data-ttu-id="e8d10-168">TypeDescriptionProviderAttribute przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="e8d10-168">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="e8d10-169">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-169">3.0</span></span> |
| [<span data-ttu-id="e8d10-170">Element ZipArchiveEntry nie obsługuje już archiwów z niespójnymi rozmiarami wpisów</span><span class="sxs-lookup"><span data-stu-id="e8d10-170">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="e8d10-171">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-171">3.0</span></span> |
| [<span data-ttu-id="e8d10-172">Element FieldInfo. SetValue zgłasza wyjątek dla pól static, tylko init</span><span class="sxs-lookup"><span data-stu-id="e8d10-172">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="e8d10-173">3,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-173">3.0</span></span> |
| [<span data-ttu-id="e8d10-174">Pola prywatne dodane do wbudowanych typów struktur</span><span class="sxs-lookup"><span data-stu-id="e8d10-174">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="e8d10-175">2.1</span><span class="sxs-lookup"><span data-stu-id="e8d10-175">2.1</span></span> |
| [<span data-ttu-id="e8d10-176">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="e8d10-176">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="e8d10-177">2.1</span><span class="sxs-lookup"><span data-stu-id="e8d10-177">2.1</span></span> |
| [<span data-ttu-id="e8d10-178">Wersje OpenSSL na macOS</span><span class="sxs-lookup"><span data-stu-id="e8d10-178">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="e8d10-179">2.1</span><span class="sxs-lookup"><span data-stu-id="e8d10-179">2.1</span></span> |
| [<span data-ttu-id="e8d10-180">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="e8d10-180">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="e8d10-181">1.0</span><span class="sxs-lookup"><span data-stu-id="e8d10-181">1.0</span></span> |
| [<span data-ttu-id="e8d10-182">Obsługa wyjątków uszkodzonego stanu procesu nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="e8d10-182">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="e8d10-183">1.0</span><span class="sxs-lookup"><span data-stu-id="e8d10-183">1.0</span></span> |
| [<span data-ttu-id="e8d10-184">Właściwości UriBuilder nie dołączają już znaków wiodących</span><span class="sxs-lookup"><span data-stu-id="e8d10-184">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="e8d10-185">1.0</span><span class="sxs-lookup"><span data-stu-id="e8d10-185">1.0</span></span> |
| [<span data-ttu-id="e8d10-186">Proces. element StartInfo zgłasza InvalidOperationException dla procesów, które nie zostały uruchomione</span><span class="sxs-lookup"><span data-stu-id="e8d10-186">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="e8d10-187">1.0</span><span class="sxs-lookup"><span data-stu-id="e8d10-187">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="e8d10-188">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-188">.NET 5.0</span></span>

[!INCLUDE [obsolete-apis-with-custom-diagnostics](../../../includes/core-changes/corefx/5.0/obsolete-apis-with-custom-diagnostics.md)]

***

[!INCLUDE [frameworkdescription-returns-net-not-net-core](../../../includes/core-changes/corefx/5.0/frameworkdescription-returns-net-not-net-core.md)]

<span data-ttu-id="e8d10-189">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e8d10-189">\*\*_</span></span>

[!INCLUDE [assembly-api-behavior-changes-for-single-file-publish](../../../includes/core-changes/corefx/5.0/assembly-api-behavior-changes-for-single-file-publish.md)]

_*_

[!INCLUDE [reverse-order-of-tags-in-activity-property](../../../includes/core-changes/corefx/5.0/reverse-order-of-tags-in-activity-property.md)]

_*_

[!INCLUDE [reference-assembly-parameter-names-rc1](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names-rc1.md)]

_*_

[!INCLUDE [os-platform-attributes-renamed](../../../includes/core-changes/corefx/5.0/os-platform-attributes-renamed.md)]

_*_

[!INCLUDE [thread-abort-obsolete](../../../includes/core-changes/corefx/5.0/thread-abort-obsolete.md)]

_*_

[!INCLUDE [obsolete-consoleloggeroptions-properties](../../../includes/core-changes/corefx/5.0/obsolete-consoleloggeroptions-properties.md)]

_*_

[!INCLUDE [hardware-instrinsics-issupported-checks](../../../includes/core-changes/corefx/5.0/hardware-instrinsics-issupported-checks.md)]

_*_

[!INCLUDE [reference-assembly-parameter-names](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names.md)]

_*_

[!INCLUDE [non-ascii-chars-in-uri-parsed-correctly](../../../includes/core-changes/corefx/5.0/non-ascii-chars-in-uri-parsed-correctly.md)]

_*_

[!INCLUDE [unc-path-recognition-unix](../../../includes/core-changes/corefx/5.0/unc-path-recognition-unix.md)]

_*_

[!INCLUDE [environment-osversion-returns-correct-version](../../../includes/core-changes/corefx/5.0/environment-osversion-returns-correct-version.md)]

_*_

[!INCLUDE [orderby-firstordefault-complexity-increase](../../../includes/core-changes/corefx/5.0/orderby-firstordefault-complexity-increase.md)]

_*_

[!INCLUDE [intptr-uintptr-implement-iformattable](../../../includes/core-changes/corefx/5.0/intptr-uintptr-implement-iformattable.md)]

_*_

[!INCLUDE [principalpermissionattribute-obsolete](../../../includes/core-changes/corefx/5.0/principalpermissionattribute-obsolete.md)]

_*_

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

_*_

[!INCLUDE [utf-7-code-paths-obsolete](../../../includes/core-changes/corefx/5.0/utf-7-code-paths-obsolete.md)]

_*_

[!INCLUDE [vectort-throws-notsupportedexception](../../../includes/core-changes/corefx/5.0/vectort-throws-notsupportedexception.md)]

_*_

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

_*_

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

_*_

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

_*_

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

_*_

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="e8d10-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e8d10-190">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

_*_

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

_*_

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

_*_

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

_*_

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

_*_

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

_*_

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

_*_

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

_*_

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="e8d10-191">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e8d10-191">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a><span data-ttu-id="e8d10-192">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="e8d10-192">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

<span data-ttu-id="e8d10-193">_\*\*</span><span class="sxs-lookup"><span data-stu-id="e8d10-193">_\*\*</span></span>
