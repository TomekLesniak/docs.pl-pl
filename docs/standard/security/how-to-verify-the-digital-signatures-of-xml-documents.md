---
title: 'Instrukcje: Sprawdzanie podpisów cyfrowych w dokumentach XML'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSA class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
ms.openlocfilehash: b9b2dc6a558d1fd6acd2922a7c8ad82ce8776c26
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557050"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="1eab8-102">Instrukcje: Sprawdzanie podpisów cyfrowych w dokumentach XML</span><span class="sxs-lookup"><span data-stu-id="1eab8-102">How to: Verify the Digital Signatures of XML Documents</span></span>

<span data-ttu-id="1eab8-103">Możesz użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw, aby zweryfikować dane XML podpisane przy użyciu podpisu cyfrowego.</span><span class="sxs-lookup"><span data-stu-id="1eab8-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span> <span data-ttu-id="1eab8-104">Podpisy cyfrowe XML (XMLDSIG) pozwalają sprawdzić, czy dane nie zostały zmienione po podpisaniu.</span><span class="sxs-lookup"><span data-stu-id="1eab8-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span> <span data-ttu-id="1eab8-105">Aby uzyskać więcej informacji na temat standardu XMLDSIG, zobacz specyfikację organizacja World Wide Web Consortium (W3C) pod adresem <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="1eab8-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at <https://www.w3.org/TR/xmldsig-core/>.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1eab8-106">Kod w tym artykule ma zastosowanie do systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="1eab8-106">The code in this article applies to Windows.</span></span>

<span data-ttu-id="1eab8-107">W przykładzie kodu w tej procedurze pokazano, jak sprawdzić podpis cyfrowy XML zawarty w <`Signature`> elementu.</span><span class="sxs-lookup"><span data-stu-id="1eab8-107">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="1eab8-108">Przykład pobiera klucz publiczny RSA z kontenera kluczy, a następnie używa klucza do zweryfikowania podpisu.</span><span class="sxs-lookup"><span data-stu-id="1eab8-108">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
<span data-ttu-id="1eab8-109">Aby uzyskać informacje na temat tworzenia podpisu cyfrowego, który można zweryfikować przy użyciu tej metody, zobacz [How to: Sign XML Documents with Digital Signatures](how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="1eab8-109">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="1eab8-110">Aby sprawdzić podpis cyfrowy dokumentu XML</span><span class="sxs-lookup"><span data-stu-id="1eab8-110">To verify the digital signature of an XML document</span></span>  
  
1. <span data-ttu-id="1eab8-111">Aby sprawdzić dokument, należy użyć tego samego klucza asymetrycznego, który został użyty do podpisywania.</span><span class="sxs-lookup"><span data-stu-id="1eab8-111">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="1eab8-112">Utwórz <xref:System.Security.Cryptography.CspParameters> obiekt i określ nazwę kontenera kluczy, który został użyty do podpisywania.</span><span class="sxs-lookup"><span data-stu-id="1eab8-112">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="1eab8-113">Pobierz klucz publiczny przy użyciu <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy.</span><span class="sxs-lookup"><span data-stu-id="1eab8-113">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="1eab8-114">Klucz jest ładowany automatycznie z kontenera kluczy według nazwy podczas przekazywania <xref:System.Security.Cryptography.CspParameters> obiektu do konstruktora <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy.</span><span class="sxs-lookup"><span data-stu-id="1eab8-114">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="1eab8-115">Utwórz <xref:System.Xml.XmlDocument> obiekt przez załadowanie pliku XML z dysku.</span><span class="sxs-lookup"><span data-stu-id="1eab8-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="1eab8-116"><xref:System.Xml.XmlDocument>Obiekt zawiera podpisany dokument XML do zweryfikowania.</span><span class="sxs-lookup"><span data-stu-id="1eab8-116">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="1eab8-117">Utwórz nowy <xref:System.Security.Cryptography.Xml.SignedXml> obiekt i przekaż <xref:System.Xml.XmlDocument> do niego obiekt.</span><span class="sxs-lookup"><span data-stu-id="1eab8-117">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="1eab8-118">Znajdź element <`signature`> i Utwórz nowy <xref:System.Xml.XmlNodeList> obiekt.</span><span class="sxs-lookup"><span data-stu-id="1eab8-118">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="1eab8-119">Załaduj plik XML pierwszego <`signature`> elementu do <xref:System.Security.Cryptography.Xml.SignedXml> obiektu.</span><span class="sxs-lookup"><span data-stu-id="1eab8-119">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="1eab8-120">Sprawdź podpis przy użyciu <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> metody i klucza publicznego RSA.</span><span class="sxs-lookup"><span data-stu-id="1eab8-120">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="1eab8-121">Ta metoda zwraca wartość logiczną wskazującą powodzenie lub niepowodzenie.</span><span class="sxs-lookup"><span data-stu-id="1eab8-121">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="1eab8-122">Przykład</span><span class="sxs-lookup"><span data-stu-id="1eab8-122">Example</span></span>

<span data-ttu-id="1eab8-123">W tym przykładzie przyjęto założenie, że plik o nazwie `"test.xml"` istnieje w tym samym katalogu co skompilowany program.</span><span class="sxs-lookup"><span data-stu-id="1eab8-123">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="1eab8-124">`"test.xml"`Plik musi być podpisany przy użyciu technik opisanych w [instrukcje: podpisywanie dokumentów XML za pomocą podpisów cyfrowych](how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="1eab8-124">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
[!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
[!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1eab8-125">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="1eab8-125">Compiling the Code</span></span>  
  
- <span data-ttu-id="1eab8-126">W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="1eab8-126">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="1eab8-127">W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="1eab8-127">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="1eab8-128">Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .</span><span class="sxs-lookup"><span data-stu-id="1eab8-128">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="1eab8-129">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="1eab8-129">.NET Security</span></span>

<span data-ttu-id="1eab8-130">Nigdy nie przechowuj ani nie przesyłaj klucza prywatnego pary kluczy asymetrycznych w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="1eab8-130">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="1eab8-131">Aby uzyskać więcej informacji na temat symetrycznych i asymetrycznych kluczy kryptograficznych, zobacz [generowanie kluczy do szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="1eab8-131">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="1eab8-132">Nie osadzaj klucza prywatnego bezpośrednio w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="1eab8-132">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="1eab8-133">Klucze osadzone można łatwo odczytywać z zestawu przy użyciu [Ildasm.exe (Il dezasembler)](../../framework/tools/ildasm-exe-il-disassembler.md) lub otwierając zestaw w edytorze tekstu, takim jak Notatnik.</span><span class="sxs-lookup"><span data-stu-id="1eab8-133">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eab8-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1eab8-134">See also</span></span>

- [<span data-ttu-id="1eab8-135">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="1eab8-135">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="1eab8-136">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="1eab8-136">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="1eab8-137">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="1eab8-137">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="1eab8-138">Instrukcje: Podpisywanie dokumentów XML za pomocą podpisów cyfrowych</span><span class="sxs-lookup"><span data-stu-id="1eab8-138">How to: Sign XML Documents with Digital Signatures</span></span>](how-to-sign-xml-documents-with-digital-signatures.md)
- [<span data-ttu-id="1eab8-139">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1eab8-139">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
