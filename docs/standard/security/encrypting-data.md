---
title: Szyfrowanie danych
description: Dowiedz się, jak szyfrować dane w programie .NET przy użyciu algorytmu symetrycznego lub algorytmu asymetrycznego.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], symmetric
- symmetric encryption
- cryptography [.NET], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 8a8b5988a13ab571284b08c7aaece3542467aa71
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556972"
---
# <a name="encrypting-data"></a>Szyfrowanie danych

Szyfrowanie symetryczne i szyfrowanie asymetryczne są wykonywane przy użyciu różnych procesów. Szyfrowanie symetryczne jest wykonywane na strumieniach i dlatego jest przydatne do szyfrowania dużych ilości danych. Szyfrowanie asymetryczne jest wykonywane w niewielkiej liczbie bajtów i dlatego jest przydatne tylko w przypadku małych ilości danych.  
  
## <a name="symmetric-encryption"></a>Szyfrowanie symetryczne  

Zarządzane klasy kryptografii symetrycznej są używane z specjalną klasą strumienia o nazwie a <xref:System.Security.Cryptography.CryptoStream> , która szyfruje dane odczytane do strumienia. Klasa **CryptoStream** jest inicjowana za pomocą zarządzanej klasy strumienia, klasy implementującej <xref:System.Security.Cryptography.ICryptoTransform> interfejs (utworzony na podstawie klasy implementującej algorytm kryptograficzny) i <xref:System.Security.Cryptography.CryptoStreamMode> wyliczenia opisującego typ dostępu, który jest dozwolony dla **CryptoStream**. Klasę **CryptoStream** można zainicjować przy użyciu dowolnej klasy, która dziedziczy z <xref:System.IO.Stream> klasy, w tym <xref:System.IO.FileStream> , <xref:System.IO.MemoryStream> , i <xref:System.Net.Sockets.NetworkStream> . Za pomocą tych klas można wykonać szyfrowanie symetryczne na różnych obiektach strumienia.  
  
Poniższy przykład ilustruje sposób tworzenia nowego wystąpienia domyślnej klasy implementacji dla <xref:System.Security.Cryptography.Aes> algorytmu. To wystąpienie jest używane do wykonywania szyfrowania na klasie **CryptoStream** . W tym przykładzie **CryptoStream** jest inicjowany przy użyciu obiektu Stream o nazwie `myStream` , który może być dowolnym typem strumienia zarządzanego. Metoda **coclass** z klasy **AES** jest przenoszona z klucza i IV, który jest używany do szyfrowania. W takim przypadku użyto klucza domyślnego i dodatku IV wygenerowanego z `aes` .
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
Po wykonaniu tego kodu wszystkie dane zapisywane w obiekcie **CryptoStream** są szyfrowane przy użyciu algorytmu AES.  
  
Poniższy przykład pokazuje cały proces tworzenia strumienia, szyfrowania strumienia, zapisywania do strumienia i zamykania strumienia. W tym przykładzie tworzony jest strumień plików zaszyfrowany przy użyciu klasy **CryptoStream** i klasy **AES** . Wiadomość jest zapisywana w zaszyfrowanym strumieniu z <xref:System.IO.StreamWriter> klasą.
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

Kod szyfruje strumień przy użyciu algorytmu symetrycznego AES i zapisuje "Hello world!" do strumienia. Jeśli kod zakończy się pomyślnie, tworzy zaszyfrowany plik o nazwie *TestData.txt* i wyświetla następujący tekst w konsoli programu:  
  
```console  
The text was encrypted.  
```  

Plik można odszyfrować przy użyciu przykładu szyfrowania symetrycznego w [odszyfrowaniu danych](decrypting-data.md). Ten przykład i ten przykład określa ten sam klucz i IV.

Jeśli jednak występuje wyjątek, kod wyświetla następujący tekst w konsoli programu:  
  
```console  
The encryption failed.  
```

## <a name="asymmetric-encryption"></a>Szyfrowanie asymetryczne

Algorytmy asymetryczne są zwykle używane do szyfrowania małych ilości danych, takich jak szyfrowanie klucza symetrycznego i IV. Zazwyczaj pojedyncze wykonywanie szyfrowania asymetrycznego używa klucza publicznego wygenerowanego przez inną firmę. W <xref:System.Security.Cryptography.RSA> tym celu Klasa jest udostępniana przez platformę .NET.  
  
Poniższy przykład używa informacji o kluczu publicznym do szyfrowania klucza symetrycznego i IV. Są inicjowane dwubajtowe tablice reprezentujące klucz publiczny strony trzeciej. <xref:System.Security.Cryptography.RSAParameters>Obiekt jest zainicjowany do tych wartości. Następnie obiekt **RSAParameters** (wraz z kluczem publicznym, który reprezentuje) jest zaimportowany do wystąpienia **RSA** przy użyciu <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> metody. Na koniec kluczem prywatnym i IV tworzonym przez <xref:System.Security.Cryptography.Aes> klasę są szyfrowane. Ten przykład wymaga, aby systemy miały zainstalowane szyfrowanie 128-bitowe.  
  
```vb  
Imports System
Imports System.Security.Cryptography

Module Module1

    Sub Main()
        'Initialize the byte arrays to the public key information.  
        Dim modulus As Byte() = {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19, 202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}

        Dim exponent As Byte() = {1, 0, 1}

        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte
        Dim encryptedSymmetricIV() As Byte

        'Create a new instance of the default RSA implementation class.
        Dim rsa As RSA = RSA.Create()

        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()

        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus
        rsaKeyInfo.Exponent = exponent

        'Import key parameters into rsa
        rsa.ImportParameters(rsaKeyInfo)

        'Create a new instance of the default Aes implementation class.  
        Dim aes As Aes = Aes.Create()

        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1)
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1)
    End Sub

End Module
```  
  
```csharp  
using System;
using System.Security.Cryptography;

class Class1
{
    static void Main()
    {
        //Initialize the byte arrays to the public key information.  
        byte[] modulus = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};

        byte[] exponent = { 1, 0, 1 };

        //Create values to store encrypted symmetric keys.  
        byte[] encryptedSymmetricKey;
        byte[] encryptedSymmetricIV;

        //Create a new instance of the RSA class.  
        RSA rsa = RSA.Create();

        //Create a new instance of the RSAParameters structure.  
        RSAParameters rsaKeyInfo = new RSAParameters();

        //Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus;
        rsaKeyInfo.Exponent = exponent;

        //Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo);

        //Create a new instance of the default Aes implementation class.  
        Aes aes = Aes.Create();

        //Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1);
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1);
    }
}
```  
  
## <a name="see-also"></a>Zobacz też

- [Generowanie kluczy szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md)
- [Odszyfrowywanie danych](decrypting-data.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- [Luki w zabezpieczeniach chronometrażu z odszyfrowywaniem symetrycznym w trybie CBC przy użyciu uzupełnienia](vulnerabilities-cbc-mode.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
