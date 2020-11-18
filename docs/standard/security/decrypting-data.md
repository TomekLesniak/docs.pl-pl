---
title: Odszyfrowywanie danych
description: Dowiedz się, jak odszyfrować dane w programie .NET przy użyciu algorytmu symetrycznego lub algorytmu asymetrycznego.
ms.date: 07/16/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: cf286eeca8a9372c6532c56701e4775d5e09d786
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831107"
---
# <a name="decrypting-data"></a>Odszyfrowywanie danych

Odszyfrowywanie jest odwrotną operacją szyfrowania. W przypadku szyfrowania klucza tajnego należy znać zarówno klucz, jak i IV, które były używane do szyfrowania danych. W przypadku szyfrowania klucza publicznego należy znać klucz publiczny (Jeśli dane zostały zaszyfrowane przy użyciu klucza prywatnego) lub klucza prywatnego (Jeśli dane zostały zaszyfrowane przy użyciu klucza publicznego).

## <a name="symmetric-decryption"></a>Odszyfrowywanie symetryczne

Odszyfrowywanie danych szyfrowanych za pomocą algorytmów symetrycznych jest podobne do procesu używanego do szyfrowania danych za pomocą algorytmów symetrycznych. <xref:System.Security.Cryptography.CryptoStream>Klasa jest używana z symetrycznymi klasami kryptografii udostępnianymi przez platformę .NET do odszyfrowywania danych odczytanych z dowolnego zarządzanego obiektu strumienia.

Poniższy przykład ilustruje sposób tworzenia nowego wystąpienia domyślnej klasy implementacji dla <xref:System.Security.Cryptography.Aes> algorytmu. To wystąpienie jest używane do wykonania odszyfrowywania w <xref:System.Security.Cryptography.CryptoStream> obiekcie. Ten przykład najpierw tworzy nowe wystąpienie <xref:System.Security.Cryptography.Aes> klasy implementacji. Odczytuje wartość Vector inicjującą (IV) z zarządzanej zmiennej strumienia `myStream` . Następnie tworzy wystąpienie <xref:System.Security.Cryptography.CryptoStream> obiektu i inicjuje go dla wartości `myStream` wystąpienia. <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType>Metoda z <xref:System.Security.Cryptography.Aes> wystąpienia jest przenoszona wartość IV i ten sam klucz, który był używany do szyfrowania.

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

Poniższy przykład pokazuje cały proces tworzenia strumienia, odszyfrowywania strumienia, odczytywania ze strumienia i zamykania strumieni. Tworzony jest obiekt strumienia pliku, który odczytuje plik o nazwie *TestData.txt*. Strumień pliku jest następnie odszyfrowywany przy użyciu klasy **CryptoStream** i **AES** . Ten przykład określa wartość klucza, która jest używana w przykładzie szyfrowania symetrycznego do [szyfrowania danych](encrypting-data.md). Nie jest wyświetlany kod wymagany do szyfrowania i transferu tych wartości.

:::code language="csharp" source="snippets/decrypting-data/csharp/aes-decrypt.cs":::
:::code language="vb" source="snippets/decrypting-data/vb/aes-decrypt.vb":::

W poprzednim przykładzie użyto tego samego klucza, a algorytm używany w przykładzie szyfrowania symetrycznego do [szyfrowania danych](encrypting-data.md). Odszyfrowuje plik *TestData.txt* , który jest tworzony przez ten przykład, i wyświetla oryginalny tekst w konsoli programu.

## <a name="asymmetric-decryption"></a>Odszyfrowywanie asymetryczne

Zazwyczaj strona (Strona A) generuje zarówno klucz publiczny, jak i prywatny, a klucz jest przechowywany w pamięci lub w kontenerze kluczy kryptograficznych. Następnie firma A następnie wysyła klucz publiczny do innej strony (strona B). Przy użyciu klucza publicznego Strona B szyfruje dane i wysyła je z powrotem do strony A. Po odebraniu danych firma odszyfruje je przy użyciu klucza prywatnego, który odpowiada. Odszyfrowywanie powiedzie się tylko wtedy, gdy strona A używa klucza prywatnego, który odpowiada stronie klucza publicznego, który jest używany do szyfrowania danych.

Aby uzyskać informacje na temat sposobu przechowywania klucza asymetrycznego w bezpiecznym kontenerze kluczy kryptograficznych i sposobie późniejszego pobierania klucza asymetrycznego, zobacz [How to: Store asymetryczne klucze w kontenerze kluczy](how-to-store-asymmetric-keys-in-a-key-container.md).

Poniższy przykład ilustruje odszyfrowywanie dwóch tablic bajtów reprezentujących klucz symetryczny i IV. Aby uzyskać informacje na temat sposobu wyodrębniania asymetrycznego klucza publicznego z <xref:System.Security.Cryptography.RSA> obiektu w formacie, który można łatwo przesłać do innej firmy, zobacz [szyfrowanie danych](encrypting-data.md).

```vb
'Create a new instance of the RSA class.
Dim rsa As RSA = RSA.Create()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, RSAEncryptionPadding.Pkcs1)
```

```csharp
//Create a new instance of the RSA class.
RSA rsa = RSA.Create();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , RSAEncryptionPadding.Pkcs1);
```

## <a name="see-also"></a>Zobacz także

- [Generowanie kluczy szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md)
- [Szyfrowanie danych](encrypting-data.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Model kryptografii](cryptography-model.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- [Luki w zabezpieczeniach chronometrażu z odszyfrowywaniem symetrycznym w trybie CBC przy użyciu uzupełnienia](vulnerabilities-cbc-mode.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
