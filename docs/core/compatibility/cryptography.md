---
title: Krytyczne zmiany kryptografii
description: Wyświetla listę istotnych zmian związanych z kryptografią w programie .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: c9405625cc4075c05468dc9b8502bf8c76587bad
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997744"
---
# <a name="cryptography-breaking-changes"></a>Krytyczne zmiany kryptografii

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | :-: |
| [Domyślne mechanizmy szyfrowania TLS dla platformy .NET w systemie Linux](#default-tls-cipher-suites-for-net-on-linux) | 5,0 |
| [Interfejsy API System. Security. Cryptography nie są obsługiwane w zestawie webassembly Blazor](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | 5,0 |
| [System. Security. Cryptography. OID jest funkcjonalnie init-Only](#systemsecuritycryptographyoid-is-functionally-init-only) | 5,0 |
| [Rozpocznij składnię ZAUFANEgo certyfikatu nie jest już obsługiwana w systemie Linux](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | 3,0 |
| [EnvelopedCms domyślnie szyfrowanie AES-256](#envelopedcms-defaults-to-aes-256-encryption) | 3,0 |
| [Zwiększono minimalny rozmiar generowania klucza RSAOpenSsl](#minimum-size-for-rsaopenssl-key-generation-has-increased) | 3,0 |
| [.NET Core 3,0 preferuje OpenSSL 1.1. x do OpenSSL 1.0. x](#net-core-30-prefers-openssl-11x-to-openssl-10x) | 3,0 |
| [CryptoStream. Dispose przekształca końcowy blok tylko podczas pisania](#cryptostreamdispose-transforms-final-block-only-when-writing) | 3,0 |
| [Parametr logiczny elementu SignedCms. ComputeSignature jest przestrzegany](#boolean-parameter-of-signedcmscomputesignature-is-respected) | 2.1 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [default-cipher-suites-for-tls-on-linux](../../../includes/core-changes/cryptography/5.0/default-cipher-suites-for-tls-on-linux.md)]

***

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

***

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
