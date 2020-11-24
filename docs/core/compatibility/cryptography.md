---
title: Krytyczne zmiany kryptografii
description: Wyświetla listę istotnych zmian związanych z kryptografią w programie .NET Core 2.1-3.0.
ms.date: 04/22/2020
ms.openlocfilehash: a4801bb4d5a859e2c8c2b536ee0597cb4db2f65d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682656"
---
# <a name="cryptography-breaking-changes-for-net-core-21-30"></a><span data-ttu-id="eb47a-103">Krytyczne zmiany kryptografii dla platformy .NET Core 2.1-3.0</span><span class="sxs-lookup"><span data-stu-id="eb47a-103">Cryptography breaking changes for .NET Core 2.1-3.0</span></span>

<span data-ttu-id="eb47a-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="eb47a-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="eb47a-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="eb47a-105">Breaking change</span></span> | <span data-ttu-id="eb47a-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="eb47a-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="eb47a-107">Rozpocznij składnię ZAUFANEgo certyfikatu nie jest już obsługiwana w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="eb47a-107">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="eb47a-108">3.0</span><span class="sxs-lookup"><span data-stu-id="eb47a-108">3.0</span></span> |
| [<span data-ttu-id="eb47a-109">EnvelopedCms domyślnie szyfrowanie AES-256</span><span class="sxs-lookup"><span data-stu-id="eb47a-109">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="eb47a-110">3.0</span><span class="sxs-lookup"><span data-stu-id="eb47a-110">3.0</span></span> |
| [<span data-ttu-id="eb47a-111">Zwiększono minimalny rozmiar generowania klucza RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="eb47a-111">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="eb47a-112">3.0</span><span class="sxs-lookup"><span data-stu-id="eb47a-112">3.0</span></span> |
| [<span data-ttu-id="eb47a-113">.NET Core 3,0 preferuje OpenSSL 1.1. x do OpenSSL 1.0. x</span><span class="sxs-lookup"><span data-stu-id="eb47a-113">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="eb47a-114">3.0</span><span class="sxs-lookup"><span data-stu-id="eb47a-114">3.0</span></span> |
| [<span data-ttu-id="eb47a-115">CryptoStream. Dispose przekształca końcowy blok tylko podczas pisania</span><span class="sxs-lookup"><span data-stu-id="eb47a-115">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="eb47a-116">3.0</span><span class="sxs-lookup"><span data-stu-id="eb47a-116">3.0</span></span> |
| [<span data-ttu-id="eb47a-117">Parametr logiczny elementu SignedCms. ComputeSignature jest przestrzegany</span><span class="sxs-lookup"><span data-stu-id="eb47a-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="eb47a-118">2.1</span><span class="sxs-lookup"><span data-stu-id="eb47a-118">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="eb47a-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="eb47a-119">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

<span data-ttu-id="eb47a-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="eb47a-120">\*\*_</span></span>

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

_*_

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

_*_

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="eb47a-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="eb47a-121">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

<span data-ttu-id="eb47a-122">_\*\*</span><span class="sxs-lookup"><span data-stu-id="eb47a-122">_\*\*</span></span>
