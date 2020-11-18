---
title: 'Instrukcje: Sprawdzanie podpisów cyfrowych w dokumentach XML'
ms.date: 07/14/2020
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
ms.openlocfilehash: 9cbebd34866b66c00bf4aca708d75e315b067b0d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820075"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a>Instrukcje: Sprawdzanie podpisów cyfrowych w dokumentach XML

Możesz użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw, aby zweryfikować dane XML podpisane przy użyciu podpisu cyfrowego. Podpisy cyfrowe XML (XMLDSIG) pozwalają sprawdzić, czy dane nie zostały zmienione po podpisaniu. Aby uzyskać więcej informacji na temat standardu XMLDSIG, zobacz specyfikację organizacja World Wide Web Consortium (W3C) pod adresem <https://www.w3.org/TR/xmldsig-core/> .
  
> [!NOTE]
> Kod w tym artykule ma zastosowanie do systemu Windows.

W przykładzie kodu w tej procedurze pokazano, jak sprawdzić podpis cyfrowy XML zawarty w <`Signature`> elementu.  Przykład pobiera klucz publiczny RSA z kontenera kluczy, a następnie używa klucza do zweryfikowania podpisu.  
  
Aby uzyskać informacje na temat tworzenia podpisu cyfrowego, który można zweryfikować przy użyciu tej metody, zobacz [How to: Sign XML Documents with Digital Signatures](how-to-sign-xml-documents-with-digital-signatures.md).  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a>Aby sprawdzić podpis cyfrowy dokumentu XML  
  
1. Aby sprawdzić dokument, należy użyć tego samego klucza asymetrycznego, który został użyty do podpisywania.  Utwórz <xref:System.Security.Cryptography.CspParameters> obiekt i określ nazwę kontenera kluczy, który został użyty do podpisywania.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. Pobierz klucz publiczny przy użyciu <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy.  Klucz jest ładowany automatycznie z kontenera kluczy według nazwy podczas przekazywania <xref:System.Security.Cryptography.CspParameters> obiektu do konstruktora <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. Utwórz <xref:System.Xml.XmlDocument> obiekt przez załadowanie pliku XML z dysku.  <xref:System.Xml.XmlDocument>Obiekt zawiera podpisany dokument XML do zweryfikowania.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. Utwórz nowy <xref:System.Security.Cryptography.Xml.SignedXml> obiekt i przekaż <xref:System.Xml.XmlDocument> do niego obiekt.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. Znajdź element <`signature`> i Utwórz nowy <xref:System.Xml.XmlNodeList> obiekt.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. Załaduj plik XML pierwszego <`signature`> elementu do <xref:System.Security.Cryptography.Xml.SignedXml> obiektu.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. Sprawdź podpis przy użyciu <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> metody i klucza publicznego RSA.  Ta metoda zwraca wartość logiczną wskazującą powodzenie lub niepowodzenie.  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a>Przykład

W tym przykładzie przyjęto założenie, że plik o nazwie `"test.xml"` istnieje w tym samym katalogu co skompilowany program.  `"test.xml"`Plik musi być podpisany przy użyciu technik opisanych w [instrukcje: podpisywanie dokumentów XML za pomocą podpisów cyfrowych](how-to-sign-xml-documents-with-digital-signatures.md).  
  
[!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
[!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
- W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .

- W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).
  
- Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .  
  
## <a name="net-security"></a>Zabezpieczenia platformy .NET

Nigdy nie przechowuj ani nie przesyłaj klucza prywatnego pary kluczy asymetrycznych w postaci zwykłego tekstu.  Aby uzyskać więcej informacji na temat symetrycznych i asymetrycznych kluczy kryptograficznych, zobacz [generowanie kluczy do szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md).  
  
Nie osadzaj klucza prywatnego bezpośrednio w kodzie źródłowym.  Klucze osadzone można łatwo odczytywać z zestawu przy użyciu [Ildasm.exe (Il dezasembler)](../../framework/tools/ildasm-exe-il-disassembler.md) lub otwierając zestaw w edytorze tekstu, takim jak Notatnik.  
  
## <a name="see-also"></a>Zobacz także

- [Model kryptografii](cryptography-model.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [Instrukcje: Podpisywanie dokumentów XML za pomocą podpisów cyfrowych](how-to-sign-xml-documents-with-digital-signatures.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
