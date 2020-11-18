---
title: 'Instrukcje: Odszyfrowywanie elementów XML przy użyciu kluczy asymetrycznych'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSA class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
ms.openlocfilehash: 0456c89987b37840daa1c84342528d11c6da73a4
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822233"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="ad8a7-102">Instrukcje: Odszyfrowywanie elementów XML przy użyciu kluczy asymetrycznych</span><span class="sxs-lookup"><span data-stu-id="ad8a7-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>

<span data-ttu-id="ad8a7-103">Można użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw do szyfrowania i odszyfrowywania elementu w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="ad8a7-104">Szyfrowanie XML jest standardowym sposobem wymiany i przechowywania zaszyfrowanych danych XML bez obaw o dane, które są łatwo odczytywane.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="ad8a7-105">Aby uzyskać więcej informacji na temat standardu szyfrowania XML, zobacz [składnię i przetwarzanie podpisu XML](https://www.w3.org/TR/xmldsig-core/)zalecenia organizacja World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="ad8a7-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  

> [!NOTE]
> <span data-ttu-id="ad8a7-106">Kod w tym artykule ma zastosowanie do systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-106">The code in this article applies to Windows.</span></span>

<span data-ttu-id="ad8a7-107">Przykład w tej procedurze odszyfrowuje element XML, który został zaszyfrowany przy użyciu metod opisanych w artykule [jak: szyfrowanie elementów XML przy użyciu kluczy asymetrycznych](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="ad8a7-107">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="ad8a7-108">Znajduje `EncryptedData` element> <, odszyfrowuje element, a następnie zamienia element na oryginalny element XML w formacie zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-108">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
<span data-ttu-id="ad8a7-109">Ten przykład odszyfrowuje element XML przy użyciu dwóch kluczy.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-109">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="ad8a7-110">Pobiera on wcześniej wygenerowany klucz prywatny RSA z kontenera kluczy, a następnie używa klucza RSA do odszyfrowania klucza sesji przechowywanego w <`EncryptedKey`> elementu <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-110">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="ad8a7-111">W przykładzie zostanie użyty klucz sesji do odszyfrowania elementu XML.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-111">The example then uses the session key to decrypt the XML element.</span></span>  
  
<span data-ttu-id="ad8a7-112">Ten przykład jest odpowiedni dla sytuacji, w których wiele aplikacji musi udostępniać zaszyfrowane dane lub w przypadku, gdy aplikacja ma zapisywać zaszyfrowane dane między uruchomionymi danymi.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-112">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="ad8a7-113">Aby odszyfrować element XML za pomocą klucza asymetrycznego</span><span class="sxs-lookup"><span data-stu-id="ad8a7-113">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="ad8a7-114">Utwórz <xref:System.Security.Cryptography.CspParameters> obiekt i określ nazwę kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-114">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="ad8a7-115">Pobierz wcześniej wygenerowany klucz asymetryczny z kontenera przy użyciu <xref:System.Security.Cryptography.RSACryptoServiceProvider> obiektu.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-115">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="ad8a7-116">Klucz jest automatycznie pobierany z kontenera kluczy podczas przekazywania <xref:System.Security.Cryptography.CspParameters> obiektu do <xref:System.Security.Cryptography.RSACryptoServiceProvider> konstruktora.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-116">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="ad8a7-117">Utwórz nowy <xref:System.Security.Cryptography.Xml.EncryptedXml> obiekt do odszyfrowania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-117">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="ad8a7-118">Dodaj mapowanie klucza/nazwy, aby skojarzyć klucz RSA z elementem w dokumencie, który ma zostać odszyfrowany.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-118">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="ad8a7-119">Należy użyć tej samej nazwy klucza, który został użyty podczas szyfrowania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-119">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="ad8a7-120">Należy zauważyć, że ta nazwa jest oddzielona od nazwy używanej do identyfikowania klucza w kontenerze kluczy określonym w kroku 1.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-120">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="ad8a7-121">Wywołaj <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> metodę w celu odszyfrowania `EncryptedData` elementu> <.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-121">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="ad8a7-122">Ta metoda powoduje odszyfrowanie klucza sesji przy użyciu klucza RSA i automatyczne odszyfrowanie elementu XML przy użyciu klucza sesji.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-122">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="ad8a7-123">Automatycznie zastępuje <`EncryptedData`> elementu pierwotnym tekstem.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-123">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="ad8a7-124">Zapisz dokument XML.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-124">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="ad8a7-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad8a7-125">Example</span></span>

<span data-ttu-id="ad8a7-126">W tym przykładzie przyjęto założenie, że plik o nazwie `test.xml` istnieje w tym samym katalogu co skompilowany program.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-126">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="ad8a7-127">Przyjęto również założenie, że `test.xml` zawiera element XML, który został zaszyfrowany przy użyciu technik opisanych w [instrukcje: szyfrowanie elementów XML przy użyciu kluczy asymetrycznych](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="ad8a7-127">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
[!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad8a7-128">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="ad8a7-128">Compiling the Code</span></span>  
  
- <span data-ttu-id="ad8a7-129">W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="ad8a7-129">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="ad8a7-130">W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="ad8a7-130">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="ad8a7-131">Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .</span><span class="sxs-lookup"><span data-stu-id="ad8a7-131">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="ad8a7-132">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="ad8a7-132">.NET Security</span></span>  

<span data-ttu-id="ad8a7-133">Nigdy nie przechowuj symetrycznego klucza kryptograficznego w postaci zwykłego tekstu lub przesyłaj klucz symetryczny między maszynami w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-133">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="ad8a7-134">Ponadto nigdy nie należy przechowywać ani przenosić klucza prywatnego pary kluczy asymetrycznych w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-134">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="ad8a7-135">Aby uzyskać więcej informacji na temat symetrycznych i asymetrycznych kluczy kryptograficznych, zobacz [generowanie kluczy do szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="ad8a7-135">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="ad8a7-136">Nigdy nie osadzaj klucza bezpośrednio w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-136">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="ad8a7-137">Klucze osadzone można łatwo odczytywać z zestawu przy użyciu [Ildasm.exe (Il dezasembler)](../../framework/tools/ildasm-exe-il-disassembler.md) lub otwierając zestaw w edytorze tekstu, takim jak Notatnik.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-137">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="ad8a7-138">Gdy skończysz korzystać z klucza kryptograficznego, usuń go z pamięci przez ustawienie każdego bajtu na zero lub przez wywołanie <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> metody zarządzanej klasy kryptografii.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-138">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="ad8a7-139">Klucze kryptograficzne mogą być czasami odczytywane z pamięci przez debuger lub odczytywane z dysku twardego, jeśli lokalizacja pamięci jest stronicowana na dysku.</span><span class="sxs-lookup"><span data-stu-id="ad8a7-139">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad8a7-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ad8a7-140">See also</span></span>

- [<span data-ttu-id="ad8a7-141">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="ad8a7-141">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="ad8a7-142">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="ad8a7-142">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="ad8a7-143">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="ad8a7-143">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="ad8a7-144">Instrukcje: Szyfrowanie elementów XML przy użyciu kluczy asymetrycznych</span><span class="sxs-lookup"><span data-stu-id="ad8a7-144">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](how-to-encrypt-xml-elements-with-asymmetric-keys.md)
- [<span data-ttu-id="ad8a7-145">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ad8a7-145">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
