---
title: Odszyfrowywanie danych
description: Dowiedz się, jak odszyfrować dane w programie .NET przy użyciu algorytmu symetrycznego lub algorytmu asymetrycznego.
ms.date: 07/16/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 2ba4c3ba43d688aeb66c67ec3f94f4a503d47892
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556985"
---
# <a name="decrypting-data"></a>Odszyfrowywanie danych

Odszyfrowywanie jest odwrotną operacją szyfrowania. W przypadku szyfrowania klucza tajnego należy znać zarówno klucz, jak i IV, które były używane do szyfrowania danych. W przypadku szyfrowania klucza publicznego należy znać klucz publiczny (Jeśli dane zostały zaszyfrowane przy użyciu klucza prywatnego) lub klucza prywatnego (Jeśli dane zostały zaszyfrowane przy użyciu klucza publicznego).

## <a name="symmetric-decryption"></a>Odszyfrowywanie symetryczne

Odszyfrowywanie danych szyfrowanych za pomocą algorytmów symetrycznych jest podobne do procesu używanego do szyfrowania danych za pomocą algorytmów symetrycznych. <xref:System.Security.Cryptography.CryptoStream>Klasa jest używana z symetrycznymi klasami kryptografii udostępnianymi przez platformę .NET do odszyfrowywania danych odczytanych z dowolnego zarządzanego obiektu strumienia.

Poniższy przykład ilustruje sposób tworzenia nowego wystąpienia domyślnej klasy implementacji dla <xref:System.Security.Cryptography.Aes> algorytmu. To wystąpienie jest używane do wykonania odszyfrowywania w <xref:System.Security.Cryptography.CryptoStream> obiekcie. Ten przykład najpierw tworzy nowe wystąpienie klasy implementacji **AES** . Następnie tworzy obiekt **CryptoStream** i inicjuje go do wartości strumienia zarządzanego o nazwie `myStream` . Następnie Metoda CryptoStream **z klasy** **AES** jest przenoszona z tego samego klucza i IV, który był używany do szyfrowania, a następnie jest przenoszona do konstruktora **CryptoStream** programu.

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

Poniższy przykład pokazuje cały proces tworzenia strumienia, odszyfrowywania strumienia, odczytywania ze strumienia i zamykania strumieni. Tworzony jest obiekt strumienia pliku, który odczytuje plik o nazwie *TestData.txt*. Strumień pliku jest następnie odszyfrowywany przy użyciu klasy **CryptoStream** i **AES** . W tym przykładzie określono wartości key i IV, które są używane w przykładowym szyfrowaniu szyfrowanym do [szyfrowania danych](encrypting-data.md). Nie jest wyświetlany kod wymagany do szyfrowania i transferu tych wartości.

```vb
Imports System
Imports System.IO
Imports System.Security.Cryptography

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Create a file stream.
            Dim myStream As FileStream = new FileStream("TestData.txt", FileMode.Open)

            'Create a new instance of the default Aes implementation class
            'and decrypt the stream.
            Dim aes As Aes = Aes.Create()

            'Create an instance of the CryptoStream class, pass it the file stream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            myStream.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The decryption Failed.")
            Throw
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

class Class1
{
    static void Main(string[] args)
    {
        //The key and IV must be the same values that were used
        //to encrypt the stream.
        byte[] key = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        byte[] iv = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        try
        {
            //Create a file stream.
            FileStream myStream = new FileStream("TestData.txt", FileMode.Open);

            //Create a new instance of the default Aes implementation class
            Aes aes = Aes.Create();

            //Create a CryptoStream, pass it the file stream, and decrypt
            //it with the Aes class using the key and IV.
            CryptoStream cryptStream = new CryptoStream(
               myStream,
               aes.CreateDecryptor(key, iv),
               CryptoStreamMode.Read);

            //Read the stream.
            StreamReader sReader = new StreamReader(cryptStream);

            //Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

            //Close the streams.
            sReader.Close();
            myStream.Close();
        }
        //Catch any exceptions.
        catch
        {
            Console.WriteLine("The decryption failed.");
            throw;
        }
    }
}
```

W powyższym przykładzie użyto tego samego klucza, IV i algorytmu użytego w przykładzie szyfrowania symetrycznego do [szyfrowania danych](encrypting-data.md). Odszyfrowuje plik *TestData.txt* , który jest tworzony przez ten przykład, i wyświetla oryginalny tekst w konsoli programu.

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

## <a name="see-also"></a>Zobacz też

- [Generowanie kluczy szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md)
- [Szyfrowanie danych](encrypting-data.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Model kryptografii](cryptography-model.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- [Luki w zabezpieczeniach chronometrażu z odszyfrowywaniem symetrycznym w trybie CBC przy użyciu uzupełnienia](vulnerabilities-cbc-mode.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
