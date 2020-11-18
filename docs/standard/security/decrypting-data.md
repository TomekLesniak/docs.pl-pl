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
# <a name="decrypting-data"></a><span data-ttu-id="50c92-103">Odszyfrowywanie danych</span><span class="sxs-lookup"><span data-stu-id="50c92-103">Decrypting Data</span></span>

<span data-ttu-id="50c92-104">Odszyfrowywanie jest odwrotną operacją szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="50c92-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="50c92-105">W przypadku szyfrowania klucza tajnego należy znać zarówno klucz, jak i IV, które były używane do szyfrowania danych.</span><span class="sxs-lookup"><span data-stu-id="50c92-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="50c92-106">W przypadku szyfrowania klucza publicznego należy znać klucz publiczny (Jeśli dane zostały zaszyfrowane przy użyciu klucza prywatnego) lub klucza prywatnego (Jeśli dane zostały zaszyfrowane przy użyciu klucza publicznego).</span><span class="sxs-lookup"><span data-stu-id="50c92-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="50c92-107">Odszyfrowywanie symetryczne</span><span class="sxs-lookup"><span data-stu-id="50c92-107">Symmetric Decryption</span></span>

<span data-ttu-id="50c92-108">Odszyfrowywanie danych szyfrowanych za pomocą algorytmów symetrycznych jest podobne do procesu używanego do szyfrowania danych za pomocą algorytmów symetrycznych.</span><span class="sxs-lookup"><span data-stu-id="50c92-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="50c92-109"><xref:System.Security.Cryptography.CryptoStream>Klasa jest używana z symetrycznymi klasami kryptografii udostępnianymi przez platformę .NET do odszyfrowywania danych odczytanych z dowolnego zarządzanego obiektu strumienia.</span><span class="sxs-lookup"><span data-stu-id="50c92-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="50c92-110">Poniższy przykład ilustruje sposób tworzenia nowego wystąpienia domyślnej klasy implementacji dla <xref:System.Security.Cryptography.Aes> algorytmu.</span><span class="sxs-lookup"><span data-stu-id="50c92-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="50c92-111">To wystąpienie jest używane do wykonania odszyfrowywania w <xref:System.Security.Cryptography.CryptoStream> obiekcie.</span><span class="sxs-lookup"><span data-stu-id="50c92-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="50c92-112">Ten przykład najpierw tworzy nowe wystąpienie <xref:System.Security.Cryptography.Aes> klasy implementacji.</span><span class="sxs-lookup"><span data-stu-id="50c92-112">This example first creates a new instance of the <xref:System.Security.Cryptography.Aes> implementation class.</span></span> <span data-ttu-id="50c92-113">Odczytuje wartość Vector inicjującą (IV) z zarządzanej zmiennej strumienia `myStream` .</span><span class="sxs-lookup"><span data-stu-id="50c92-113">It reads the initialization vector (IV) value from a managed stream variable, `myStream`.</span></span> <span data-ttu-id="50c92-114">Następnie tworzy wystąpienie <xref:System.Security.Cryptography.CryptoStream> obiektu i inicjuje go dla wartości `myStream` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="50c92-114">Next it instantiates a <xref:System.Security.Cryptography.CryptoStream> object and initializes it to the value of the `myStream` instance.</span></span> <span data-ttu-id="50c92-115"><xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType>Metoda z <xref:System.Security.Cryptography.Aes> wystąpienia jest przenoszona wartość IV i ten sam klucz, który był używany do szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="50c92-115">The <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType> method from the <xref:System.Security.Cryptography.Aes> instance is passed the IV value and the same key that was used for encryption.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="50c92-116">Poniższy przykład pokazuje cały proces tworzenia strumienia, odszyfrowywania strumienia, odczytywania ze strumienia i zamykania strumieni.</span><span class="sxs-lookup"><span data-stu-id="50c92-116">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="50c92-117">Tworzony jest obiekt strumienia pliku, który odczytuje plik o nazwie *TestData.txt*.</span><span class="sxs-lookup"><span data-stu-id="50c92-117">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="50c92-118">Strumień pliku jest następnie odszyfrowywany przy użyciu klasy **CryptoStream** i **AES** .</span><span class="sxs-lookup"><span data-stu-id="50c92-118">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="50c92-119">Ten przykład określa wartość klucza, która jest używana w przykładzie szyfrowania symetrycznego do [szyfrowania danych](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="50c92-119">This example specifies key value that is used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="50c92-120">Nie jest wyświetlany kod wymagany do szyfrowania i transferu tych wartości.</span><span class="sxs-lookup"><span data-stu-id="50c92-120">It does not show the code needed to encrypt and transfer these values.</span></span>

:::code language="csharp" source="snippets/decrypting-data/csharp/aes-decrypt.cs":::
:::code language="vb" source="snippets/decrypting-data/vb/aes-decrypt.vb":::

<span data-ttu-id="50c92-121">W poprzednim przykładzie użyto tego samego klucza, a algorytm używany w przykładzie szyfrowania symetrycznego do [szyfrowania danych](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="50c92-121">The preceding example uses the same key, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="50c92-122">Odszyfrowuje plik *TestData.txt* , który jest tworzony przez ten przykład, i wyświetla oryginalny tekst w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="50c92-122">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="50c92-123">Odszyfrowywanie asymetryczne</span><span class="sxs-lookup"><span data-stu-id="50c92-123">Asymmetric Decryption</span></span>

<span data-ttu-id="50c92-124">Zazwyczaj strona (Strona A) generuje zarówno klucz publiczny, jak i prywatny, a klucz jest przechowywany w pamięci lub w kontenerze kluczy kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="50c92-124">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="50c92-125">Następnie firma A następnie wysyła klucz publiczny do innej strony (strona B).</span><span class="sxs-lookup"><span data-stu-id="50c92-125">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="50c92-126">Przy użyciu klucza publicznego Strona B szyfruje dane i wysyła je z powrotem do strony A. Po odebraniu danych firma odszyfruje je przy użyciu klucza prywatnego, który odpowiada.</span><span class="sxs-lookup"><span data-stu-id="50c92-126">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="50c92-127">Odszyfrowywanie powiedzie się tylko wtedy, gdy strona A używa klucza prywatnego, który odpowiada stronie klucza publicznego, który jest używany do szyfrowania danych.</span><span class="sxs-lookup"><span data-stu-id="50c92-127">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="50c92-128">Aby uzyskać informacje na temat sposobu przechowywania klucza asymetrycznego w bezpiecznym kontenerze kluczy kryptograficznych i sposobie późniejszego pobierania klucza asymetrycznego, zobacz [How to: Store asymetryczne klucze w kontenerze kluczy](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="50c92-128">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="50c92-129">Poniższy przykład ilustruje odszyfrowywanie dwóch tablic bajtów reprezentujących klucz symetryczny i IV.</span><span class="sxs-lookup"><span data-stu-id="50c92-129">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="50c92-130">Aby uzyskać informacje na temat sposobu wyodrębniania asymetrycznego klucza publicznego z <xref:System.Security.Cryptography.RSA> obiektu w formacie, który można łatwo przesłać do innej firmy, zobacz [szyfrowanie danych](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="50c92-130">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="50c92-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="50c92-131">See also</span></span>

- [<span data-ttu-id="50c92-132">Generowanie kluczy szyfrowania i odszyfrowywania</span><span class="sxs-lookup"><span data-stu-id="50c92-132">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="50c92-133">Szyfrowanie danych</span><span class="sxs-lookup"><span data-stu-id="50c92-133">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="50c92-134">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="50c92-134">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="50c92-135">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="50c92-135">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="50c92-136">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="50c92-136">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="50c92-137">Luki w zabezpieczeniach chronometrażu z odszyfrowywaniem symetrycznym w trybie CBC przy użyciu uzupełnienia</span><span class="sxs-lookup"><span data-stu-id="50c92-137">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="50c92-138">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="50c92-138">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
