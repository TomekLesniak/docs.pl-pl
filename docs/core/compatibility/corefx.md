---
title: Podstawowe zmiany w bibliotece klas podstawowych
description: Wyświetla istotne zmiany w podstawowych bibliotekach programu .NET.
ms.date: 07/27/2020
ms.openlocfilehash: 8ea1cd995484c2930c8a9c2eb4c7419be57cf9c0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440179"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="0f4a2-103">Podstawowe zmiany w bibliotekach .NET</span><span class="sxs-lookup"><span data-stu-id="0f4a2-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="0f4a2-104">Podstawowe biblioteki .NET zapewniają pierwotne i inne typy ogólne używane przez platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0f4a2-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="0f4a2-105">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="0f4a2-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="0f4a2-106">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="0f4a2-106">Breaking change</span></span> | <span data-ttu-id="0f4a2-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="0f4a2-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="0f4a2-108">LastIndexOf Ulepszono obsługę pustych ciągów wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="0f4a2-108">LastIndexOf has improved handling of empty search strings</span></span>](#lastindexof-has-improved-handling-of-empty-search-strings) | <span data-ttu-id="0f4a2-109">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-109">5.0</span></span> |
| [<span data-ttu-id="0f4a2-110">Interfejsy API pamięci podręcznej zestawów globalnych są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="0f4a2-110">Global assembly cache APIs are obsolete</span></span>](#global-assembly-cache-apis-are-obsolete) | <span data-ttu-id="0f4a2-111">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-111">5.0</span></span> |
| [<span data-ttu-id="0f4a2-112">Interfejsy API komunikacji zdalnej są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="0f4a2-112">Remoting APIs are obsolete</span></span>](#remoting-apis-are-obsolete) | <span data-ttu-id="0f4a2-113">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-113">5.0</span></span> |
| [<span data-ttu-id="0f4a2-114">Większość interfejsów API zabezpieczeń dostępu kodu jest przestarzałych</span><span class="sxs-lookup"><span data-stu-id="0f4a2-114">Most code access security APIs are obsolete</span></span>](#most-code-access-security-apis-are-obsolete) | <span data-ttu-id="0f4a2-115">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-115">5.0</span></span> |
| [<span data-ttu-id="0f4a2-116">Interfejs API Obsoletions z identyfikatorami diagnostycznymi innymi niż domyślne</span><span class="sxs-lookup"><span data-stu-id="0f4a2-116">API obsoletions with non-default diagnostic IDs</span></span>](#api-obsoletions-with-non-default-diagnostic-ids) | <span data-ttu-id="0f4a2-117">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-117">5.0</span></span> |
| [<span data-ttu-id="0f4a2-118">FrameworkDescription jest wartością .NET zamiast .NET Core</span><span class="sxs-lookup"><span data-stu-id="0f4a2-118">FrameworkDescription's value is .NET instead of .NET Core</span></span>](#frameworkdescriptions-value-is-net-instead-of-net-core) | <span data-ttu-id="0f4a2-119">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-119">5.0</span></span> |
| [<span data-ttu-id="0f4a2-120">Zmiany zachowania interfejsu API związane z zestawem dla formatu publikowania pojedynczego pliku</span><span class="sxs-lookup"><span data-stu-id="0f4a2-120">Assembly-related API behavior changes for single-file publishing format</span></span>](#assembly-related-api-behavior-changes-for-single-file-publishing-format) | <span data-ttu-id="0f4a2-121">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-121">5.0</span></span> |
| [<span data-ttu-id="0f4a2-122">Kolejność tagów w działaniu. Tagi są odwrócone</span><span class="sxs-lookup"><span data-stu-id="0f4a2-122">Order of tags in Activity.Tags is reversed</span></span>](#order-of-tags-in-activitytags-is-reversed) | <span data-ttu-id="0f4a2-123">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-123">5.0</span></span> |
| [<span data-ttu-id="0f4a2-124">Nazwy parametrów zostały zmienione w wersji RC1</span><span class="sxs-lookup"><span data-stu-id="0f4a2-124">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="0f4a2-125">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-125">5.0</span></span> |
| [<span data-ttu-id="0f4a2-126">Atrybuty OSPlatform zostały zmienione lub usunięte</span><span class="sxs-lookup"><span data-stu-id="0f4a2-126">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="0f4a2-127">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-127">5.0</span></span> |
| [<span data-ttu-id="0f4a2-128">Wątek. Abort jest przestarzały</span><span class="sxs-lookup"><span data-stu-id="0f4a2-128">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="0f4a2-129">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-129">5.0</span></span> |
| [<span data-ttu-id="0f4a2-130">Przestarzałe właściwości w ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="0f4a2-130">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="0f4a2-131">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-131">5.0</span></span> |
| [<span data-ttu-id="0f4a2-132">Wewnętrzne testy nieobsługiwane sprzętowo mogą się różnić w zależności od typów zagnieżdżonych</span><span class="sxs-lookup"><span data-stu-id="0f4a2-132">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="0f4a2-133">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-133">5.0</span></span> |
| [<span data-ttu-id="0f4a2-134">Nazwy parametrów zostały zmienione w zestawach odwołań</span><span class="sxs-lookup"><span data-stu-id="0f4a2-134">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="0f4a2-135">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-135">5.0</span></span> |
| [<span data-ttu-id="0f4a2-136">Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="0f4a2-136">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="0f4a2-137">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-137">5.0</span></span> |
| [<span data-ttu-id="0f4a2-138">Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="0f4a2-138">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="0f4a2-139">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-139">5.0</span></span> |
| [<span data-ttu-id="0f4a2-140">Środowisko. OSVersion zwraca poprawną wersję systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="0f4a2-140">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="0f4a2-141">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-141">5.0</span></span> |
| [<span data-ttu-id="0f4a2-142">Złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł</span><span class="sxs-lookup"><span data-stu-id="0f4a2-142">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="0f4a2-143">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-143">5.0</span></span> |
| [<span data-ttu-id="0f4a2-144">IntPtr i UIntPtr Implementuj IFormattable</span><span class="sxs-lookup"><span data-stu-id="0f4a2-144">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="0f4a2-145">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-145">5.0</span></span> |
| [<span data-ttu-id="0f4a2-146">PrincipalPermissionAttribute jest przestarzały jako błąd</span><span class="sxs-lookup"><span data-stu-id="0f4a2-146">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="0f4a2-147">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-147">5.0</span></span> |
| [<span data-ttu-id="0f4a2-148">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0f4a2-148">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="0f4a2-149">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-149">5.0</span></span> |
| [<span data-ttu-id="0f4a2-150">Ścieżki kodu UTF-7 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="0f4a2-150">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="0f4a2-151">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-151">5.0</span></span> |
| [<span data-ttu-id="0f4a2-152">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="0f4a2-152">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="0f4a2-153">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-153">5.0</span></span> |
| [<span data-ttu-id="0f4a2-154">ActivityIdFormat domyślny to W3C</span><span class="sxs-lookup"><span data-stu-id="0f4a2-154">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="0f4a2-155">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-155">5.0</span></span> |
| [<span data-ttu-id="0f4a2-156">Zmiana zachowania dla Vector2. Lerp i Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="0f4a2-156">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="0f4a2-157">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-157">5.0</span></span> |
| [<span data-ttu-id="0f4a2-158">Metody SSE i SSE2 CompareGreaterThan prawidłowo obsługują dane wejściowe NaN</span><span class="sxs-lookup"><span data-stu-id="0f4a2-158">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="0f4a2-159">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-159">5.0</span></span> |
| [<span data-ttu-id="0f4a2-160">Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje</span><span class="sxs-lookup"><span data-stu-id="0f4a2-160">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="0f4a2-161">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-161">5.0</span></span> |
| [<span data-ttu-id="0f4a2-162">Usunięto pakiet Microsoft. DotNet. PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="0f4a2-162">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="0f4a2-163">5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-163">5.0</span></span> |
| [<span data-ttu-id="0f4a2-164">Interfejsy API służące do raportowania wersji teraz produktu i nie wersji</span><span class="sxs-lookup"><span data-stu-id="0f4a2-164">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="0f4a2-165">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-165">3.0</span></span> |
| [<span data-ttu-id="0f4a2-166">Niestandardowe wystąpienia EncoderFallbackBuffer nie mogą podlegać rekursywnie</span><span class="sxs-lookup"><span data-stu-id="0f4a2-166">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="0f4a2-167">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-167">3.0</span></span> |
| [<span data-ttu-id="0f4a2-168">Zmiany zachowań formatowania zmiennoprzecinkowego i analizowania</span><span class="sxs-lookup"><span data-stu-id="0f4a2-168">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="0f4a2-169">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-169">3.0</span></span> |
| [<span data-ttu-id="0f4a2-170">Operacje analizowania zmiennoprzecinkowe nie będą już kończyć się niepowodzeniem lub nie generują wyjątku overflow</span><span class="sxs-lookup"><span data-stu-id="0f4a2-170">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="0f4a2-171">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-171">3.0</span></span> |
| [<span data-ttu-id="0f4a2-172">InvalidAsynchronousStateException — przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="0f4a2-172">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="0f4a2-173">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-173">3.0</span></span> |
| [<span data-ttu-id="0f4a2-174">Zastępowanie źle sformułowanych sekwencji bajtów w formacie UTF-8 następuje po wskazówkach dotyczących standardu Unicode</span><span class="sxs-lookup"><span data-stu-id="0f4a2-174">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="0f4a2-175">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-175">3.0</span></span> |
| [<span data-ttu-id="0f4a2-176">TypeDescriptionProviderAttribute przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="0f4a2-176">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="0f4a2-177">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-177">3.0</span></span> |
| [<span data-ttu-id="0f4a2-178">Element ZipArchiveEntry nie obsługuje już archiwów z niespójnymi rozmiarami wpisów</span><span class="sxs-lookup"><span data-stu-id="0f4a2-178">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="0f4a2-179">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-179">3.0</span></span> |
| [<span data-ttu-id="0f4a2-180">Element FieldInfo. SetValue zgłasza wyjątek dla pól static, tylko init</span><span class="sxs-lookup"><span data-stu-id="0f4a2-180">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="0f4a2-181">3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-181">3.0</span></span> |
| [<span data-ttu-id="0f4a2-182">Pola prywatne dodane do wbudowanych typów struktur</span><span class="sxs-lookup"><span data-stu-id="0f4a2-182">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="0f4a2-183">2.1</span><span class="sxs-lookup"><span data-stu-id="0f4a2-183">2.1</span></span> |
| [<span data-ttu-id="0f4a2-184">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="0f4a2-184">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="0f4a2-185">2.1</span><span class="sxs-lookup"><span data-stu-id="0f4a2-185">2.1</span></span> |
| [<span data-ttu-id="0f4a2-186">Wersje OpenSSL na macOS</span><span class="sxs-lookup"><span data-stu-id="0f4a2-186">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="0f4a2-187">2.1</span><span class="sxs-lookup"><span data-stu-id="0f4a2-187">2.1</span></span> |
| [<span data-ttu-id="0f4a2-188">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="0f4a2-188">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="0f4a2-189">1,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-189">1.0</span></span> |
| [<span data-ttu-id="0f4a2-190">Obsługa wyjątków uszkodzonego stanu procesu nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="0f4a2-190">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="0f4a2-191">1,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-191">1.0</span></span> |
| [<span data-ttu-id="0f4a2-192">Właściwości UriBuilder nie dołączają już znaków wiodących</span><span class="sxs-lookup"><span data-stu-id="0f4a2-192">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="0f4a2-193">1,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-193">1.0</span></span> |
| [<span data-ttu-id="0f4a2-194">Proces. element StartInfo zgłasza InvalidOperationException dla procesów, które nie zostały uruchomione</span><span class="sxs-lookup"><span data-stu-id="0f4a2-194">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="0f4a2-195">1,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-195">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="0f4a2-196">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-196">.NET 5.0</span></span>

[!INCLUDE [lastindexof-improved-handling-of-empty-values](../../../includes/core-changes/corefx/5.0/lastindexof-improved-handling-of-empty-values.md)]

***

[!INCLUDE [remoting-apis-obsolete](../../../includes/core-changes/corefx/5.0/remoting-apis-obsolete.md)]

***

[!INCLUDE [globalassemblycache-property-obsolete](../../../includes/core-changes/corefx/5.0/global-assembly-cache-apis-obsolete.md)]

***

[!INCLUDE [code-access-security-apis-obsolete](../../../includes/core-changes/corefx/5.0/code-access-security-apis-obsolete.md)]

***

[!INCLUDE [obsolete-apis-with-custom-diagnostics](../../../includes/core-changes/corefx/5.0/obsolete-apis-with-custom-diagnostics.md)]

***

[!INCLUDE [frameworkdescription-returns-net-not-net-core](../../../includes/core-changes/corefx/5.0/frameworkdescription-returns-net-not-net-core.md)]

***

[!INCLUDE [assembly-api-behavior-changes-for-single-file-publish](../../../includes/core-changes/corefx/5.0/assembly-api-behavior-changes-for-single-file-publish.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="0f4a2-198">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-198">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="0f4a2-199">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0f4a2-199">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="0f4a2-200">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="0f4a2-200">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
