---
title: 'Instrukcje: Szyfrowanie elementów XML przy użyciu kluczy symetrycznych'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AES algorithm
- cryptography [.NET], symmetric keys
- encryption [.NET], symmetric keys
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.Aes class
- XML encryption
- Advanced Encryption Standard algorithm
ms.assetid: d8461a44-aa2c-4ef4-b3e4-ab7cbaaee1b5
ms.openlocfilehash: cfda1835a1390b025f2ee0509a91c59104a77ae9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820231"
---
# <a name="how-to-encrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="363a1-102">Instrukcje: Szyfrowanie elementów XML przy użyciu kluczy symetrycznych</span><span class="sxs-lookup"><span data-stu-id="363a1-102">How to: Encrypt XML Elements with Symmetric Keys</span></span>

<span data-ttu-id="363a1-103">Można użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw do szyfrowania elementu w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="363a1-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="363a1-104">Szyfrowanie XML umożliwia przechowywanie i transportowanie poufnego kodu XML bez obaw o dane, które są łatwo odczytywane.</span><span class="sxs-lookup"><span data-stu-id="363a1-104">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="363a1-105">Ta procedura służy do szyfrowania elementu XML przy użyciu algorytmu Advanced Encryption Standard (AES).</span><span class="sxs-lookup"><span data-stu-id="363a1-105">This procedure encrypts an XML element using the Advanced Encryption Standard (AES) algorithm.</span></span>  
  
 <span data-ttu-id="363a1-106">Informacje o sposobie odszyfrowywania elementu XML, który został zaszyfrowany przy użyciu tej procedury, można znaleźć w temacie [How to: Deszyfruj elementy XML przy użyciu kluczy symetrycznych](how-to-decrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="363a1-106">For information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Symmetric Keys](how-to-decrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="363a1-107">W przypadku używania algorytmu symetrycznego, takiego jak AES do szyfrowania danych XML, należy użyć tego samego klucza do szyfrowania i odszyfrowywania danych XML.</span><span class="sxs-lookup"><span data-stu-id="363a1-107">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="363a1-108">W przykładzie tej procedury przyjęto założenie, że zaszyfrowany kod XML zostanie odszyfrowany przy użyciu tego samego klucza, a strony szyfrujące i odszyfrowuje zgadzają się na algorytm i klucz do użycia.</span><span class="sxs-lookup"><span data-stu-id="363a1-108">The example in this procedure assumes that the encrypted XML will be decrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="363a1-109">Ten przykład nie przechowuje ani nie szyfruje klucza AES w zaszyfrowanym formacie XML.</span><span class="sxs-lookup"><span data-stu-id="363a1-109">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="363a1-110">Ten przykład jest odpowiedni dla sytuacji, w których pojedyncza aplikacja musi szyfrować dane na podstawie klucza sesji przechowywanego w pamięci lub na podstawie kryptograficznego klucza silnego pochodzącego z hasła.</span><span class="sxs-lookup"><span data-stu-id="363a1-110">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="363a1-111">W przypadku, gdy co najmniej dwie aplikacje muszą udostępniać zaszyfrowane dane XML, należy rozważyć użycie schematu szyfrowania na podstawie algorytmu asymetrycznego lub certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="363a1-111">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="363a1-112">Aby zaszyfrować element XML przy użyciu klucza symetrycznego</span><span class="sxs-lookup"><span data-stu-id="363a1-112">To encrypt an XML element with a symmetric key</span></span>  
  
1. <span data-ttu-id="363a1-113">Generuj klucz symetryczny przy użyciu <xref:System.Security.Cryptography.Aes> klasy.</span><span class="sxs-lookup"><span data-stu-id="363a1-113">Generate a symmetric key using the <xref:System.Security.Cryptography.Aes> class.</span></span>  <span data-ttu-id="363a1-114">Ten klucz będzie używany do szyfrowania elementu XML.</span><span class="sxs-lookup"><span data-stu-id="363a1-114">This key will be used to encrypt the XML element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="363a1-115">Utwórz <xref:System.Xml.XmlDocument> obiekt przez załadowanie pliku XML z dysku.</span><span class="sxs-lookup"><span data-stu-id="363a1-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="363a1-116"><xref:System.Xml.XmlDocument>Obiekt zawiera element XML do zaszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="363a1-116">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="363a1-117">Znajdź określony element w <xref:System.Xml.XmlDocument> obiekcie i Utwórz nowy <xref:System.Xml.XmlElement> obiekt do reprezentowania elementu, który chcesz zaszyfrować.</span><span class="sxs-lookup"><span data-stu-id="363a1-117">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="363a1-118">W tym przykładzie `"creditcard"` element jest szyfrowany.</span><span class="sxs-lookup"><span data-stu-id="363a1-118">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#4)]  
  
4. <span data-ttu-id="363a1-119">Utwórz nowe wystąpienie <xref:System.Security.Cryptography.Xml.EncryptedXml> klasy i użyj go do zaszyfrowania <xref:System.Xml.XmlElement> przy użyciu klucza symetrycznego.</span><span class="sxs-lookup"><span data-stu-id="363a1-119">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the <xref:System.Xml.XmlElement> with the symmetric key.</span></span>  <span data-ttu-id="363a1-120"><xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A>Metoda zwraca zaszyfrowany element jako tablicę szyfrowanych bajtów.</span><span class="sxs-lookup"><span data-stu-id="363a1-120">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#5)]  
  
5. <span data-ttu-id="363a1-121">Utwórz <xref:System.Security.Cryptography.Xml.EncryptedData> obiekt i wypełnij go identyfikatorem URL elementu szyfrowania XML.</span><span class="sxs-lookup"><span data-stu-id="363a1-121">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the XML Encryption element.</span></span>  <span data-ttu-id="363a1-122">Ten identyfikator adresu URL umożliwia osobie odszyfrowanej, że kod XML zawiera zaszyfrowany element.</span><span class="sxs-lookup"><span data-stu-id="363a1-122">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="363a1-123">Możesz użyć pola, <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> Aby określić identyfikator URL.</span><span class="sxs-lookup"><span data-stu-id="363a1-123">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#6)]  
  
6. <span data-ttu-id="363a1-124">Utwórz <xref:System.Security.Cryptography.Xml.EncryptionMethod> obiekt, który jest zainicjowany do identyfikatora URL algorytmu kryptograficznego użytego do wygenerowania klucza.</span><span class="sxs-lookup"><span data-stu-id="363a1-124">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the key.</span></span>  <span data-ttu-id="363a1-125">Przekaż <xref:System.Security.Cryptography.Xml.EncryptionMethod> obiekt do <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="363a1-125">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#7)]  
  
7. <span data-ttu-id="363a1-126">Dodaj dane zaszyfrowanego elementu do <xref:System.Security.Cryptography.Xml.EncryptedData> obiektu.</span><span class="sxs-lookup"><span data-stu-id="363a1-126">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#8)]  
  
8. <span data-ttu-id="363a1-127">Zamień element z oryginalnego obiektu na <xref:System.Xml.XmlDocument> <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span><span class="sxs-lookup"><span data-stu-id="363a1-127">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="363a1-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="363a1-128">Example</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="363a1-129">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="363a1-129">Compiling the Code</span></span>  
  
- <span data-ttu-id="363a1-130">W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="363a1-130">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="363a1-131">W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="363a1-131">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="363a1-132">Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .</span><span class="sxs-lookup"><span data-stu-id="363a1-132">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="363a1-133">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="363a1-133">.NET Security</span></span>

<span data-ttu-id="363a1-134">Nie przechowuj klucza kryptograficznego w postaci zwykłego tekstu lub przesyłaj klucz między maszynami w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="363a1-134">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  <span data-ttu-id="363a1-135">Zamiast tego należy użyć bezpiecznego kontenera kluczy do przechowywania kluczy kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="363a1-135">Instead, use a secure key container to store cryptographic keys.</span></span>  
  
<span data-ttu-id="363a1-136">Gdy skończysz korzystać z klucza kryptograficznego, usuń go z pamięci przez ustawienie każdego bajtu na zero lub przez wywołanie <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> metody zarządzanej klasy kryptografii.</span><span class="sxs-lookup"><span data-stu-id="363a1-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="363a1-137">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="363a1-137">See also</span></span>

- <span data-ttu-id="363a1-138">[Model kryptografii](cryptography-model.md) — opis sposobu implementacji kryptografii w bibliotece klas bazowych.</span><span class="sxs-lookup"><span data-stu-id="363a1-138">[Cryptography Model](cryptography-model.md) - Describes how cryptography is implemented in the base class library.</span></span>
- [<span data-ttu-id="363a1-139">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="363a1-139">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="363a1-140">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="363a1-140">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="363a1-141">Instrukcje: Odszyfrowywanie elementów XML przy użyciu kluczy symetrycznych</span><span class="sxs-lookup"><span data-stu-id="363a1-141">How to: Decrypt XML Elements with Symmetric Keys</span></span>](how-to-decrypt-xml-elements-with-symmetric-keys.md)
- [<span data-ttu-id="363a1-142">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="363a1-142">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
