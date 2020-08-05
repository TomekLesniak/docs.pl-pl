---
title: 'Instrukcje: Szyfrowanie elementów XML przy użyciu kluczy asymetrycznych'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], asymmetric keys
- AES algorithm
- System.Security.Cryptography.RSA class
- asymmetric keys [.NET]
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- key containers
- Advanced Encryption Standard algorithm
- encryption [.NET], asymmetric keys
ms.assetid: a164ba4f-e596-4bbe-a9ca-f214fe89ed48
ms.openlocfilehash: 1c824b00a1df920108cfcd8c4590b680020cdf3e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555790"
---
# <a name="how-to-encrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="a8cab-102">Instrukcje: Szyfrowanie elementów XML przy użyciu kluczy asymetrycznych</span><span class="sxs-lookup"><span data-stu-id="a8cab-102">How to: Encrypt XML Elements with Asymmetric Keys</span></span>

<span data-ttu-id="a8cab-103">Można użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw do szyfrowania elementu w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="a8cab-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="a8cab-104">Szyfrowanie XML jest standardowym sposobem wymiany i przechowywania zaszyfrowanych danych XML bez obaw o dane, które są łatwo odczytywane.</span><span class="sxs-lookup"><span data-stu-id="a8cab-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="a8cab-105">Aby uzyskać więcej informacji na temat standardu szyfrowania XML, zapoznaj się z artykułem Specyfikacja organizacja World Wide Web Consortium (W3C) dla szyfrowania XML znajdującego się w temacie <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="a8cab-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="a8cab-106">Możesz użyć szyfrowania XML, aby zamienić dowolny element XML lub dokument z <`EncryptedData`> element, który zawiera zaszyfrowane dane XML.</span><span class="sxs-lookup"><span data-stu-id="a8cab-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span>  <span data-ttu-id="a8cab-107">`EncryptedData`Element> <może również zawierać elementy podrzędne, które zawierają informacje o kluczach i procesach używanych podczas szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="a8cab-107">The <`EncryptedData`> element can also contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="a8cab-108">Szyfrowanie XML pozwala dokument może zawierać wiele zaszyfrowanych elementów i umożliwia wielokrotne szyfrowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="a8cab-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="a8cab-109">Przykład kodu w tej procedurze pokazuje, jak utworzyć <`EncryptedData` element> wraz z kilkoma innymi elementami podrzędnymi, które można później użyć podczas odszyfrowywania.</span><span class="sxs-lookup"><span data-stu-id="a8cab-109">The code example in this procedure shows how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
 <span data-ttu-id="a8cab-110">Ten przykład szyfruje element XML przy użyciu dwóch kluczy.</span><span class="sxs-lookup"><span data-stu-id="a8cab-110">This example encrypts an XML element using two keys.</span></span>  <span data-ttu-id="a8cab-111">Generuje parę kluczy publiczny/prywatny RSA i zapisuje parę kluczy do kontenera Secure Key.</span><span class="sxs-lookup"><span data-stu-id="a8cab-111">It generates an RSA public/private key pair and saves the key pair to a secure key container.</span></span>  <span data-ttu-id="a8cab-112">W przykładzie tworzony jest oddzielny klucz sesji przy użyciu algorytmu Advanced Encryption Standard (AES).</span><span class="sxs-lookup"><span data-stu-id="a8cab-112">The example then creates a separate session key using the Advanced Encryption Standard (AES) algorithm.</span></span>  <span data-ttu-id="a8cab-113">W przykładzie zastosowano klucz sesji AES do szyfrowania dokumentu XML, a następnie jest on stosowany do szyfrowania klucza sesji AES przy użyciu klucza publicznego RSA.</span><span class="sxs-lookup"><span data-stu-id="a8cab-113">The example uses the AES session key to encrypt the XML document and then uses the RSA public key to encrypt the AES session key.</span></span>  <span data-ttu-id="a8cab-114">Na koniec przykład zapisuje zaszyfrowany klucz sesji AES i zaszyfrowane dane XML w dokumencie XML w ramach nowego `EncryptedData` elementu> <.</span><span class="sxs-lookup"><span data-stu-id="a8cab-114">Finally, the example saves the encrypted AES session key and the encrypted XML data to the XML document within a new <`EncryptedData`> element.</span></span>  
  
 <span data-ttu-id="a8cab-115">Aby odszyfrować element XML, należy pobrać klucz prywatny RSA z kontenera kluczy, użyć go do odszyfrowania klucza sesji, a następnie użyć klucza sesji do odszyfrowania dokumentu.</span><span class="sxs-lookup"><span data-stu-id="a8cab-115">To decrypt the XML element, you retrieve the RSA private key from the key container, use it to decrypt the session key, and then use the session key to decrypt the document.</span></span>  <span data-ttu-id="a8cab-116">Aby uzyskać więcej informacji na temat odszyfrowywania elementu XML, który został zaszyfrowany przy użyciu tej procedury, zobacz [How to: Deszyfruj elementy XML za pomocą kluczy asymetrycznych](how-to-decrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="a8cab-116">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Asymmetric Keys](how-to-decrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 <span data-ttu-id="a8cab-117">Ten przykład jest odpowiedni dla sytuacji, w których wiele aplikacji musi udostępniać zaszyfrowane dane lub w przypadku, gdy aplikacja wymaga zapisywania zaszyfrowanych danych między uruchomionymi danymi.</span><span class="sxs-lookup"><span data-stu-id="a8cab-117">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>
  
### <a name="to-encrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="a8cab-118">Aby zaszyfrować element XML kluczem asymetrycznym</span><span class="sxs-lookup"><span data-stu-id="a8cab-118">To encrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="a8cab-119">Utwórz <xref:System.Security.Cryptography.CspParameters> obiekt i określ nazwę kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="a8cab-119">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="a8cab-120">Generuj klucz symetryczny przy użyciu <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy.</span><span class="sxs-lookup"><span data-stu-id="a8cab-120">Generate a symmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="a8cab-121">Klucz jest automatycznie zapisywany do kontenera kluczy podczas przekazywania <xref:System.Security.Cryptography.CspParameters> obiektu do konstruktora <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy.</span><span class="sxs-lookup"><span data-stu-id="a8cab-121">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="a8cab-122">Ten klucz będzie używany do szyfrowania klucza sesji AES i można go później pobrać w celu odszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="a8cab-122">This key will be used to encrypt the AES session key and can be retrieved later to decrypt it.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="a8cab-123">Utwórz <xref:System.Xml.XmlDocument> obiekt przez załadowanie pliku XML z dysku.</span><span class="sxs-lookup"><span data-stu-id="a8cab-123">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="a8cab-124"><xref:System.Xml.XmlDocument>Obiekt zawiera element XML do zaszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="a8cab-124">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#4)]  
  
4. <span data-ttu-id="a8cab-125">Znajdź określony element w <xref:System.Xml.XmlDocument> obiekcie i Utwórz nowy <xref:System.Xml.XmlElement> obiekt do reprezentowania elementu, który chcesz zaszyfrować.</span><span class="sxs-lookup"><span data-stu-id="a8cab-125">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span> <span data-ttu-id="a8cab-126">W tym przykładzie `"creditcard"` element jest szyfrowany.</span><span class="sxs-lookup"><span data-stu-id="a8cab-126">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
5. <span data-ttu-id="a8cab-127">Utwórz nowy klucz sesji przy użyciu <xref:System.Security.Cryptography.Aes> klasy.</span><span class="sxs-lookup"><span data-stu-id="a8cab-127">Create a new session key using the <xref:System.Security.Cryptography.Aes> class.</span></span>  <span data-ttu-id="a8cab-128">Ten klucz spowoduje zaszyfrowanie elementu XML, a następnie zaszyfrowanie go i umieszczenie w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="a8cab-128">This key will encrypt the XML element, and then be encrypted itself and placed in the XML document.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
6. <span data-ttu-id="a8cab-129">Utwórz nowe wystąpienie <xref:System.Security.Cryptography.Xml.EncryptedXml> klasy i użyj go do szyfrowania określonego elementu przy użyciu klucza sesji.</span><span class="sxs-lookup"><span data-stu-id="a8cab-129">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the session key.</span></span>  <span data-ttu-id="a8cab-130"><xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A>Metoda zwraca zaszyfrowany element jako tablicę szyfrowanych bajtów.</span><span class="sxs-lookup"><span data-stu-id="a8cab-130">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
7. <span data-ttu-id="a8cab-131">Utwórz <xref:System.Security.Cryptography.Xml.EncryptedData> obiekt i wypełnij go identyfikatorem URL zaszyfrowanego elementu XML.</span><span class="sxs-lookup"><span data-stu-id="a8cab-131">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the encrypted XML element.</span></span>  <span data-ttu-id="a8cab-132">Ten identyfikator adresu URL umożliwia osobie odszyfrowanej, że kod XML zawiera zaszyfrowany element.</span><span class="sxs-lookup"><span data-stu-id="a8cab-132">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="a8cab-133">Możesz użyć pola, <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> Aby określić identyfikator URL.</span><span class="sxs-lookup"><span data-stu-id="a8cab-133">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  <span data-ttu-id="a8cab-134">Element XML w postaci zwykłego tekstu zostanie zastąpiony przez <`EncryptedData` element> hermetyzowany przez ten <xref:System.Security.Cryptography.Xml.EncryptedData> obiekt.</span><span class="sxs-lookup"><span data-stu-id="a8cab-134">The plaintext XML element will be replaced by an <`EncryptedData`> element encapsulated by this <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
8. <span data-ttu-id="a8cab-135">Utwórz <xref:System.Security.Cryptography.Xml.EncryptionMethod> obiekt, który jest zainicjowany do identyfikatora URL algorytmu kryptograficznego używanego do generowania klucza sesji.</span><span class="sxs-lookup"><span data-stu-id="a8cab-135">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the session key.</span></span>  <span data-ttu-id="a8cab-136">Przekaż <xref:System.Security.Cryptography.Xml.EncryptionMethod> obiekt do <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="a8cab-136">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#9)]  
  
9. <span data-ttu-id="a8cab-137">Utwórz <xref:System.Security.Cryptography.Xml.EncryptedKey> obiekt, który będzie zawierać zaszyfrowany klucz sesji.</span><span class="sxs-lookup"><span data-stu-id="a8cab-137">Create an <xref:System.Security.Cryptography.Xml.EncryptedKey> object to contain the encrypted session key.</span></span>  <span data-ttu-id="a8cab-138">Zaszyfruj klucz sesji, Dodaj go do <xref:System.Security.Cryptography.Xml.EncryptedKey> obiektu, a następnie wprowadź nazwę klucza sesji i adres URL identyfikatora klucza.</span><span class="sxs-lookup"><span data-stu-id="a8cab-138">Encrypt the session key, add it to the <xref:System.Security.Cryptography.Xml.EncryptedKey> object, and enter a session key name and key identifier URL.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#10)]  
  
10. <span data-ttu-id="a8cab-139">Utwórz nowy <xref:System.Security.Cryptography.Xml.DataReference> obiekt, który mapuje dane zaszyfrowane do określonego klucza sesji.</span><span class="sxs-lookup"><span data-stu-id="a8cab-139">Create a new <xref:System.Security.Cryptography.Xml.DataReference> object that maps the encrypted data to a particular session key.</span></span>  <span data-ttu-id="a8cab-140">Ten opcjonalny krok pozwala łatwo określić, że wiele części dokumentu XML było szyfrowanych za pomocą jednego klucza.</span><span class="sxs-lookup"><span data-stu-id="a8cab-140">This optional step allows you to easily specify that multiple parts of an XML document were encrypted by a single key.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#11)]  
  
11. <span data-ttu-id="a8cab-141">Dodaj zaszyfrowany klucz do <xref:System.Security.Cryptography.Xml.EncryptedData> obiektu.</span><span class="sxs-lookup"><span data-stu-id="a8cab-141">Add the encrypted key to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#12)]  
  
12. <span data-ttu-id="a8cab-142">Utwórz nowy <xref:System.Security.Cryptography.Xml.KeyInfo> obiekt, aby określić nazwę klucza RSA.</span><span class="sxs-lookup"><span data-stu-id="a8cab-142">Create a new <xref:System.Security.Cryptography.Xml.KeyInfo> object to specify the name of the RSA key.</span></span>  <span data-ttu-id="a8cab-143">Dodaj go do <xref:System.Security.Cryptography.Xml.EncryptedData> obiektu.</span><span class="sxs-lookup"><span data-stu-id="a8cab-143">Add it to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span> <span data-ttu-id="a8cab-144">Dzięki temu odszyfrowanie umożliwia zidentyfikowanie poprawnego klucza asymetrycznego do użycia podczas odszyfrowywania klucza sesji.</span><span class="sxs-lookup"><span data-stu-id="a8cab-144">This helps the decrypting party identify the correct asymmetric key to use when decrypting the session key.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#13)]  
  
13. <span data-ttu-id="a8cab-145">Dodaj dane zaszyfrowanego elementu do <xref:System.Security.Cryptography.Xml.EncryptedData> obiektu.</span><span class="sxs-lookup"><span data-stu-id="a8cab-145">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#14)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#14)]  
  
14. <span data-ttu-id="a8cab-146">Zamień element z oryginalnego obiektu na <xref:System.Xml.XmlDocument> <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span><span class="sxs-lookup"><span data-stu-id="a8cab-146">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#15)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#15)]  
  
15. <span data-ttu-id="a8cab-147">Zapisz <xref:System.Xml.XmlDocument> obiekt.</span><span class="sxs-lookup"><span data-stu-id="a8cab-147">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#16)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="a8cab-148">Przykład</span><span class="sxs-lookup"><span data-stu-id="a8cab-148">Example</span></span>  
 <span data-ttu-id="a8cab-149">W tym przykładzie przyjęto założenie, że plik o nazwie `"test.xml"` istnieje w tym samym katalogu co skompilowany program.</span><span class="sxs-lookup"><span data-stu-id="a8cab-149">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="a8cab-150">Zakłada również, że `"test.xml"` zawiera `"creditcard"` element.</span><span class="sxs-lookup"><span data-stu-id="a8cab-150">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="a8cab-151">Można umieścić następujący kod XML w pliku o nazwie `test.xml` i użyć go w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="a8cab-151">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a8cab-152">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="a8cab-152">Compiling the Code</span></span>  
  
- <span data-ttu-id="a8cab-153">W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="a8cab-153">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="a8cab-154">W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="a8cab-154">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="a8cab-155">Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .</span><span class="sxs-lookup"><span data-stu-id="a8cab-155">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="a8cab-156">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="a8cab-156">.NET Security</span></span>

<span data-ttu-id="a8cab-157">Nigdy nie przechowuj symetrycznego klucza kryptograficznego w postaci zwykłego tekstu lub przesyłaj klucz symetryczny między maszynami w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="a8cab-157">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="a8cab-158">Ponadto nigdy nie należy przechowywać ani przenosić klucza prywatnego pary kluczy asymetrycznych w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="a8cab-158">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="a8cab-159">Aby uzyskać więcej informacji na temat symetrycznych i asymetrycznych kluczy kryptograficznych, zobacz [generowanie kluczy do szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="a8cab-159">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="a8cab-160">Nigdy nie osadzaj klucza bezpośrednio w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="a8cab-160">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="a8cab-161">Klucze osadzone można łatwo odczytywać z zestawu przy użyciu [Ildasm.exe (Il dezasembler)](../../framework/tools/ildasm-exe-il-disassembler.md) lub otwierając zestaw w edytorze tekstu, takim jak Notatnik.</span><span class="sxs-lookup"><span data-stu-id="a8cab-161">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
<span data-ttu-id="a8cab-162">Gdy skończysz korzystać z klucza kryptograficznego, usuń go z pamięci przez ustawienie każdego bajtu na zero lub przez wywołanie <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> metody zarządzanej klasy kryptografii.</span><span class="sxs-lookup"><span data-stu-id="a8cab-162">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="a8cab-163">Klucze kryptograficzne mogą być czasami odczytywane z pamięci przez debuger lub odczytywane z dysku twardego, jeśli lokalizacja pamięci jest stronicowana na dysku.</span><span class="sxs-lookup"><span data-stu-id="a8cab-163">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8cab-164">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a8cab-164">See also</span></span>

- [<span data-ttu-id="a8cab-165">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="a8cab-165">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="a8cab-166">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="a8cab-166">Cryptographic Services</span></span>](cryptographic-services.md)
- <span data-ttu-id="a8cab-167">[Kryptografia międzyplatformowa](cross-platform-cryptography.md)- <xref:System.Security.Cryptography.Xml></span><span class="sxs-lookup"><span data-stu-id="a8cab-167">[Cross-Platform Cryptography](cross-platform-cryptography.md)- <xref:System.Security.Cryptography.Xml></span></span>
- [<span data-ttu-id="a8cab-168">Instrukcje: Odszyfrowywanie elementów XML przy użyciu kluczy asymetrycznych</span><span class="sxs-lookup"><span data-stu-id="a8cab-168">How to: Decrypt XML Elements with Asymmetric Keys</span></span>](how-to-decrypt-xml-elements-with-asymmetric-keys.md)
- [<span data-ttu-id="a8cab-169">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a8cab-169">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
