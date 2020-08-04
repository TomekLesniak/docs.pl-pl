---
title: Podstawowe zmiany w bibliotece klas podstawowych
description: Wyświetla istotne zmiany w podstawowych bibliotekach programu .NET.
ms.date: 07/27/2020
ms.openlocfilehash: 558aa1d76831cd15e2028c17d2b0b2e82f64ef9a
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517333"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="40383-103">Podstawowe zmiany w bibliotekach .NET</span><span class="sxs-lookup"><span data-stu-id="40383-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="40383-104">Podstawowe biblioteki .NET zapewniają pierwotne i inne typy ogólne używane przez platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40383-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="40383-105">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="40383-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="40383-106">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="40383-106">Breaking change</span></span> | <span data-ttu-id="40383-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="40383-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="40383-108">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="40383-108">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="40383-109">5.0</span><span class="sxs-lookup"><span data-stu-id="40383-109">5.0</span></span> |
| [<span data-ttu-id="40383-110">Ścieżki kodu UTF-7 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="40383-110">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="40383-111">5.0</span><span class="sxs-lookup"><span data-stu-id="40383-111">5.0</span></span> |
| [<span data-ttu-id="40383-112">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="40383-112">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="40383-113">5.0</span><span class="sxs-lookup"><span data-stu-id="40383-113">5.0</span></span> |
| [<span data-ttu-id="40383-114">ActivityIdFormat domyślny to W3C</span><span class="sxs-lookup"><span data-stu-id="40383-114">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="40383-115">5.0</span><span class="sxs-lookup"><span data-stu-id="40383-115">5.0</span></span> |
| [<span data-ttu-id="40383-116">Zmiana zachowania dla Vector2. Lerp i Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="40383-116">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="40383-117">5.0</span><span class="sxs-lookup"><span data-stu-id="40383-117">5.0</span></span> |
| [<span data-ttu-id="40383-118">Metody SSE i SSE2 CompareGreaterThan prawidłowo obsługują dane wejściowe NaN</span><span class="sxs-lookup"><span data-stu-id="40383-118">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="40383-119">5.0</span><span class="sxs-lookup"><span data-stu-id="40383-119">5.0</span></span> |
| [<span data-ttu-id="40383-120">Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje</span><span class="sxs-lookup"><span data-stu-id="40383-120">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="40383-121">5.0</span><span class="sxs-lookup"><span data-stu-id="40383-121">5.0</span></span> |
| [<span data-ttu-id="40383-122">Usunięto pakiet Microsoft. DotNet. PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="40383-122">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="40383-123">5.0</span><span class="sxs-lookup"><span data-stu-id="40383-123">5.0</span></span> |
| [<span data-ttu-id="40383-124">Interfejsy API służące do raportowania wersji teraz produktu i nie wersji</span><span class="sxs-lookup"><span data-stu-id="40383-124">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="40383-125">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-125">3.0</span></span> |
| [<span data-ttu-id="40383-126">Niestandardowe wystąpienia EncoderFallbackBuffer nie mogą podlegać rekursywnie</span><span class="sxs-lookup"><span data-stu-id="40383-126">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="40383-127">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-127">3.0</span></span> |
| [<span data-ttu-id="40383-128">Zmiany zachowań formatowania zmiennoprzecinkowego i analizowania</span><span class="sxs-lookup"><span data-stu-id="40383-128">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="40383-129">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-129">3.0</span></span> |
| [<span data-ttu-id="40383-130">Operacje analizowania zmiennoprzecinkowe nie będą już kończyć się niepowodzeniem lub nie generują wyjątku overflow</span><span class="sxs-lookup"><span data-stu-id="40383-130">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="40383-131">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-131">3.0</span></span> |
| [<span data-ttu-id="40383-132">InvalidAsynchronousStateException — przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="40383-132">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="40383-133">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-133">3.0</span></span> |
| [<span data-ttu-id="40383-134">Zastępowanie źle sformułowanych sekwencji bajtów w formacie UTF-8 następuje po wskazówkach dotyczących standardu Unicode</span><span class="sxs-lookup"><span data-stu-id="40383-134">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="40383-135">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-135">3.0</span></span> |
| [<span data-ttu-id="40383-136">TypeDescriptionProviderAttribute przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="40383-136">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="40383-137">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-137">3.0</span></span> |
| [<span data-ttu-id="40383-138">Element ZipArchiveEntry nie obsługuje już archiwów z niespójnymi rozmiarami wpisów</span><span class="sxs-lookup"><span data-stu-id="40383-138">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="40383-139">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-139">3.0</span></span> |
| [<span data-ttu-id="40383-140">Zmień semantykę (String) na wartość null w Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="40383-140">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="40383-141">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-141">3.0</span></span> |
| [<span data-ttu-id="40383-142">Metody JsonEncodedText. Encode mają dodatkowy argument JavaScriptEncoder</span><span class="sxs-lookup"><span data-stu-id="40383-142">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="40383-143">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-143">3.0</span></span> |
| [<span data-ttu-id="40383-144">Zmieniono sygnaturę JsonFactoryConverter. isconverter</span><span class="sxs-lookup"><span data-stu-id="40383-144">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="40383-145">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-145">3.0</span></span> |
| [<span data-ttu-id="40383-146">Zmiany interfejsu API jsonelement</span><span class="sxs-lookup"><span data-stu-id="40383-146">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="40383-147">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-147">3.0</span></span> |
| [<span data-ttu-id="40383-148">Element FieldInfo. SetValue zgłasza wyjątek dla pól static, tylko init</span><span class="sxs-lookup"><span data-stu-id="40383-148">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="40383-149">3.0</span><span class="sxs-lookup"><span data-stu-id="40383-149">3.0</span></span> |
| [<span data-ttu-id="40383-150">Pola prywatne dodane do wbudowanych typów struktur</span><span class="sxs-lookup"><span data-stu-id="40383-150">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="40383-151">2.1</span><span class="sxs-lookup"><span data-stu-id="40383-151">2.1</span></span> |
| [<span data-ttu-id="40383-152">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="40383-152">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="40383-153">2.1</span><span class="sxs-lookup"><span data-stu-id="40383-153">2.1</span></span> |
| [<span data-ttu-id="40383-154">Wersje OpenSSL na macOS</span><span class="sxs-lookup"><span data-stu-id="40383-154">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="40383-155">2.1</span><span class="sxs-lookup"><span data-stu-id="40383-155">2.1</span></span> |
| [<span data-ttu-id="40383-156">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="40383-156">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="40383-157">1.0</span><span class="sxs-lookup"><span data-stu-id="40383-157">1.0</span></span> |
| [<span data-ttu-id="40383-158">Obsługa wyjątków uszkodzonego stanu procesu nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="40383-158">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="40383-159">1.0</span><span class="sxs-lookup"><span data-stu-id="40383-159">1.0</span></span> |
| [<span data-ttu-id="40383-160">Właściwości UriBuilder nie dołączają już znaków wiodących</span><span class="sxs-lookup"><span data-stu-id="40383-160">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="40383-161">1.0</span><span class="sxs-lookup"><span data-stu-id="40383-161">1.0</span></span> |
| [<span data-ttu-id="40383-162">Proces. element StartInfo zgłasza InvalidOperationException dla procesów, które nie zostały uruchomione</span><span class="sxs-lookup"><span data-stu-id="40383-162">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="40383-163">1.0</span><span class="sxs-lookup"><span data-stu-id="40383-163">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="40383-164">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="40383-164">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="40383-165">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="40383-165">.NET Core 3.0</span></span>

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

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="40383-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="40383-166">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="40383-167">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="40383-167">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
