---
title: Podstawowe zmiany w bibliotece klas podstawowych
description: Wyświetla istotne zmiany w podstawowych bibliotekach programu .NET.
ms.date: 07/27/2020
ms.openlocfilehash: d474d5547245e57206d669531b74b5be31c98ca0
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556340"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="cbd45-103">Podstawowe zmiany w bibliotekach .NET</span><span class="sxs-lookup"><span data-stu-id="cbd45-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="cbd45-104">Podstawowe biblioteki .NET zapewniają pierwotne i inne typy ogólne używane przez platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cbd45-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="cbd45-105">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="cbd45-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cbd45-106">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="cbd45-106">Breaking change</span></span> | <span data-ttu-id="cbd45-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="cbd45-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cbd45-108">PrincipalPermissionAttribute jest przestarzały jako błąd</span><span class="sxs-lookup"><span data-stu-id="cbd45-108">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="cbd45-109">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-109">5.0</span></span> |
| [<span data-ttu-id="cbd45-110">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cbd45-110">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="cbd45-111">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-111">5.0</span></span> |
| [<span data-ttu-id="cbd45-112">Ścieżki kodu UTF-7 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="cbd45-112">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="cbd45-113">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-113">5.0</span></span> |
| [<span data-ttu-id="cbd45-114">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="cbd45-114">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="cbd45-115">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-115">5.0</span></span> |
| [<span data-ttu-id="cbd45-116">ActivityIdFormat domyślny to W3C</span><span class="sxs-lookup"><span data-stu-id="cbd45-116">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="cbd45-117">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-117">5.0</span></span> |
| [<span data-ttu-id="cbd45-118">Zmiana zachowania dla Vector2. Lerp i Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="cbd45-118">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="cbd45-119">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-119">5.0</span></span> |
| [<span data-ttu-id="cbd45-120">Metody SSE i SSE2 CompareGreaterThan prawidłowo obsługują dane wejściowe NaN</span><span class="sxs-lookup"><span data-stu-id="cbd45-120">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="cbd45-121">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-121">5.0</span></span> |
| [<span data-ttu-id="cbd45-122">Element CounterSet. CreateCounterSetInstance teraz zgłasza InvalidOperationException, jeśli wystąpienie już istnieje</span><span class="sxs-lookup"><span data-stu-id="cbd45-122">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="cbd45-123">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-123">5.0</span></span> |
| [<span data-ttu-id="cbd45-124">Usunięto pakiet Microsoft. DotNet. PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="cbd45-124">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="cbd45-125">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-125">5.0</span></span> |
| [<span data-ttu-id="cbd45-126">Interfejsy API służące do raportowania wersji teraz produktu i nie wersji</span><span class="sxs-lookup"><span data-stu-id="cbd45-126">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="cbd45-127">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-127">3.0</span></span> |
| [<span data-ttu-id="cbd45-128">Niestandardowe wystąpienia EncoderFallbackBuffer nie mogą podlegać rekursywnie</span><span class="sxs-lookup"><span data-stu-id="cbd45-128">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="cbd45-129">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-129">3.0</span></span> |
| [<span data-ttu-id="cbd45-130">Zmiany zachowań formatowania zmiennoprzecinkowego i analizowania</span><span class="sxs-lookup"><span data-stu-id="cbd45-130">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="cbd45-131">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-131">3.0</span></span> |
| [<span data-ttu-id="cbd45-132">Operacje analizowania zmiennoprzecinkowe nie będą już kończyć się niepowodzeniem lub nie generują wyjątku overflow</span><span class="sxs-lookup"><span data-stu-id="cbd45-132">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="cbd45-133">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-133">3.0</span></span> |
| [<span data-ttu-id="cbd45-134">InvalidAsynchronousStateException — przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="cbd45-134">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="cbd45-135">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-135">3.0</span></span> |
| [<span data-ttu-id="cbd45-136">Zastępowanie źle sformułowanych sekwencji bajtów w formacie UTF-8 następuje po wskazówkach dotyczących standardu Unicode</span><span class="sxs-lookup"><span data-stu-id="cbd45-136">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="cbd45-137">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-137">3.0</span></span> |
| [<span data-ttu-id="cbd45-138">TypeDescriptionProviderAttribute przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="cbd45-138">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="cbd45-139">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-139">3.0</span></span> |
| [<span data-ttu-id="cbd45-140">Element ZipArchiveEntry nie obsługuje już archiwów z niespójnymi rozmiarami wpisów</span><span class="sxs-lookup"><span data-stu-id="cbd45-140">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="cbd45-141">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-141">3.0</span></span> |
| [<span data-ttu-id="cbd45-142">Element FieldInfo. SetValue zgłasza wyjątek dla pól static, tylko init</span><span class="sxs-lookup"><span data-stu-id="cbd45-142">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="cbd45-143">3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-143">3.0</span></span> |
| [<span data-ttu-id="cbd45-144">Pola prywatne dodane do wbudowanych typów struktur</span><span class="sxs-lookup"><span data-stu-id="cbd45-144">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="cbd45-145">2.1</span><span class="sxs-lookup"><span data-stu-id="cbd45-145">2.1</span></span> |
| [<span data-ttu-id="cbd45-146">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="cbd45-146">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="cbd45-147">2.1</span><span class="sxs-lookup"><span data-stu-id="cbd45-147">2.1</span></span> |
| [<span data-ttu-id="cbd45-148">Wersje OpenSSL na macOS</span><span class="sxs-lookup"><span data-stu-id="cbd45-148">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="cbd45-149">2.1</span><span class="sxs-lookup"><span data-stu-id="cbd45-149">2.1</span></span> |
| [<span data-ttu-id="cbd45-150">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="cbd45-150">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="cbd45-151">1.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-151">1.0</span></span> |
| [<span data-ttu-id="cbd45-152">Obsługa wyjątków uszkodzonego stanu procesu nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="cbd45-152">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="cbd45-153">1.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-153">1.0</span></span> |
| [<span data-ttu-id="cbd45-154">Właściwości UriBuilder nie dołączają już znaków wiodących</span><span class="sxs-lookup"><span data-stu-id="cbd45-154">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="cbd45-155">1.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-155">1.0</span></span> |
| [<span data-ttu-id="cbd45-156">Proces. element StartInfo zgłasza InvalidOperationException dla procesów, które nie zostały uruchomione</span><span class="sxs-lookup"><span data-stu-id="cbd45-156">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="cbd45-157">1.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-157">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="cbd45-158">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="cbd45-158">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="cbd45-159">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cbd45-159">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="cbd45-160">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cbd45-160">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="cbd45-161">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="cbd45-161">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
