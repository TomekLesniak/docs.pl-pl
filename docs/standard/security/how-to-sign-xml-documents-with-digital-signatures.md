---
title: 'Instrukcje: Podpisywanie dokumentów XML za pomocą podpisów cyfrowych'
description: Dowiedz się, jak podpisywać dokumenty XML za pomocą podpisów cyfrowych. Użyj klas w przestrzeni nazw System.Security.Cryptography.Xml w programie .NET.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSA class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
ms.openlocfilehash: 2cb63fd91b1aeb51c762975103ea665e0d8539b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726681"
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a><span data-ttu-id="6e8fd-104">Instrukcje: Podpisywanie dokumentów XML za pomocą podpisów cyfrowych</span><span class="sxs-lookup"><span data-stu-id="6e8fd-104">How to: Sign XML Documents with Digital Signatures</span></span>

<span data-ttu-id="6e8fd-105">Możesz użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw, aby podpisać dokument XML lub część dokumentu XML z podpisem cyfrowym.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-105">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to sign an XML document or part of an XML document with a digital signature.</span></span>  <span data-ttu-id="6e8fd-106">Podpisy cyfrowe XML (XMLDSIG) pozwalają sprawdzić, czy dane nie zostały zmienione po podpisaniu.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-106">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span>  <span data-ttu-id="6e8fd-107">Aby uzyskać więcej informacji na temat standardu XMLDSIG, zobacz [składnia i przetwarzanie w formacie XML](https://www.w3.org/TR/xmldsig-core/)zalecenia dotyczące organizacja World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="6e8fd-107">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e8fd-108">Kod w tym artykule ma zastosowanie do systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-108">The code in this article applies to Windows.</span></span>

<span data-ttu-id="6e8fd-109">Przykład kodu w tej procedurze pokazuje, jak cyfrowo podpisać cały dokument XML i dołączyć podpis do dokumentu w <`Signature`> elementu.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-109">The code example in this procedure demonstrates how to digitally sign an entire XML document and attach the signature to the document in a <`Signature`> element.</span></span>  <span data-ttu-id="6e8fd-110">Przykład tworzy klucz podpisywania RSA, dodaje klucz do kontenera klucza zabezpieczeń, a następnie używa klucza do cyfrowego podpisywania dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-110">The example creates an RSA signing key, adds the key to a secure key container, and then uses the key to digitally sign an XML document.</span></span>  <span data-ttu-id="6e8fd-111">Następnie można pobrać klucz w celu zweryfikowania podpisu cyfrowego XML lub można go użyć do podpisania innego dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-111">The key can then be retrieved to verify the XML digital signature, or can be used to sign another XML document.</span></span>  
  
<span data-ttu-id="6e8fd-112">Aby uzyskać informacje na temat weryfikowania podpisu cyfrowego XML, który został utworzony przy użyciu tej procedury, zobacz [How to: Verify Digital Signatures of XML Documents](how-to-verify-the-digital-signatures-of-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="6e8fd-112">For information about how to verify an XML digital signature that was created using this procedure, see [How to: Verify the Digital Signatures of XML Documents](how-to-verify-the-digital-signatures-of-xml-documents.md).</span></span>  
  
### <a name="to-digitally-sign-an-xml-document"></a><span data-ttu-id="6e8fd-113">Aby podpisać cyfrowo dokument XML</span><span class="sxs-lookup"><span data-stu-id="6e8fd-113">To digitally sign an XML document</span></span>  
  
1. <span data-ttu-id="6e8fd-114">Utwórz <xref:System.Security.Cryptography.CspParameters> obiekt i określ nazwę kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-114">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="6e8fd-115">Generuj klucz asymetryczny przy użyciu <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-115">Generate an asymmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="6e8fd-116">Klucz jest automatycznie zapisywany do kontenera kluczy podczas przekazywania <xref:System.Security.Cryptography.CspParameters> obiektu do konstruktora <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-116">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="6e8fd-117">Ten klucz będzie używany do podpisywania dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-117">This key will be used to sign the XML document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="6e8fd-118">Utwórz <xref:System.Xml.XmlDocument> obiekt przez załadowanie pliku XML z dysku.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-118">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="6e8fd-119"><xref:System.Xml.XmlDocument>Obiekt zawiera element XML do zaszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-119">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="6e8fd-120">Utwórz nowy <xref:System.Security.Cryptography.Xml.SignedXml> obiekt i przekaż <xref:System.Xml.XmlDocument> do niego obiekt.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-120">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="6e8fd-121">Dodaj podpis klucza RSA do <xref:System.Security.Cryptography.Xml.SignedXml> obiektu.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-121">Add the signing RSA key to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="6e8fd-122">Utwórz obiekt opisujący <xref:System.Security.Cryptography.Xml.Reference> elementy do podpisania.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-122">Create a <xref:System.Security.Cryptography.Xml.Reference> object that describes what to sign.</span></span>  <span data-ttu-id="6e8fd-123">Aby podpisać cały dokument, należy ustawić <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> Właściwość na `""` .</span><span class="sxs-lookup"><span data-stu-id="6e8fd-123">To sign the entire document, set the <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> property to `""`.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="6e8fd-124">Dodaj <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> obiekt do <xref:System.Security.Cryptography.Xml.Reference> obiektu.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-124">Add an <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> object to the <xref:System.Security.Cryptography.Xml.Reference> object.</span></span>  <span data-ttu-id="6e8fd-125">Przekształcenie umożliwia weryfikatorowi reprezentowania danych XML w taki sam sposób, w jaki użyto osoby podpisującej.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-125">A transformation allows the verifier to represent the XML data in the identical manner that the signer used.</span></span>  <span data-ttu-id="6e8fd-126">Dane XML mogą być reprezentowane na różne sposoby, więc ten krok jest niezbędny do weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-126">XML data can be represented in different ways, so this step is vital to verification.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8. <span data-ttu-id="6e8fd-127">Dodaj <xref:System.Security.Cryptography.Xml.Reference> obiekt do <xref:System.Security.Cryptography.Xml.SignedXml> obiektu.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-127">Add the <xref:System.Security.Cryptography.Xml.Reference> object to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. <span data-ttu-id="6e8fd-128">Oblicz podpis, wywołując <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-128">Compute the signature by calling the <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> method.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. <span data-ttu-id="6e8fd-129">Pobierz reprezentację XML sygnatury (<`Signature` elementu>) i Zapisz ją w nowym <xref:System.Xml.XmlElement> obiekcie.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-129">Retrieve the XML representation of the signature (a <`Signature`> element) and save it to a new <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. <span data-ttu-id="6e8fd-130">Dołącz element do <xref:System.Xml.XmlDocument> obiektu.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-130">Append the element to the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. <span data-ttu-id="6e8fd-131">Zapisz dokument.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-131">Save the document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="6e8fd-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="6e8fd-132">Example</span></span>  

 <span data-ttu-id="6e8fd-133">W tym przykładzie przyjęto założenie, że plik o nazwie `test.xml` istnieje w tym samym katalogu co skompilowany program.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-133">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="6e8fd-134">Można umieścić następujący kod XML w pliku o nazwie `test.xml` i użyć go w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-134">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6e8fd-135">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="6e8fd-135">Compiling the Code</span></span>  
  
- <span data-ttu-id="6e8fd-136">W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="6e8fd-136">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="6e8fd-137">W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="6e8fd-137">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="6e8fd-138">Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .</span><span class="sxs-lookup"><span data-stu-id="6e8fd-138">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="6e8fd-139">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="6e8fd-139">.NET Security</span></span>

<span data-ttu-id="6e8fd-140">Nigdy nie przechowuj ani nie przesyłaj klucza prywatnego pary kluczy asymetrycznych w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-140">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="6e8fd-141">Aby uzyskać więcej informacji na temat symetrycznych i asymetrycznych kluczy kryptograficznych, zobacz [generowanie kluczy do szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="6e8fd-141">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="6e8fd-142">Nie osadzaj klucza prywatnego bezpośrednio w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-142">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="6e8fd-143">Klucze osadzone można łatwo odczytywać z zestawu przy użyciu [Ildasm.exe (Il dezasembler)](../../framework/tools/ildasm-exe-il-disassembler.md) lub otwierając zestaw w edytorze tekstu, takim jak Notatnik.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-143">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e8fd-144">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6e8fd-144">See also</span></span>

- [<span data-ttu-id="6e8fd-145">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="6e8fd-145">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="6e8fd-146">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="6e8fd-146">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="6e8fd-147">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="6e8fd-147">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="6e8fd-148">Instrukcje: Sprawdzanie podpisów cyfrowych w dokumentach XML</span><span class="sxs-lookup"><span data-stu-id="6e8fd-148">How to: Verify the Digital Signatures of XML Documents</span></span>](how-to-verify-the-digital-signatures-of-xml-documents.md)
- [<span data-ttu-id="6e8fd-149">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6e8fd-149">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
