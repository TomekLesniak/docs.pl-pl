---
title: Model kryptografii .NET
description: Przejrzyj implementacje zwykłych algorytmów kryptograficznych w programie .NET. Zapoznaj się z rozszerzalnym modelem kryptografii dziedziczenia obiektów, projektem strumienia i konfiguracją &.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: f9ec08992cb8db8f81f11de661612e1b7d15131c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831120"
---
# <a name="net-cryptography-model"></a>Model kryptografii .NET

Platforma .NET udostępnia implementacje wielu standardowych algorytmów kryptograficznych, a model kryptografii .NET jest rozszerzalny.

## <a name="object-inheritance"></a>Dziedziczenie obiektu

System kryptograficzny platformy .NET implementuje rozszerzalny wzorzec dziedziczenia klasy pochodnej. Hierarchia jest następująca:

- Klasa typu algorytmu, taka jak <xref:System.Security.Cryptography.SymmetricAlgorithm> ,  <xref:System.Security.Cryptography.AsymmetricAlgorithm> , lub <xref:System.Security.Cryptography.HashAlgorithm> . Ten poziom jest abstrakcyjny.

- Klasa algorytmu, która dziedziczy z klasy typu algorytmu; na przykład, <xref:System.Security.Cryptography.Aes> , <xref:System.Security.Cryptography.RSA> lub <xref:System.Security.Cryptography.ECDiffieHellman> . Ten poziom jest abstrakcyjny.

- Implementacja klasy algorytmu, która dziedziczy z klasy algorytmu; na przykład, <xref:System.Security.Cryptography.AesManaged> , <xref:System.Security.Cryptography.RC2CryptoServiceProvider> lub <xref:System.Security.Cryptography.ECDiffieHellmanCng> . Ten poziom jest w pełni zaimplementowany.

Ten wzorzec klas pochodnych pozwala dodać nowy algorytm lub nową implementację istniejącego algorytmu. Na przykład, aby utworzyć nowy algorytm klucza publicznego, można dziedziczyć z <xref:System.Security.Cryptography.AsymmetricAlgorithm> klasy. Aby utworzyć nową implementację określonego algorytmu, należy utworzyć nieabstrakcyjną klasę pochodną tego algorytmu.

## <a name="how-algorithms-are-implemented-in-net"></a>Jak zaimplementowane są algorytmy w programie .NET

Przykładem różnych implementacji dla algorytmu, należy wziąć pod uwagę Algorytmy symetryczne. Podstawą dla wszystkich algorytmów symetrycznych jest <xref:System.Security.Cryptography.SymmetricAlgorithm> , która jest dziedziczona przez <xref:System.Security.Cryptography.Aes> , <xref:System.Security.Cryptography.TripleDES> i inne, które nie są już zalecane.

<xref:System.Security.Cryptography.Aes> jest dziedziczona przez <xref:System.Security.Cryptography.AesCryptoServiceProvider> , <xref:System.Security.Cryptography.AesCng> , i <xref:System.Security.Cryptography.AesManaged> .

W .NET Framework w systemie Windows:

* `*CryptoServiceProvider` klasy algorytmu, takie jak <xref:System.Security.Cryptography.AesCryptoServiceProvider> , są otokami wokół implementacji algorytmu Windows CRYPTOGRAPHY API (CAPI).
* `*Cng` klasy algorytmu, takie jak <xref:System.Security.Cryptography.ECDiffieHellmanCng> , są otokami wokół implementacji Windows Cryptography Next Generation (CNG).
* `*Managed` klasy, takie jak <xref:System.Security.Cryptography.AesManaged> , są zapisywane w całości w kodzie zarządzanym. `*Managed` implementacje nie są certyfikowane przez standardy FIPS (Federal Information Processing Standards) i mogą być wolniejsze niż `*CryptoServiceProvider` `*Cng` klasy otoki i.

W przypadku programów .NET Core i .NET 5 i nowszych wersje wszystkie klasy implementacji ( `*CryptoServiceProvider` , `*Managed` i `*Cng` ) są otokami dla algorytmów systemu operacyjnego (OS). Jeśli algorytmy systemu operacyjnego są certyfikowane pod kątem zgodności ze standardem FIPS, .NET używa algorytmów certyfikowanych przez FIPS. Aby uzyskać więcej informacji, zobacz [Kryptografia międzyplatformowa](cross-platform-cryptography.md).

W większości przypadków nie trzeba bezpośrednio odwoływać się do klasy implementacji algorytmu, takiej jak `AesCryptoServiceProvider` . Metody i właściwości, które zazwyczaj są potrzebne, znajdują się w klasie algorytmu podstawowego, na przykład `Aes` . Utwórz wystąpienie domyślnej klasy implementacji przy użyciu metody fabryki w klasie algorytmu podstawowego i zapoznaj się z klasą algorytmu podstawowego. Na przykład zobacz wyróżniony wiersz kodu w następującym przykładzie:

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="16":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="12":::

## <a name="cryptographic-configuration"></a>Konfiguracja kryptograficzna

Konfiguracja kryptograficzna pozwala rozwiązać konkretną implementację algorytmu do nazwy algorytmu, umożliwiając rozszerzanie klas kryptografii platformy .NET. Możesz dodać własną implementację sprzętu lub oprogramowania do algorytmu i zmapować implementację do wybranej nazwy algorytmu. Jeśli w pliku konfiguracji nie określono algorytmu, zostaną użyte ustawienia domyślne.

## <a name="choosing-an-algorithm"></a>Wybieranie algorytmu

Istnieje możliwość wybrania algorytmu z różnych przyczyn: na przykład w celu zapewnienia integralności danych lub wygenerowania klucza. Algorytmy symetryczne i hash są przeznaczone do ochrony danych z powodów związanych z integralnością (ochrona przed zmianami) lub z przyczyn zachowania poufności informacji (ochrona przed wyświetlaniem). Algorytmy wyznaczania wartości skrótu są używane głównie w celu zapewnienia integralności danych.

Poniżej znajduje się lista zalecanych algorytmów według aplikacji:

- Prywatność danych:
  - <xref:System.Security.Cryptography.Aes>
- Integralność danych:
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- Podpis cyfrowy:
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- Wymiana kluczy:
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- Generowanie liczb losowych:
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- Generowanie klucza przy użyciu hasła:
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a>Zobacz także

- [Usługi kryptograficzne](cryptographic-services.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
