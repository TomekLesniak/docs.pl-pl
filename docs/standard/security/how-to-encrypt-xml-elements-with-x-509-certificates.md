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
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a>Instrukcje: Szyfrowanie elementów XML za pomocą certyfikatów X.509

Można użyć klas w <xref:System.Security.Cryptography.Xml> przestrzeni nazw do szyfrowania elementu w dokumencie XML.  Szyfrowanie XML jest standardowym sposobem wymiany i przechowywania zaszyfrowanych danych XML bez obaw o dane, które są łatwo odczytywane.  Aby uzyskać więcej informacji na temat standardu szyfrowania XML, zapoznaj się z artykułem Specyfikacja organizacja World Wide Web Consortium (W3C) dla szyfrowania XML znajdującego się w temacie <https://www.w3.org/TR/xmldsig-core/> .  
  
 Możesz użyć szyfrowania XML, aby zamienić dowolny element XML lub dokument z <`EncryptedData`> element, który zawiera zaszyfrowane dane XML. `EncryptedData`Element> <może zawierać elementy podrzędne, które zawierają informacje o kluczach i procesach używanych podczas szyfrowania.  Szyfrowanie XML pozwala dokument może zawierać wiele zaszyfrowanych elementów i umożliwia wielokrotne szyfrowanie elementu.  Przykład kodu w tej procedurze pokazuje, jak utworzyć <`EncryptedData` element> wraz z kilkoma innymi elementami podrzędnymi, które można później użyć podczas odszyfrowywania.  
  
Ten przykład szyfruje element XML przy użyciu dwóch kluczy. Przykład programowo pobiera certyfikat i używa go do szyfrowania elementu XML przy użyciu <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> metody. Wewnętrznie <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> Metoda tworzy osobny klucz sesji i używa jej do szyfrowania dokumentu XML. Ta metoda szyfruje klucz sesji i zapisuje go wraz z zaszyfrowanym kodem XML w ramach nowego `EncryptedData` elementu <>.  

Aby odszyfrować element XML, wywołaj <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> metodę, która automatycznie pobiera certyfikat X. 509 ze sklepu i wykonuje wymagane odszyfrowywanie.  Aby uzyskać więcej informacji na temat odszyfrowywania elementu XML, który został zaszyfrowany przy użyciu tej procedury, zobacz [How to: Deszyfruj elementy XML za pomocą certyfikatów X. 509](how-to-decrypt-xml-elements-with-x-509-certificates.md).  
  
Ten przykład jest odpowiedni dla sytuacji, w których wiele aplikacji musi udostępniać zaszyfrowane dane lub w przypadku, gdy aplikacja wymaga zapisywania zaszyfrowanych danych między uruchomionymi danymi.  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a>Aby zaszyfrować element XML z certyfikatem X.509  

Aby uruchomić ten przykład, należy utworzyć certyfikat testowy i zapisać go w magazynie certyfikatów. Instrukcje dotyczące tego zadania są dostępne tylko dla narzędzia do [tworzenia certyfikatów systemu Windows (Makecert.exe)](/windows/desktop/SecCrypto/makecert).

1. Użyj [Makecert.exe](/windows/desktop/SecCrypto/makecert) do wygenerowania certyfikatu test X. 509 i umieść go w lokalnym magazynie użytkowników. Musisz wygenerować klucz wymiany i należy dokonać eksportu klucza. Uruchom następujące polecenie:  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2020 -e 01/01/2025 -sky exchange -ss my  
    ```  
  
2. Utwórz <xref:System.Security.Cryptography.X509Certificates.X509Store> obiekt i zainicjuj go, aby otworzyć bieżący magazyn użytkowników.  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. Otwórz sklep w trybie tylko do odczytu.  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. Zainicjuj <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> wszystkie certyfikaty w sklepie.  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. Wylicz certyfikaty w magazynie i Znajdź certyfikat z odpowiednią nazwą.  W tym przykładzie certyfikat ma nazwę `"CN=XML_ENC_TEST_CERT"` .  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. Zamknij sklep po zlokalizowaniu certyfikatu.  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. Utwórz <xref:System.Xml.XmlDocument> obiekt przez załadowanie pliku XML z dysku.  <xref:System.Xml.XmlDocument>Obiekt zawiera element XML do zaszyfrowania.  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. Znajdź określony element w <xref:System.Xml.XmlDocument> obiekcie i Utwórz nowy <xref:System.Xml.XmlElement> obiekt do reprezentowania elementu, który chcesz zaszyfrować.  W tym przykładzie `"creditcard"` element jest szyfrowany.  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. Utwórz nowe wystąpienie <xref:System.Security.Cryptography.Xml.EncryptedXml> klasy i użyj go do szyfrowania określonego elementu przy użyciu certyfikatu X. 509.  <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>Metoda zwraca zaszyfrowany element jako <xref:System.Security.Cryptography.Xml.EncryptedData> obiekt.  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. Zamień element z oryginalnego obiektu na <xref:System.Xml.XmlDocument> <xref:System.Security.Cryptography.Xml.EncryptedData> element.  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. Zapisz <xref:System.Xml.XmlDocument> obiekt.  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a>Przykład  
 W tym przykładzie przyjęto założenie, że plik o nazwie `"test.xml"` istnieje w tym samym katalogu co skompilowany program.  Zakłada również, że `"test.xml"` zawiera `"creditcard"` element.  Można umieścić następujący kod XML w pliku o nazwie `test.xml` i użyć go w tym przykładzie.  
  
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
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
- W projekcie, który jest przeznaczony dla .NET Framework, należy dołączyć odwołanie do `System.Security.dll` .

- W projekcie przeznaczonym dla platformy .NET Core lub .NET 5 Zainstaluj pakiet NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).
  
- Uwzględnij następujące przestrzenie nazw: <xref:System.Xml> , <xref:System.Security.Cryptography> , i <xref:System.Security.Cryptography.Xml> .  
  
## <a name="net-security"></a>Zabezpieczenia platformy .NET
  
Certyfikat X. 509 użyty w tym przykładzie służy tylko do celów testowych.  Aplikacje powinny używać certyfikatu X. 509 wygenerowanego przez zaufany urząd certyfikacji.  
  
## <a name="see-also"></a>Zobacz też

- [Model kryptografii](cryptography-model.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [Instrukcje: Odszyfrowywanie elementów XML za pomocą certyfikatów X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
