---
title: Krytyczne zmiany kryptografii
description: Wyświetla listę istotnych zmian związanych z kryptografią w programie .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: 6f37e5caacadc276562e63a728162c6b26f2e435
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159559"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="5f9cb-103">Krytyczne zmiany kryptografii</span><span class="sxs-lookup"><span data-stu-id="5f9cb-103">Cryptography breaking changes</span></span>

<span data-ttu-id="5f9cb-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="5f9cb-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="5f9cb-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="5f9cb-105">Breaking change</span></span> | <span data-ttu-id="5f9cb-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="5f9cb-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="5f9cb-107">Tworzenie wystąpienia domyślnych metod abstrakcyjnych nie jest obsługiwane</span><span class="sxs-lookup"><span data-stu-id="5f9cb-107">Instantiating default implementations of cryptographic abstractions is not supported</span></span>](#instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported) | <span data-ttu-id="5f9cb-108">5,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-108">5.0</span></span> |
| [<span data-ttu-id="5f9cb-109">Domyślne mechanizmy szyfrowania TLS dla platformy .NET w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="5f9cb-109">Default TLS cipher suites for .NET on Linux</span></span>](#default-tls-cipher-suites-for-net-on-linux) | <span data-ttu-id="5f9cb-110">5,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-110">5.0</span></span> |
| [<span data-ttu-id="5f9cb-111">Interfejsy API System. Security. Cryptography nie są obsługiwane w zestawie webassembly Blazor</span><span class="sxs-lookup"><span data-stu-id="5f9cb-111">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | <span data-ttu-id="5f9cb-112">5,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-112">5.0</span></span> |
| [<span data-ttu-id="5f9cb-113">System. Security. Cryptography. OID jest funkcjonalnie init-Only</span><span class="sxs-lookup"><span data-stu-id="5f9cb-113">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="5f9cb-114">5,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-114">5.0</span></span> |
| [<span data-ttu-id="5f9cb-115">Rozpocznij składnię ZAUFANEgo certyfikatu nie jest już obsługiwana w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="5f9cb-115">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="5f9cb-116">3,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-116">3.0</span></span> |
| [<span data-ttu-id="5f9cb-117">EnvelopedCms domyślnie szyfrowanie AES-256</span><span class="sxs-lookup"><span data-stu-id="5f9cb-117">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="5f9cb-118">3,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-118">3.0</span></span> |
| [<span data-ttu-id="5f9cb-119">Zwiększono minimalny rozmiar generowania klucza RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="5f9cb-119">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="5f9cb-120">3,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-120">3.0</span></span> |
| [<span data-ttu-id="5f9cb-121">.NET Core 3,0 preferuje OpenSSL 1.1. x do OpenSSL 1.0. x</span><span class="sxs-lookup"><span data-stu-id="5f9cb-121">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="5f9cb-122">3,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-122">3.0</span></span> |
| [<span data-ttu-id="5f9cb-123">CryptoStream. Dispose przekształca końcowy blok tylko podczas pisania</span><span class="sxs-lookup"><span data-stu-id="5f9cb-123">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="5f9cb-124">3,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-124">3.0</span></span> |
| [<span data-ttu-id="5f9cb-125">Parametr logiczny elementu SignedCms. ComputeSignature jest przestrzegany</span><span class="sxs-lookup"><span data-stu-id="5f9cb-125">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="5f9cb-126">2.1</span><span class="sxs-lookup"><span data-stu-id="5f9cb-126">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="5f9cb-127">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-127">.NET 5.0</span></span>

[!INCLUDE [instantiating-default-implementations-of-cryptographic-abstractions-not-supported](../../../includes/core-changes/cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)]

***

[!INCLUDE [default-cipher-suites-for-tls-on-linux](../../../includes/core-changes/cryptography/5.0/default-cipher-suites-for-tls-on-linux.md)]

***

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

***

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="5f9cb-128">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5f9cb-128">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="5f9cb-129">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5f9cb-129">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
