---
title: Generowanie kluczy szyfrowania i odszyfrowywania
description: Informacje na temat tworzenia kluczy symetrycznych i asymetrycznych na potrzeby szyfrowania i odszyfrowywania w programie .NET oraz zarządzania nimi.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET], keys
- symmetric keys
- asymmetric keys [.NET]
- cryptography [.NET], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: 2af54cef4f233b7bcae5c476f1aa49fdbf7ef2fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689722"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="5c9b4-103">Generowanie kluczy szyfrowania i odszyfrowywania</span><span class="sxs-lookup"><span data-stu-id="5c9b4-103">Generating Keys for Encryption and Decryption</span></span>

<span data-ttu-id="5c9b4-104">Tworzenie kluczy i zarządzanie nimi jest ważną częścią procesu kryptograficznego.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-104">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="5c9b4-105">Algorytmy symetryczne wymagają utworzenia klucza i wektora inicjalizacji (IV).</span><span class="sxs-lookup"><span data-stu-id="5c9b4-105">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="5c9b4-106">Klucz musi być poufny dla każdego, kto nie powinien odszyfrować danych.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-106">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="5c9b4-107">IV nie musi być tajny, ale powinien zostać zmieniony dla każdej sesji.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-107">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="5c9b4-108">Algorytmy asymetryczne wymagają utworzenia klucza publicznego i klucza prywatnego.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-108">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="5c9b4-109">Klucz publiczny może być publiczny dla każdej osoby, natomiast klucz prywatny musi być znany tylko przez osobę, która będzie odszyfrować dane zaszyfrowane za pomocą klucza publicznego.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-109">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="5c9b4-110">W tej sekcji opisano, jak generować klucze dla algorytmów symetrycznych i asymetrycznych oraz zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-110">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="5c9b4-111">Klucze symetryczne</span><span class="sxs-lookup"><span data-stu-id="5c9b4-111">Symmetric Keys</span></span>  

 <span data-ttu-id="5c9b4-112">Klasy szyfrowania symetrycznego dostarczane przez platformę .NET wymagają klucza i nowego wektora inicjalizacji (IV) do szyfrowania i odszyfrowywania danych.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-112">The symmetric encryption classes supplied by .NET require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="5c9b4-113">Za każdym razem, gdy tworzysz nowe wystąpienie jednej z zarządzanych, symetryczne klasy kryptograficzne przy użyciu metody bez parametrów `Create()` , nowy klucz i IV są tworzone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-113">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the parameterless `Create()` method, a new key and IV are automatically created.</span></span> <span data-ttu-id="5c9b4-114">Każda osoba, która zezwoli na odszyfrowanie danych, musi mieć ten sam klucz i IV i korzystać z tego samego algorytmu.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-114">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="5c9b4-115">Ogólnie rzecz biorąc, należy utworzyć nowy klucz i IV dla każdej sesji, a klucz i IV nie powinny być przechowywane do użytku w późniejszej sesji.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-115">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="5c9b4-116">Aby przekazać klucz symetryczny i IV do strony zdalnej, zazwyczaj należy zaszyfrować klucz symetryczny przy użyciu szyfrowania asymetrycznego.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-116">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="5c9b4-117">Wysyłanie klucza w niezabezpieczonej sieci bez szyfrowania jest niebezpieczne, ponieważ każdy z nich przechwytuje klucz i IV może odszyfrować dane.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-117">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span>  
  
 <span data-ttu-id="5c9b4-118">W poniższym przykładzie pokazano Tworzenie nowego wystąpienia domyślnej klasy implementacji dla <xref:System.Security.Cryptography.Aes> algorytmu.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-118">The following example shows the creation of a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 <span data-ttu-id="5c9b4-119">Gdy poprzedni kod jest wykonywany, nowy klucz i IV są generowane i umieszczane odpowiednio w właściwościach **Key** i **IV** .</span><span class="sxs-lookup"><span data-stu-id="5c9b4-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="5c9b4-120">Czasami może być konieczne wygenerowanie wielu kluczy.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="5c9b4-121">W takiej sytuacji można utworzyć nowe wystąpienie klasy implementującej algorytm symetryczny, a następnie utworzyć nowy klucz i IV, wywołując metody **do generowania kluczy** i **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="5c9b4-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="5c9b4-122">Poniższy przykład kodu ilustruje sposób tworzenia nowych kluczy i użycie japońskich ideograficznych po wykonaniu nowego wystąpienia symetrycznej klasy kryptograficznej.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-122">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
aes.GenerateIV()  
aes.GenerateKey()  
```  
  
```csharp  
Aes aes = Aes.Create();  
aes.GenerateIV();  
aes.GenerateKey();  
```  
  
 <span data-ttu-id="5c9b4-123">Gdy poprzedni kod jest wykonywany, klucz i IV są generowane po wykonaniu nowego wystąpienia **algorytmu AES** .</span><span class="sxs-lookup"><span data-stu-id="5c9b4-123">When the preceding code is executed, a key and IV are generated when the new instance of **Aes** is made.</span></span> <span data-ttu-id="5c9b4-124">Po wywołaniu metod **do generowania kluczy** i **GenerateIV** są tworzone inne klucze i IV.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>
  
## <a name="asymmetric-keys"></a><span data-ttu-id="5c9b4-125">Klucze asymetryczne</span><span class="sxs-lookup"><span data-stu-id="5c9b4-125">Asymmetric Keys</span></span>

 <span data-ttu-id="5c9b4-126">Platforma .NET udostępnia <xref:System.Security.Cryptography.RSA> klasę do szyfrowania asymetrycznego.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-126">.NET provides the <xref:System.Security.Cryptography.RSA> class for asymmetric encryption.</span></span> <span data-ttu-id="5c9b4-127">Ta klasa tworzy parę kluczy publicznych/prywatnych `Create()` w przypadku utworzenia nowego wystąpienia przy użyciu metody bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-127">This class creates a public/private key pair when you use the parameterless `Create()` method to create a new instance.</span></span> <span data-ttu-id="5c9b4-128">Klucze asymetryczne mogą być przechowywane do użytku w wielu sesjach lub generowane tylko dla jednej sesji.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="5c9b4-129">Chociaż klucz publiczny można ogólnie udostępnić, klucz prywatny powinien być ściśle chroniony.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="5c9b4-130">Para kluczy publiczny/prywatny jest generowana za każdym razem, gdy tworzone jest nowe wystąpienie klasy algorytmu asymetrycznego.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="5c9b4-131">Po utworzeniu nowego wystąpienia klasy można wyodrębnić informacje o kluczu przy użyciu <xref:System.Security.Cryptography.RSA.ExportParameters%2A> metody, która zwraca <xref:System.Security.Cryptography.RSAParameters> strukturę, która zawiera informacje o kluczu.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-131">After a new instance of the class is created, the key information can be extracted using the <xref:System.Security.Cryptography.RSA.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span> <span data-ttu-id="5c9b4-132">Metoda przyjmuje wartość logiczną, która wskazuje, czy zwrócić tylko informacje o kluczu publicznym, czy zwrócić zarówno klucz publiczny, jak i informacje o kluczu prywatnym.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-132">The method accepts a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span>

<span data-ttu-id="5c9b4-133">Istnieją również inne metody, które umożliwiają wyodrębnienie najważniejszych informacji, takich jak:</span><span class="sxs-lookup"><span data-stu-id="5c9b4-133">There are also other methods that let you extract key information, such as:</span></span>

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

<span data-ttu-id="5c9b4-134">Wystąpienie **RSA** można zainicjować do wartości struktury **RSAParameters** przy użyciu <xref:System.Security.Cryptography.RSA.ImportParameters%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-134">An **RSA** instance can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A> method.</span></span> <span data-ttu-id="5c9b4-135">Lub Utwórz nowe wystąpienie przy użyciu <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-135">Or create a new instance by using the <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="5c9b4-136">Asymetryczne klucze prywatne nigdy nie powinny być przechowywane Verbatim ani w postaci zwykłego tekstu na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="5c9b4-137">Jeśli musisz przechować klucz prywatny, należy użyć kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="5c9b4-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="5c9b4-138">Aby uzyskać więcej informacji o tym, jak przechowywać klucz prywatny w kontenerze kluczy, zobacz [jak: przechowywanie kluczy asymetrycznych w kontenerze kluczy](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="5c9b4-138">For more information about how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="5c9b4-139">Poniższy przykład kodu tworzy nowe wystąpienie klasy **RSA** , tworząc parę kluczy publiczny/prywatny i zapisuje informacje o kluczu publicznym do struktury **RSAParameters** .</span><span class="sxs-lookup"><span data-stu-id="5c9b4-139">The following code example creates a new instance of the **RSA** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSA = RSA.Create()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSA rsa = RSA.Create();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c9b4-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5c9b4-140">See also</span></span>

- [<span data-ttu-id="5c9b4-141">Szyfrowanie danych</span><span class="sxs-lookup"><span data-stu-id="5c9b4-141">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="5c9b4-142">Odszyfrowywanie danych</span><span class="sxs-lookup"><span data-stu-id="5c9b4-142">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="5c9b4-143">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="5c9b4-143">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="5c9b4-144">Instrukcje: Przechowywanie kluczy asymetrycznych w kontenerze kluczy</span><span class="sxs-lookup"><span data-stu-id="5c9b4-144">How to: Store Asymmetric Keys in a Key Container</span></span>](how-to-store-asymmetric-keys-in-a-key-container.md)
- [<span data-ttu-id="5c9b4-145">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="5c9b4-145">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="5c9b4-146">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5c9b4-146">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
