---
title: Krytyczne zmiany kryptografii
description: Wyświetla listę istotnych zmian związanych z kryptografią w programie .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: 621a3dad28b67ee33056dce3df0379efaeb90776
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065110"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="112e4-103">Krytyczne zmiany kryptografii</span><span class="sxs-lookup"><span data-stu-id="112e4-103">Cryptography breaking changes</span></span>

<span data-ttu-id="112e4-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="112e4-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="112e4-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="112e4-105">Breaking change</span></span> | <span data-ttu-id="112e4-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="112e4-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="112e4-107">System. Security. Cryptography. OID jest funkcjonalnie init-Only</span><span class="sxs-lookup"><span data-stu-id="112e4-107">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="112e4-108">5,0</span><span class="sxs-lookup"><span data-stu-id="112e4-108">5.0</span></span> |
| [<span data-ttu-id="112e4-109">Rozpocznij składnię ZAUFANEgo certyfikatu nie jest już obsługiwana w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="112e4-109">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="112e4-110">3,0</span><span class="sxs-lookup"><span data-stu-id="112e4-110">3.0</span></span> |
| [<span data-ttu-id="112e4-111">EnvelopedCms domyślnie szyfrowanie AES-256</span><span class="sxs-lookup"><span data-stu-id="112e4-111">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="112e4-112">3,0</span><span class="sxs-lookup"><span data-stu-id="112e4-112">3.0</span></span> |
| [<span data-ttu-id="112e4-113">Zwiększono minimalny rozmiar generowania klucza RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="112e4-113">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="112e4-114">3,0</span><span class="sxs-lookup"><span data-stu-id="112e4-114">3.0</span></span> |
| [<span data-ttu-id="112e4-115">.NET Core 3,0 preferuje OpenSSL 1.1. x do OpenSSL 1.0. x</span><span class="sxs-lookup"><span data-stu-id="112e4-115">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="112e4-116">3,0</span><span class="sxs-lookup"><span data-stu-id="112e4-116">3.0</span></span> |
| [<span data-ttu-id="112e4-117">CryptoStream. Dispose przekształca końcowy blok tylko podczas pisania</span><span class="sxs-lookup"><span data-stu-id="112e4-117">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="112e4-118">3,0</span><span class="sxs-lookup"><span data-stu-id="112e4-118">3.0</span></span> |
| [<span data-ttu-id="112e4-119">Parametr logiczny elementu SignedCms. ComputeSignature jest przestrzegany</span><span class="sxs-lookup"><span data-stu-id="112e4-119">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="112e4-120">2.1</span><span class="sxs-lookup"><span data-stu-id="112e4-120">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="112e4-121">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="112e4-121">.NET 5.0</span></span>

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="112e4-122">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="112e4-122">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="112e4-123">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="112e4-123">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
