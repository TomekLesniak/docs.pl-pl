---
title: 'Instrukcje: Odszyfrowywanie elementów XML za pomocą certyfikatów X.509'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
ms.openlocfilehash: f60947a3b722f33c88b696d47c6a4000a1cb076b
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555737"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="219d5-102">Instrukcje: Odszyfrowywanie elementów XML za pomocą certyfikatów X.509</span><span class="sxs-lookup"><span data-stu-id="219d5-102">How to: Decrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="219d5-103">Można użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw do szyfrowania i odszyfrowywania elementu w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="219d5-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="219d5-104">Szyfrowanie XML jest standardowym sposobem wymiany i przechowywania zaszyfrowanych danych XML bez obaw o dane, które są łatwo odczytywane.</span><span class="sxs-lookup"><span data-stu-id="219d5-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="219d5-105">Aby uzyskać więcej informacji na temat standardu szyfrowania XML, zapoznaj się z artykułem Specyfikacja organizacja World Wide Web Consortium (W3C) dla szyfrowania XML znajdującego się w temacie <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="219d5-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="219d5-106">Ten przykład odszyfrowuje element XML, który został zaszyfrowany przy użyciu metod opisanych w: [jak szyfrować elementy XML za pomocą certyfikatów X. 509](how-to-encrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="219d5-106">This example decrypts an XML element that was encrypted using the methods described in: [How to: Encrypt XML Elements with X.509 Certificates](how-to-encrypt-xml-elements-with-x-509-certificates.md).</span></span>  <span data-ttu-id="219d5-107">Znajduje `EncryptedData` element> <, odszyfrowuje element, a następnie zamienia element na oryginalny element XML w formacie zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="219d5-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
<span data-ttu-id="219d5-108">Przykład kodu w tej procedurze odszyfrowuje element XML przy użyciu certyfikatu X. 509 z lokalnego magazynu certyfikatów bieżącego konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="219d5-108">The code example in this procedure decrypts an XML element using an X.509 certificate from the local certificate store of the current user account.</span></span>  <span data-ttu-id="219d5-109">W przykładzie używa <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> metody do automatycznego pobierania certyfikatu X. 509 i odszyfrowywania klucza sesji przechowywanego w <> elementu `EncryptedKey` <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="219d5-109">The example uses the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to automatically retrieve the X.509 certificate and decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="219d5-110"><xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>Metoda następnie automatycznie używa klucza sesji do odszyfrowania elementu XML.</span><span class="sxs-lookup"><span data-stu-id="219d5-110">The <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method then automatically uses the session key to decrypt the XML element.</span></span>  
  
<span data-ttu-id="219d5-111">Ten przykład jest odpowiedni dla sytuacji, w których wiele aplikacji musi udostępniać zaszyfrowane dane lub w przypadku, gdy aplikacja wymaga zapisywania zaszyfrowanych danych między uruchomionymi danymi.</span><span class="sxs-lookup"><span data-stu-id="219d5-111">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="219d5-112">Aby odszyfrować element XML z certyfikatem X.509</span><span class="sxs-lookup"><span data-stu-id="219d5-112">To decrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="219d5-113">Utwórz <xref:System.Xml.XmlDocument> obiekt przez załadowanie pliku XML z dysku.</span><span class="sxs-lookup"><span data-stu-id="219d5-113">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="219d5-114"><xref:System.Xml.XmlDocument>Obiekt zawiera element XML do odszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="219d5-114">The <xref:System.Xml.XmlDocument> object contains the XML element to decrypt.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. <span data-ttu-id="219d5-115">Utwórz nowy <xref:System.Security.Cryptography.Xml.EncryptedXml> obiekt przez przekazanie <xref:System.Xml.XmlDocument> obiektu do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="219d5-115">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object by passing the <xref:System.Xml.XmlDocument> object to the constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. <span data-ttu-id="219d5-116">Odszyfruj dokument XML przy użyciu <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="219d5-116">Decrypt the XML document using the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. <span data-ttu-id="219d5-117">Zapisz <xref:System.Xml.XmlDocument> obiekt.</span><span class="sxs-lookup"><span data-stu-id="219d5-117">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="219d5-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="219d5-118">Example</span></span>

<span data-ttu-id="219d5-119">W tym przykładzie przyjęto założenie, że plik o nazwie `"test.xml"` istnieje w tym samym katalogu co skompilowany program.</span><span class="sxs-lookup"><span data-stu-id="219d5-119">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="219d5-120">Zakłada również, że `"test.xml"` zawiera `"creditcard"` element.</span><span class="sxs-lookup"><span data-stu-id="219d5-120">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="219d5-121">Można umieścić następujący kod XML w pliku o nazwie `test.xml` i użyć go w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="219d5-121">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
[!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="219d5-122">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="219d5-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="219d5-123">W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="219d5-123">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="219d5-124">W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="219d5-124">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>

- <span data-ttu-id="219d5-125">Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .</span><span class="sxs-lookup"><span data-stu-id="219d5-125">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="219d5-126">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="219d5-126">.NET Security</span></span>

<span data-ttu-id="219d5-127">Certyfikat X. 509 użyty w tym przykładzie służy tylko do celów testowych.</span><span class="sxs-lookup"><span data-stu-id="219d5-127">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="219d5-128">Aplikacje powinny używać certyfikatu X. 509 wygenerowanego przez zaufany urząd certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="219d5-128">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219d5-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="219d5-129">See also</span></span>

- [<span data-ttu-id="219d5-130">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="219d5-130">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="219d5-131">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="219d5-131">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="219d5-132">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="219d5-132">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="219d5-133">Instrukcje: Szyfrowanie elementów XML za pomocą certyfikatów X.509</span><span class="sxs-lookup"><span data-stu-id="219d5-133">How to: Encrypt XML Elements with X.509 Certificates</span></span>](how-to-encrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="219d5-134">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="219d5-134">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
