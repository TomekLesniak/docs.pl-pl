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
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a>Instrukcje: Odszyfrowywanie elementów XML przy użyciu kluczy asymetrycznych

Można użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw do szyfrowania i odszyfrowywania elementu w dokumencie XML.  Szyfrowanie XML jest standardowym sposobem wymiany i przechowywania zaszyfrowanych danych XML bez obaw o dane, które są łatwo odczytywane.  Aby uzyskać więcej informacji na temat standardu szyfrowania XML, zobacz [składnię i przetwarzanie podpisu XML](https://www.w3.org/TR/xmldsig-core/)zalecenia organizacja World Wide Web Consortium (W3C).  

> [!NOTE]
> Kod w tym artykule ma zastosowanie do systemu Windows.

Przykład w tej procedurze odszyfrowuje element XML, który został zaszyfrowany przy użyciu metod opisanych w artykule [jak: szyfrowanie elementów XML przy użyciu kluczy asymetrycznych](how-to-encrypt-xml-elements-with-asymmetric-keys.md).  Znajduje `EncryptedData` element> <, odszyfrowuje element, a następnie zamienia element na oryginalny element XML w formacie zwykłego tekstu.  
  
Ten przykład odszyfrowuje element XML przy użyciu dwóch kluczy.  Pobiera on wcześniej wygenerowany klucz prywatny RSA z kontenera kluczy, a następnie używa klucza RSA do odszyfrowania klucza sesji przechowywanego w <`EncryptedKey`> elementu <`EncryptedData`>.  W przykładzie zostanie użyty klucz sesji do odszyfrowania elementu XML.  
  
Ten przykład jest odpowiedni dla sytuacji, w których wiele aplikacji musi udostępniać zaszyfrowane dane lub w przypadku, gdy aplikacja ma zapisywać zaszyfrowane dane między uruchomionymi danymi.  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a>Aby odszyfrować element XML za pomocą klucza asymetrycznego  
  
1. Utwórz <xref:System.Security.Cryptography.CspParameters> obiekt i określ nazwę kontenera kluczy.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. Pobierz wcześniej wygenerowany klucz asymetryczny z kontenera przy użyciu <xref:System.Security.Cryptography.RSACryptoServiceProvider> obiektu.  Klucz jest automatycznie pobierany z kontenera kluczy podczas przekazywania <xref:System.Security.Cryptography.CspParameters> obiektu do <xref:System.Security.Cryptography.RSACryptoServiceProvider> konstruktora.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. Utwórz nowy <xref:System.Security.Cryptography.Xml.EncryptedXml> obiekt do odszyfrowania dokumentu.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. Dodaj mapowanie klucza/nazwy, aby skojarzyć klucz RSA z elementem w dokumencie, który ma zostać odszyfrowany.  Należy użyć tej samej nazwy klucza, który został użyty podczas szyfrowania dokumentu.  Należy zauważyć, że ta nazwa jest oddzielona od nazwy używanej do identyfikowania klucza w kontenerze kluczy określonym w kroku 1.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. Wywołaj <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> metodę w celu odszyfrowania `EncryptedData` elementu> <.  Ta metoda powoduje odszyfrowanie klucza sesji przy użyciu klucza RSA i automatyczne odszyfrowanie elementu XML przy użyciu klucza sesji.  Automatycznie zastępuje <`EncryptedData`> elementu pierwotnym tekstem.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. Zapisz dokument XML.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a>Przykład

W tym przykładzie przyjęto założenie, że plik o nazwie `test.xml` istnieje w tym samym katalogu co skompilowany program.  Przyjęto również założenie, że `test.xml` zawiera element XML, który został zaszyfrowany przy użyciu technik opisanych w [instrukcje: szyfrowanie elementów XML przy użyciu kluczy asymetrycznych](how-to-encrypt-xml-elements-with-asymmetric-keys.md).  
  
[!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
- W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .

- W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).
  
- Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .  
  
## <a name="net-security"></a>Zabezpieczenia platformy .NET  

Nigdy nie przechowuj symetrycznego klucza kryptograficznego w postaci zwykłego tekstu lub przesyłaj klucz symetryczny między maszynami w postaci zwykłego tekstu.  Ponadto nigdy nie należy przechowywać ani przenosić klucza prywatnego pary kluczy asymetrycznych w postaci zwykłego tekstu.  Aby uzyskać więcej informacji na temat symetrycznych i asymetrycznych kluczy kryptograficznych, zobacz [generowanie kluczy do szyfrowania i odszyfrowywania](generating-keys-for-encryption-and-decryption.md).  
  
 Nigdy nie osadzaj klucza bezpośrednio w kodzie źródłowym.  Klucze osadzone można łatwo odczytywać z zestawu przy użyciu [Ildasm.exe (Il dezasembler)](../../framework/tools/ildasm-exe-il-disassembler.md) lub otwierając zestaw w edytorze tekstu, takim jak Notatnik.  
  
 Gdy skończysz korzystać z klucza kryptograficznego, usuń go z pamięci przez ustawienie każdego bajtu na zero lub przez wywołanie <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> metody zarządzanej klasy kryptografii.  Klucze kryptograficzne mogą być czasami odczytywane z pamięci przez debuger lub odczytywane z dysku twardego, jeśli lokalizacja pamięci jest stronicowana na dysku.  
  
## <a name="see-also"></a>Zobacz także

- [Model kryptografii](cryptography-model.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [Instrukcje: Szyfrowanie elementów XML przy użyciu kluczy asymetrycznych](how-to-encrypt-xml-elements-with-asymmetric-keys.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
