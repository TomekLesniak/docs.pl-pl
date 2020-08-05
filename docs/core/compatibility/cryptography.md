---
title: Krytyczne zmiany kryptografii
description: Wyświetla listę istotnych zmian związanych z kryptografią w programie .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: 34098027c4cbe5e5fb31a22d981af706e07cb7da
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556032"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="23cae-103">Krytyczne zmiany kryptografii</span><span class="sxs-lookup"><span data-stu-id="23cae-103">Cryptography breaking changes</span></span>

<span data-ttu-id="23cae-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="23cae-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="23cae-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="23cae-105">Breaking change</span></span> | <span data-ttu-id="23cae-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="23cae-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="23cae-107">Rozpocznij składnię ZAUFANEgo certyfikatu nie jest już obsługiwana w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="23cae-107">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="23cae-108">3.0</span><span class="sxs-lookup"><span data-stu-id="23cae-108">3.0</span></span> |
| [<span data-ttu-id="23cae-109">EnvelopedCms domyślnie szyfrowanie AES-256</span><span class="sxs-lookup"><span data-stu-id="23cae-109">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="23cae-110">3.0</span><span class="sxs-lookup"><span data-stu-id="23cae-110">3.0</span></span> |
| [<span data-ttu-id="23cae-111">Zwiększono minimalny rozmiar generowania klucza RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="23cae-111">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="23cae-112">3.0</span><span class="sxs-lookup"><span data-stu-id="23cae-112">3.0</span></span> |
| [<span data-ttu-id="23cae-113">.NET Core 3,0 preferuje OpenSSL 1.1. x do OpenSSL 1.0. x</span><span class="sxs-lookup"><span data-stu-id="23cae-113">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="23cae-114">3.0</span><span class="sxs-lookup"><span data-stu-id="23cae-114">3.0</span></span> |
| [<span data-ttu-id="23cae-115">Parametr logiczny elementu SignedCms. ComputeSignature jest przestrzegany</span><span class="sxs-lookup"><span data-stu-id="23cae-115">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="23cae-116">2.1</span><span class="sxs-lookup"><span data-stu-id="23cae-116">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="23cae-117">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="23cae-117">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="23cae-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="23cae-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
