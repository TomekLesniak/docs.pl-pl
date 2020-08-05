---
title: 'Instrukcje: Szyfrowanie elementów XML za pomocą certyfikatów X.509'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], X.509 certificates
- cryptography [.NET], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
ms.openlocfilehash: c978bea7336e64d6622aca4d21c7ef3317d73957
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555724"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="edc4e-102">Instrukcje: Szyfrowanie elementów XML za pomocą certyfikatów X.509</span><span class="sxs-lookup"><span data-stu-id="edc4e-102">How to: Encrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="edc4e-103">Można użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw do szyfrowania elementu w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="edc4e-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="edc4e-104">Szyfrowanie XML jest standardowym sposobem wymiany i przechowywania zaszyfrowanych danych XML bez obaw o dane, które są łatwo odczytywane.</span><span class="sxs-lookup"><span data-stu-id="edc4e-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="edc4e-105">Aby uzyskać więcej informacji na temat standardu szyfrowania XML, zapoznaj się z artykułem Specyfikacja organizacja World Wide Web Consortium (W3C) dla szyfrowania XML znajdującego się w temacie <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="edc4e-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="edc4e-106">Możesz użyć szyfrowania XML, aby zamienić dowolny element XML lub dokument z <`EncryptedData`> element, który zawiera zaszyfrowane dane XML.</span><span class="sxs-lookup"><span data-stu-id="edc4e-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="edc4e-107">`EncryptedData`Element> <może zawierać elementy podrzędne, które zawierają informacje o kluczach i procesach używanych podczas szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="edc4e-107">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="edc4e-108">Szyfrowanie XML pozwala dokument może zawierać wiele zaszyfrowanych elementów i umożliwia wielokrotne szyfrowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="edc4e-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="edc4e-109">Przykład kodu w tej procedurze pokazuje, jak utworzyć <`EncryptedData` element> wraz z kilkoma innymi elementami podrzędnymi, które można później użyć podczas odszyfrowywania.</span><span class="sxs-lookup"><span data-stu-id="edc4e-109">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
<span data-ttu-id="edc4e-110">Ten przykład szyfruje element XML przy użyciu dwóch kluczy.</span><span class="sxs-lookup"><span data-stu-id="edc4e-110">This example encrypts an XML element using two keys.</span></span> <span data-ttu-id="edc4e-111">Przykład programowo pobiera certyfikat i używa go do szyfrowania elementu XML przy użyciu <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="edc4e-111">The example programmatically retrieves a certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span> <span data-ttu-id="edc4e-112">Wewnętrznie <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> Metoda tworzy osobny klucz sesji i używa jej do szyfrowania dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="edc4e-112">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="edc4e-113">Ta metoda szyfruje klucz sesji i zapisuje go wraz z zaszyfrowanym kodem XML w ramach nowego `EncryptedData` elementu <>.</span><span class="sxs-lookup"><span data-stu-id="edc4e-113">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  

<span data-ttu-id="edc4e-114">Aby odszyfrować element XML, wywołaj <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> metodę, która automatycznie pobiera certyfikat X. 509 ze sklepu i wykonuje wymagane odszyfrowywanie.</span><span class="sxs-lookup"><span data-stu-id="edc4e-114">To decrypt the XML element, call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="edc4e-115">Aby uzyskać więcej informacji na temat odszyfrowywania elementu XML, który został zaszyfrowany przy użyciu tej procedury, zobacz [How to: Deszyfruj elementy XML za pomocą certyfikatów X. 509](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="edc4e-115">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
<span data-ttu-id="edc4e-116">Ten przykład jest odpowiedni dla sytuacji, w których wiele aplikacji musi udostępniać zaszyfrowane dane lub w przypadku, gdy aplikacja wymaga zapisywania zaszyfrowanych danych między uruchomionymi danymi.</span><span class="sxs-lookup"><span data-stu-id="edc4e-116">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="edc4e-117">Aby zaszyfrować element XML z certyfikatem X.509</span><span class="sxs-lookup"><span data-stu-id="edc4e-117">To encrypt an XML element with an X.509 certificate</span></span>  

<span data-ttu-id="edc4e-118">Aby uruchomić ten przykład, należy utworzyć certyfikat testowy i zapisać go w magazynie certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="edc4e-118">To run this example, you need to create a test certificate and save it in a certificate store.</span></span> <span data-ttu-id="edc4e-119">Instrukcje dotyczące tego zadania są dostępne tylko dla narzędzia do [tworzenia certyfikatów systemu Windows (Makecert.exe)](/windows/desktop/SecCrypto/makecert).</span><span class="sxs-lookup"><span data-stu-id="edc4e-119">Instructions for that task are provided only for the Windows [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert).</span></span>

1. <span data-ttu-id="edc4e-120">Użyj [Makecert.exe](/windows/desktop/SecCrypto/makecert) do wygenerowania certyfikatu test X. 509 i umieść go w lokalnym magazynie użytkowników.</span><span class="sxs-lookup"><span data-stu-id="edc4e-120">Use [Makecert.exe](/windows/desktop/SecCrypto/makecert) to generate a test X.509 certificate and place it in the local user store.</span></span> <span data-ttu-id="edc4e-121">Musisz wygenerować klucz wymiany i należy dokonać eksportu klucza.</span><span class="sxs-lookup"><span data-stu-id="edc4e-121">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="edc4e-122">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="edc4e-122">Run the following command:</span></span>  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2020 -e 01/01/2025 -sky exchange -ss my  
    ```  
  
2. <span data-ttu-id="edc4e-123">Utwórz <xref:System.Security.Cryptography.X509Certificates.X509Store> obiekt i zainicjuj go, aby otworzyć bieżący magazyn użytkowników.</span><span class="sxs-lookup"><span data-stu-id="edc4e-123">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. <span data-ttu-id="edc4e-124">Otwórz sklep w trybie tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="edc4e-124">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. <span data-ttu-id="edc4e-125">Zainicjuj <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> wszystkie certyfikaty w sklepie.</span><span class="sxs-lookup"><span data-stu-id="edc4e-125">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. <span data-ttu-id="edc4e-126">Wylicz certyfikaty w magazynie i Znajdź certyfikat z odpowiednią nazwą.</span><span class="sxs-lookup"><span data-stu-id="edc4e-126">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="edc4e-127">W tym przykładzie certyfikat ma nazwę `"CN=XML_ENC_TEST_CERT"` .</span><span class="sxs-lookup"><span data-stu-id="edc4e-127">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. <span data-ttu-id="edc4e-128">Zamknij sklep po zlokalizowaniu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="edc4e-128">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. <span data-ttu-id="edc4e-129">Utwórz <xref:System.Xml.XmlDocument> obiekt przez załadowanie pliku XML z dysku.</span><span class="sxs-lookup"><span data-stu-id="edc4e-129">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="edc4e-130"><xref:System.Xml.XmlDocument>Obiekt zawiera element XML do zaszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="edc4e-130">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. <span data-ttu-id="edc4e-131">Znajdź określony element w <xref:System.Xml.XmlDocument> obiekcie i Utwórz nowy <xref:System.Xml.XmlElement> obiekt do reprezentowania elementu, który chcesz zaszyfrować.</span><span class="sxs-lookup"><span data-stu-id="edc4e-131">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="edc4e-132">W tym przykładzie `"creditcard"` element jest szyfrowany.</span><span class="sxs-lookup"><span data-stu-id="edc4e-132">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="edc4e-133">Utwórz nowe wystąpienie <xref:System.Security.Cryptography.Xml.EncryptedXml> klasy i użyj go do szyfrowania określonego elementu przy użyciu certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="edc4e-133">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="edc4e-134"><xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>Metoda zwraca zaszyfrowany element jako <xref:System.Security.Cryptography.Xml.EncryptedData> obiekt.</span><span class="sxs-lookup"><span data-stu-id="edc4e-134">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="edc4e-135">Zamień element z oryginalnego obiektu na <xref:System.Xml.XmlDocument> <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span><span class="sxs-lookup"><span data-stu-id="edc4e-135">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="edc4e-136">Zapisz <xref:System.Xml.XmlDocument> obiekt.</span><span class="sxs-lookup"><span data-stu-id="edc4e-136">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="edc4e-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="edc4e-137">Example</span></span>  
 <span data-ttu-id="edc4e-138">W tym przykładzie przyjęto założenie, że plik o nazwie `"test.xml"` istnieje w tym samym katalogu co skompilowany program.</span><span class="sxs-lookup"><span data-stu-id="edc4e-138">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="edc4e-139">Zakłada również, że `"test.xml"` zawiera `"creditcard"` element.</span><span class="sxs-lookup"><span data-stu-id="edc4e-139">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="edc4e-140">Można umieścić następujący kod XML w pliku o nazwie `test.xml` i użyć go w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="edc4e-140">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="edc4e-141">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="edc4e-141">Compiling the Code</span></span>  
  
- <span data-ttu-id="edc4e-142">W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="edc4e-142">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="edc4e-143">W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="edc4e-143">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="edc4e-144">Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .</span><span class="sxs-lookup"><span data-stu-id="edc4e-144">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="edc4e-145">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="edc4e-145">.NET Security</span></span>
  
<span data-ttu-id="edc4e-146">Certyfikat X. 509 użyty w tym przykładzie służy tylko do celów testowych.</span><span class="sxs-lookup"><span data-stu-id="edc4e-146">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="edc4e-147">Aplikacje powinny używać certyfikatu X. 509 wygenerowanego przez zaufany urząd certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="edc4e-147">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc4e-148">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="edc4e-148">See also</span></span>

- [<span data-ttu-id="edc4e-149">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="edc4e-149">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="edc4e-150">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="edc4e-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="edc4e-151">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="edc4e-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="edc4e-152">Instrukcje: Odszyfrowywanie elementów XML za pomocą certyfikatów X.509</span><span class="sxs-lookup"><span data-stu-id="edc4e-152">How to: Decrypt XML Elements with X.509 Certificates</span></span>](how-to-decrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="edc4e-153">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="edc4e-153">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
