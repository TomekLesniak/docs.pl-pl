---
title: Krytyczne zmiany kryptografii
description: Wyświetla listę istotnych zmian związanych z kryptografią w programie .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: b755876624a7709cfe08b5993655e78be9f8e1f2
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888616"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="31fc5-103">Krytyczne zmiany kryptografii</span><span class="sxs-lookup"><span data-stu-id="31fc5-103">Cryptography breaking changes</span></span>

<span data-ttu-id="31fc5-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="31fc5-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="31fc5-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="31fc5-105">Breaking change</span></span> | <span data-ttu-id="31fc5-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="31fc5-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="31fc5-107">Domyślna wartość FeedbackSize dla wystąpień utworzonych przez TripleDES. Create zmieniony</span><span class="sxs-lookup"><span data-stu-id="31fc5-107">Default FeedbackSize value for instances created by TripleDES.Create changed</span></span>](#default-feedbacksize-value-for-instances-created-by-tripledescreate-changed) | <span data-ttu-id="31fc5-108">5,0</span><span class="sxs-lookup"><span data-stu-id="31fc5-108">5.0</span></span> |
| [<span data-ttu-id="31fc5-109">Tworzenie wystąpienia domyślnych metod abstrakcyjnych nie jest obsługiwane</span><span class="sxs-lookup"><span data-stu-id="31fc5-109">Instantiating default implementations of cryptographic abstractions is not supported</span></span>](#instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported) | <span data-ttu-id="31fc5-110">5,0</span><span class="sxs-lookup"><span data-stu-id="31fc5-110">5.0</span></span> |
| [<span data-ttu-id="31fc5-111">Domyślne mechanizmy szyfrowania TLS dla platformy .NET w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="31fc5-111">Default TLS cipher suites for .NET on Linux</span></span>](#default-tls-cipher-suites-for-net-on-linux) | <span data-ttu-id="31fc5-112">5,0</span><span class="sxs-lookup"><span data-stu-id="31fc5-112">5.0</span></span> |
| [<span data-ttu-id="31fc5-113">Interfejsy API System. Security. Cryptography nie są obsługiwane w zestawie webassembly Blazor</span><span class="sxs-lookup"><span data-stu-id="31fc5-113">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | <span data-ttu-id="31fc5-114">5,0</span><span class="sxs-lookup"><span data-stu-id="31fc5-114">5.0</span></span> |
| [<span data-ttu-id="31fc5-115">System. Security. Cryptography. OID jest funkcjonalnie init-Only</span><span class="sxs-lookup"><span data-stu-id="31fc5-115">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="31fc5-116">5,0</span><span class="sxs-lookup"><span data-stu-id="31fc5-116">5.0</span></span> |
| [<span data-ttu-id="31fc5-117">Rozpocznij składnię ZAUFANEgo certyfikatu nie jest już obsługiwana w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="31fc5-117">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="31fc5-118">3.0</span><span class="sxs-lookup"><span data-stu-id="31fc5-118">3.0</span></span> |
| [<span data-ttu-id="31fc5-119">EnvelopedCms domyślnie szyfrowanie AES-256</span><span class="sxs-lookup"><span data-stu-id="31fc5-119">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="31fc5-120">3.0</span><span class="sxs-lookup"><span data-stu-id="31fc5-120">3.0</span></span> |
| [<span data-ttu-id="31fc5-121">Zwiększono minimalny rozmiar generowania klucza RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="31fc5-121">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="31fc5-122">3.0</span><span class="sxs-lookup"><span data-stu-id="31fc5-122">3.0</span></span> |
| [<span data-ttu-id="31fc5-123">.NET Core 3,0 preferuje OpenSSL 1.1. x do OpenSSL 1.0. x</span><span class="sxs-lookup"><span data-stu-id="31fc5-123">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="31fc5-124">3.0</span><span class="sxs-lookup"><span data-stu-id="31fc5-124">3.0</span></span> |
| [<span data-ttu-id="31fc5-125">CryptoStream. Dispose przekształca końcowy blok tylko podczas pisania</span><span class="sxs-lookup"><span data-stu-id="31fc5-125">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="31fc5-126">3.0</span><span class="sxs-lookup"><span data-stu-id="31fc5-126">3.0</span></span> |
| [<span data-ttu-id="31fc5-127">Parametr logiczny elementu SignedCms. ComputeSignature jest przestrzegany</span><span class="sxs-lookup"><span data-stu-id="31fc5-127">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="31fc5-128">2.1</span><span class="sxs-lookup"><span data-stu-id="31fc5-128">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="31fc5-129">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="31fc5-129">.NET 5.0</span></span>

[!INCLUDE [tripledes-default-feedback-size-change](../../../includes/core-changes/cryptography/5.0/tripledes-default-feedback-size-change.md)]

***

[!INCLUDE [instantiating-default-implementations-of-cryptographic-abstractions-not-supported](../../../includes/core-changes/cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)]

<span data-ttu-id="31fc5-130">\*\*_</span><span class="sxs-lookup"><span data-stu-id="31fc5-130">\*\*_</span></span>

[!INCLUDE [default-cipher-suites-for-tls-on-linux](../../../includes/core-changes/cryptography/5.0/default-cipher-suites-for-tls-on-linux.md)]

_*_

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

_*_

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="31fc5-131">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="31fc5-131">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

_*_

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

_*_

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

_*_

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

_*_

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="31fc5-132">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="31fc5-132">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

<span data-ttu-id="31fc5-133">_\*\*</span><span class="sxs-lookup"><span data-stu-id="31fc5-133">_\*\*</span></span>
