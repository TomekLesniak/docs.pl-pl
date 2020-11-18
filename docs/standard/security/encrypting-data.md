---
title: Szyfrowanie danych
description: Dowiedz się, jak szyfrować dane w programie .NET przy użyciu algorytmu symetrycznego lub algorytmu asymetrycznego.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], symmetric
- symmetric encryption
- cryptography [.NET], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 574ef3f829406d661e19f004e9a7d150954fd9e5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830600"
---
# <a name="encrypting-data"></a><span data-ttu-id="4326d-103">Szyfrowanie danych</span><span class="sxs-lookup"><span data-stu-id="4326d-103">Encrypting Data</span></span>

<span data-ttu-id="4326d-104">Szyfrowanie symetryczne i szyfrowanie asymetryczne są wykonywane przy użyciu różnych procesów.</span><span class="sxs-lookup"><span data-stu-id="4326d-104">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="4326d-105">Szyfrowanie symetryczne jest wykonywane na strumieniach i dlatego jest przydatne do szyfrowania dużych ilości danych.</span><span class="sxs-lookup"><span data-stu-id="4326d-105">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="4326d-106">Szyfrowanie asymetryczne jest wykonywane w niewielkiej liczbie bajtów i dlatego jest przydatne tylko w przypadku małych ilości danych.</span><span class="sxs-lookup"><span data-stu-id="4326d-106">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="4326d-107">Szyfrowanie symetryczne</span><span class="sxs-lookup"><span data-stu-id="4326d-107">Symmetric Encryption</span></span>  

<span data-ttu-id="4326d-108">Zarządzane klasy kryptografii symetrycznej są używane z specjalną klasą strumienia o nazwie a <xref:System.Security.Cryptography.CryptoStream> , która szyfruje dane odczytane do strumienia.</span><span class="sxs-lookup"><span data-stu-id="4326d-108">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="4326d-109">Klasa **CryptoStream** jest inicjowana za pomocą zarządzanej klasy strumienia, klasy implementującej <xref:System.Security.Cryptography.ICryptoTransform> interfejs (utworzony na podstawie klasy implementującej algorytm kryptograficzny) i <xref:System.Security.Cryptography.CryptoStreamMode> wyliczenia opisującego typ dostępu, który jest dozwolony dla **CryptoStream**.</span><span class="sxs-lookup"><span data-stu-id="4326d-109">The **CryptoStream** class is initialized with a managed stream class, a class that implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="4326d-110">Klasę **CryptoStream** można zainicjować przy użyciu dowolnej klasy, która dziedziczy z <xref:System.IO.Stream> klasy, w tym <xref:System.IO.FileStream> , <xref:System.IO.MemoryStream> , i <xref:System.Net.Sockets.NetworkStream> .</span><span class="sxs-lookup"><span data-stu-id="4326d-110">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="4326d-111">Za pomocą tych klas można wykonać szyfrowanie symetryczne na różnych obiektach strumienia.</span><span class="sxs-lookup"><span data-stu-id="4326d-111">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
<span data-ttu-id="4326d-112">Poniższy przykład ilustruje sposób tworzenia nowego wystąpienia domyślnej klasy implementacji dla <xref:System.Security.Cryptography.Aes> algorytmu.</span><span class="sxs-lookup"><span data-stu-id="4326d-112">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="4326d-113">To wystąpienie jest używane do wykonywania szyfrowania na klasie **CryptoStream** .</span><span class="sxs-lookup"><span data-stu-id="4326d-113">The instance is used to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="4326d-114">W tym przykładzie **CryptoStream** jest inicjowany przy użyciu obiektu Stream o nazwie `myStream` , który może być dowolnym typem strumienia zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="4326d-114">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="4326d-115">Metoda **coclass** z klasy **AES** jest przenoszona z klucza i IV, który jest używany do szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="4326d-115">The **CreateEncryptor** method from the **Aes** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="4326d-116">W takim przypadku użyto klucza domyślnego i dodatku IV wygenerowanego z `aes` .</span><span class="sxs-lookup"><span data-stu-id="4326d-116">In this case, the default key and IV generated from `aes` are used.</span></span>
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
<span data-ttu-id="4326d-117">Po wykonaniu tego kodu wszystkie dane zapisywane w obiekcie **CryptoStream** są szyfrowane przy użyciu algorytmu AES.</span><span class="sxs-lookup"><span data-stu-id="4326d-117">After this code is executed, any data written to the **CryptoStream** object is encrypted using the AES algorithm.</span></span>  
  
<span data-ttu-id="4326d-118">Poniższy przykład pokazuje cały proces tworzenia strumienia, szyfrowania strumienia, zapisywania do strumienia i zamykania strumienia.</span><span class="sxs-lookup"><span data-stu-id="4326d-118">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="4326d-119">W tym przykładzie tworzony jest strumień plików zaszyfrowany przy użyciu klasy **CryptoStream** i klasy **AES** .</span><span class="sxs-lookup"><span data-stu-id="4326d-119">This example creates a file stream that is encrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="4326d-120">Wygenerowany plik IV jest zapisywana na początku <xref:System.IO.FileStream> , dlatego może być odczytywany i używany do odszyfrowywania.</span><span class="sxs-lookup"><span data-stu-id="4326d-120">Generated IV is written to beginning of <xref:System.IO.FileStream>, so it can be read and used for decryption.</span></span> <span data-ttu-id="4326d-121">Następnie w zaszyfrowanym strumieniu zostanie zapisany komunikat z <xref:System.IO.StreamWriter> klasą.</span><span class="sxs-lookup"><span data-stu-id="4326d-121">Then a message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="4326d-122">Ten sam klucz może być wielokrotnie używany do szyfrowania i odszyfrowywania danych, dlatego zaleca się wygenerowanie nowej losowego kodu w języku IV za każdym razem.</span><span class="sxs-lookup"><span data-stu-id="4326d-122">While the same key can be used multiple times to encrypt and decrypt data, it is recommended to generate a new random IV each time.</span></span> <span data-ttu-id="4326d-123">W ten sposób zaszyfrowane dane są zawsze różne, nawet jeśli zwykły tekst jest taki sam.</span><span class="sxs-lookup"><span data-stu-id="4326d-123">This way the encrypted data is always different, even when plain text is the same.</span></span>
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

<span data-ttu-id="4326d-124">Kod szyfruje strumień przy użyciu algorytmu symetrycznego AES i zapisuje IV, a następnie szyfruje "Hello world!"</span><span class="sxs-lookup"><span data-stu-id="4326d-124">The code encrypts the stream using the AES symmetric algorithm, and writes IV and then encrypted "Hello World!"</span></span> <span data-ttu-id="4326d-125">do strumienia.</span><span class="sxs-lookup"><span data-stu-id="4326d-125">to the stream.</span></span> <span data-ttu-id="4326d-126">Jeśli kod zakończy się pomyślnie, tworzy zaszyfrowany plik o nazwie *TestData.txt* i wyświetla następujący tekst w konsoli programu:</span><span class="sxs-lookup"><span data-stu-id="4326d-126">If the code is successful, it creates an encrypted file named *TestData.txt* and displays the following text to the console:</span></span>
  
```console  
The text was encrypted.
```  

<span data-ttu-id="4326d-127">Plik można odszyfrować przy użyciu przykładu szyfrowania symetrycznego w [odszyfrowaniu danych](decrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="4326d-127">You can decrypt the file by using the symmetric decryption example in [Decrypting Data](decrypting-data.md).</span></span> <span data-ttu-id="4326d-128">Ten przykład i ten przykład określa ten sam klucz.</span><span class="sxs-lookup"><span data-stu-id="4326d-128">That example and this example specify the same key.</span></span>

<span data-ttu-id="4326d-129">Jeśli jednak występuje wyjątek, kod wyświetla następujący tekst w konsoli programu:</span><span class="sxs-lookup"><span data-stu-id="4326d-129">However, if an exception is raised, the code displays the following text to the console:</span></span>
  
```console  
The encryption failed.
```

## <a name="asymmetric-encryption"></a><span data-ttu-id="4326d-130">Szyfrowanie asymetryczne</span><span class="sxs-lookup"><span data-stu-id="4326d-130">Asymmetric Encryption</span></span>

<span data-ttu-id="4326d-131">Algorytmy asymetryczne są zwykle używane do szyfrowania małych ilości danych, takich jak szyfrowanie klucza symetrycznego i IV.</span><span class="sxs-lookup"><span data-stu-id="4326d-131">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="4326d-132">Zazwyczaj pojedyncze wykonywanie szyfrowania asymetrycznego używa klucza publicznego wygenerowanego przez inną firmę.</span><span class="sxs-lookup"><span data-stu-id="4326d-132">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="4326d-133">W <xref:System.Security.Cryptography.RSA> tym celu Klasa jest udostępniana przez platformę .NET.</span><span class="sxs-lookup"><span data-stu-id="4326d-133">The <xref:System.Security.Cryptography.RSA> class is provided by .NET for this purpose.</span></span>  
  
<span data-ttu-id="4326d-134">Poniższy przykład używa informacji o kluczu publicznym do szyfrowania klucza symetrycznego i IV.</span><span class="sxs-lookup"><span data-stu-id="4326d-134">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="4326d-135">Są inicjowane dwubajtowe tablice reprezentujące klucz publiczny strony trzeciej.</span><span class="sxs-lookup"><span data-stu-id="4326d-135">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="4326d-136"><xref:System.Security.Cryptography.RSAParameters>Obiekt jest zainicjowany do tych wartości.</span><span class="sxs-lookup"><span data-stu-id="4326d-136">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="4326d-137">Następnie obiekt **RSAParameters** (wraz z kluczem publicznym, który reprezentuje) jest zaimportowany do wystąpienia **RSA** przy użyciu <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="4326d-137">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSA** instance using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4326d-138">Na koniec kluczem prywatnym i IV tworzonym przez <xref:System.Security.Cryptography.Aes> klasę są szyfrowane.</span><span class="sxs-lookup"><span data-stu-id="4326d-138">Finally, the private key and IV created by an <xref:System.Security.Cryptography.Aes> class are encrypted.</span></span> <span data-ttu-id="4326d-139">Ten przykład wymaga, aby systemy miały zainstalowane szyfrowanie 128-bitowe.</span><span class="sxs-lookup"><span data-stu-id="4326d-139">This example requires systems to have 128-bit encryption installed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4326d-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4326d-140">See also</span></span>

- [<span data-ttu-id="4326d-141">Generowanie kluczy szyfrowania i odszyfrowywania</span><span class="sxs-lookup"><span data-stu-id="4326d-141">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="4326d-142">Odszyfrowywanie danych</span><span class="sxs-lookup"><span data-stu-id="4326d-142">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="4326d-143">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="4326d-143">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="4326d-144">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="4326d-144">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="4326d-145">Luki w zabezpieczeniach chronometrażu z odszyfrowywaniem symetrycznym w trybie CBC przy użyciu uzupełnienia</span><span class="sxs-lookup"><span data-stu-id="4326d-145">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="4326d-146">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4326d-146">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
