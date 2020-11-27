---
title: Obsługa identyfikatorów zasobów międzynarodowych w System.Uri
ms.date: 03/30/2017
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
ms.openlocfilehash: a3670c40a7a78e2ac8b521a4cb95477381848f36
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253365"
---
# <a name="international-resource-identifier-support-in-systemuri"></a>Obsługa identyfikatorów zasobów międzynarodowych w System.Uri

<xref:System.Uri?displayProperty=nameWithType>Klasa została rozszerzona o obsługę międzynarodowych identyfikatorów zasobów (IRI) i międzynarodowych nazw domen (IDN). Te ulepszenia są dostępne w .NET Framework 3,5, 3,0 SP1 i 2,0 SP1.  
  
## <a name="iri-and-idn-support"></a>Obsługa IRI i IDN  

 Adresy sieci Web są zwykle wyrażone przy użyciu jednolitych identyfikatorów zasobów (URI), które składają się z bardzo ograniczonego zestawu znaków:  
  
- Wielkie i małe litery ASCII z alfabetu angielskiego.  
  
- Cyfry od 0 do 9.  
  
- Niewielka liczba innych symboli ASCII.  
  
 Specyfikacje identyfikatorów URI są udokumentowane w RFC 2396 i RFC 3986 opublikowane przez Internet Engineering Task Force (IETF).  
  
 W przypadku wzrostu Internetu istnieje coraz większa potrzeba zidentyfikowania zasobów w językach innych niż angielski. Identyfikatory, które ułatwiają tę potrzebę i dopuszczają znaki inne niż ASCII (znaki w zestawie znaków Unicode/ISO 10646) są znane jako międzynarodowe identyfikatory zasobów (IRIs). Specyfikacje dla tęczówki są udokumentowane w dokumencie RFC 3987 opublikowanym przez IETF. Użycie tęczówki pozwala na używanie znaków Unicode w adresie URL.  
  
 Istniejąca <xref:System.Uri?displayProperty=nameWithType> Klasa została rozszerzona w celu zapewnienia pomocy technicznej IRI na podstawie RFC 3987. Bieżący użytkownicy nie będą widzieć żadnych zmian w zachowaniu .NET Framework 2,0, o ile nie włączą one IRI. Zapewnia to zgodność aplikacji z wcześniejszymi wersjami .NET Framework.  
  
 Aplikacja może określić, czy należy zastosować analizę międzynarodowej nazwy domeny (IDN), która została zastosowana do nazw domen i czy mają być stosowane reguły analizy IRI. Można to zrobić w machine.config lub w pliku app.config.  
  
 Włączenie IDN spowoduje przekonwertowanie wszystkich etykiet Unicode w nazwie domeny na ich odpowiedniki formacie Punycode. Nazwy formacie Punycode zawierają tylko znaki ASCII i zawsze zaczynają się od Xn--prefix. Przyczyną tego problemu jest obsługa istniejących serwerów DNS w Internecie, ponieważ większość serwerów DNS obsługuje tylko znaki ASCII (patrz dokument RFC 3940).  
  
 Włączenie IRI i IDN wpływa na wartość <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType> właściwości. Włączenie IRI i IDN może również zmienić zachowanie <xref:System.Uri.Equals%2A?displayProperty=nameWithType> <xref:System.Uri.OriginalString%2A?displayProperty=nameWithType> metod,, <xref:System.Uri.GetComponents%2A?displayProperty=nameWithType> i <xref:System.Uri.IsWellFormedOriginalString%2A> .  
  
 <xref:System.GenericUriParser?displayProperty=nameWithType>Klasa została również rozszerzona o możliwość tworzenia dostosowywalnego analizatora, który obsługuje IRI i IDN. Zachowanie <xref:System.GenericUriParser?displayProperty=nameWithType> obiektu jest określone przez przekazanie bitowej kombinacji wartości dostępnych w <xref:System.GenericUriParserOptions?displayProperty=nameWithType> wyliczeniu do <xref:System.GenericUriParser?displayProperty=nameWithType> konstruktora. <xref:System.GenericUriParserOptions.IriParsing?displayProperty=nameWithType>Typ wskazuje, że analizator obsługuje reguły analizy określone w RFC 3987 dla międzynarodowych identyfikatorów zasobów (IRI). Czy IRI jest rzeczywiście używany, zależy od tego, czy IRI jest włączona.  
  
 <xref:System.GenericUriParserOptions.Idn?displayProperty=nameWithType>Typ wskazuje, że analizator obsługuje międzynarodowy (IDN) analizowanie nazw hostów. Czy IDN jest rzeczywiście używany, zależy od tego, czy IDN jest włączona.  
  
 Włączenie analizy IRI spowoduje normalizację i sprawdzanie znaków zgodnie z najnowszymi regułami IRI w dokumencie RFC 3987. Wartość domyślna to IRI analiza, która ma zostać wyłączona, aby znormalizować i sprawdzanie znaków zostało wykonane zgodnie ze standardem RFC 2396 i RFC 3986.  
  
 Przetwarzanie IRI i IDN w <xref:System.Uri?displayProperty=nameWithType> klasie można również kontrolować przy użyciu <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> <xref:System.Configuration.IdnElement?displayProperty=nameWithType> klas ustawień konfiguracji i. <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>Ustawienie włącza lub wyłącza Przetwarzanie IRI w <xref:System.Uri?displayProperty=nameWithType> klasie. <xref:System.Configuration.IdnElement?displayProperty=nameWithType>Ustawienie włącza lub wyłącza przetwarzanie IDN w <xref:System.Uri> klasie. <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>Ustawienie powoduje także pośrednio kontrolę IDN. Aby przetwarzanie IDN było możliwe, należy włączyć przetwarzanie IRI. Jeśli przetwarzanie IRI jest wyłączone, przetwarzanie IDN zostanie ustawione na ustawienie domyślne, w którym zachowanie .NET Framework 2,0 jest używane w przypadku zgodności i nazwy IDN nie są używane.  
  
 Ustawienia konfiguracji <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> klas i są <xref:System.Configuration.IdnElement?displayProperty=nameWithType> odczytywane raz podczas <xref:System.Uri?displayProperty=nameWithType> konstruowania pierwszej klasy. Zmiany ustawień konfiguracji po upływie tego czasu zostaną zignorowane.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>
