---
title: Protokoły obsługi komunikatów
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: 69a92bfb406e2e1af3bdcbb0316711dbf531204b
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812058"
---
# <a name="messaging-protocols"></a>Protokoły obsługi komunikatów

Stos kanału Windows Communication Foundation (WCF) korzysta z kodowania i kanałów transportowych, aby przekształcić wewnętrzną reprezentację komunikatu na format przewodu i wysłać ją przy użyciu określonego transportu. Najbardziej typowym transportem używanym do współdziałania usług sieci Web jest protokół HTTP, a najpopularniejsze kodowania używane przez usługi sieci Web są oparte na języku XML protokołu SOAP 1,1, SOAP 1,2 i mechanizmu optymalizacji transmisji wiadomości (MTOM).

W tym temacie omówiono szczegóły implementacji WCF dla następujących protokołów używanych przez program <xref:System.ServiceModel.Channels.HttpTransportBindingElement> .

Specyfikacja/dokument:

- [HTTP 1,1](https://www.ietf.org/rfc/rfc2616.txt)
- [Powiązanie http protokołu SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), sekcja 7
- [Powiązanie http protokołu SOAP 1,2](https://www.w3.org/TR/soap12-part2) Sekcja 7

W tym temacie omówiono szczegóły implementacji programu WCF dotyczące następujących protokołów, które <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> i <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> wykorzystują.

Specyfikacja/dokument:

- [XML](https://www.w3.org/TR/REC-xml)
- [PROTOKÓŁ SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [Rdzeń SOAP 1,2](https://www.w3.org/TR/soap12-part1/)
- [WS-Addressing 2004/08](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [Usługi sieci Web w formacie W3C o 1,0-Core](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [Usługi sieci Web w formacie W3C adresowanie 1,0 — powiązanie SOAP](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [Usługi sieci Web w formacie W3C adresowanie 1,0 — Powiązanie WSDL](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [Usługi sieci Web w formacie W3C Addressing 1,0 — metadane](https://www.w3.org/TR/ws-addr-metadata/)
- [Powiązanie SOAP 1.1 języka WSDL](https://www.w3.org/TR/wsdl/)
- [Powiązanie WSDL SOAP 1.2](https://www.w3.org/Submission/wsdl11soap12/)

W tym temacie omówiono szczegóły implementacji programu WCF dotyczące następujących protokołów, które są używane <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> .

Specyfikacja/dokument:

- [XOP](https://www.w3.org/TR/xop10/)
- [Powiązanie MTOM + SOAP 1,2](https://www.w3.org/TR/soap12-mtom/)
- [Powiązanie SOAP 1,1](https://www.w3.org/Submission/soap11mtom10/)
- [Usługa MTOM — potwierdzenie zasad](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

W tym temacie są używane następujące przestrzenie nazw XML i skojarzone prefiksy:

| Prefiks | Uniform Resource Identifier przestrzeni nazw (URI) |
|------------|---------------------------------------------------|
| s11 | `http://schemas.xmlsoap.org/soap/envelope` |
| S12 |`http://www.w3.org/2003/05/soap-envelope` |
| WSA |`http://www.w3.org/2004/08/addressing` |
| wsam |`http://www.w3.org/2007/05/addressing/metadata` |
| wsap |`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing` |
| wsa10 |`http://www.w3.org/2005/08/addressing` |
| wsaw10 |`http://www.w3.org/2006/05/addressing/wsdl` |
| XOP |`http://www.w3.org/2004/08/xop/include` |
| xmime |`http://www.w3.org/2004/06/xmlmime`<br /><br /> `http://www.w3.org/2005/05/xmlmime` |
| różnic |`http://schemas.microsoft.com/net/2006/06/duplex` |

## <a name="soap-11-and-soap-12"></a>SOAP 1,1 i SOAP 1,2

### <a name="envelope-and-processing-model"></a>Model kopert i przetwarzania
Funkcja WCF implementuje przetwarzanie kopert protokołu SOAP 1,1 przy zastosowaniu profilu podstawowego 1,1 (BP11) i profilu podstawowego 1,0 (SSBP10). Przetwarzanie kopert protokołu SOAP 1,2 jest zaimplementowane po SOAP12-part1.

W tej sekcji opisano niektóre opcje implementacji podjęte przez program WCF w odniesieniu do BP11 i SOAP12-part1.

#### <a name="mandatory-header-processing"></a>Obowiązkowe przetwarzanie nagłówka
Funkcja WCF stosuje reguły dotyczące przetwarzania nagłówków oznaczonych `mustUnderstand` w specyfikacjach soap 1,1 i soap 1,2 z następującymi odmianami.

Komunikat wprowadzający stos kanału WCF jest przetwarzany przez poszczególne kanały skonfigurowane przez skojarzone elementy powiązania, na przykład kodowanie wiadomości tekstowych, zabezpieczenia, niezawodne komunikaty i transakcje. Każdy kanał rozpoznaje nagłówki ze skojarzonej przestrzeni nazw i oznacza je jako zrozumiałe. Gdy komunikat przechodzi do dyspozytora, program formatujący operacji odczytuje nagłówki oczekiwane przez odpowiedni kontrakt komunikatów/operacji i oznacza je zrozumiałe. Następnie Dyspozytor weryfikuje, czy wszystkie pozostałe nagłówki nie są zrozumiałe, ale oznaczone jako `mustUnderstand` i zgłasza wyjątek. Komunikaty zawierające `mustUnderstand` nagłówki, które są przeznaczone dla odbiorców, nie są przetwarzane przez kod aplikacji odbiorcy.

Takie przetwarzanie warstwowe umożliwia rozdzielenie między warstwami infrastruktury i warstwami aplikacji węzła SOAP:

- B1111: niezrozumiałe nagłówki są wykrywane po przetworzeniu komunikatu przez stos kanału infrastruktury WCF, ale przed przetworzeniem przez aplikację

     `mustUnderstand`Wartość nagłówka różni się od protokołu soap 1,1 i protokołu soap 1,2. Profil podstawowy 1,1 wymaga, aby `mustUnderstand` wartość była równa 0 lub 1 dla komunikatów protokołu SOAP 1,1. Protokół SOAP 1,2 dopuszcza wartość 0, 1, `false` i `true` jako wartości, ale zaleca emitowanie kanonicznej reprezentacji `xs:boolean` wartości ( `false` , `true` ).

- B1112: Funkcja WCF emituje `mustUnderstand` wartości 0 i 1 dla wersji soap 1,1 i soap 1,2 dla koperty protokołu SOAP. Funkcja WCF akceptuje całą przestrzeń wartości `xs:boolean` dla `mustUnderstand` nagłówka (0, 1, `false` , `true` ).

#### <a name="soap-faults"></a>Błędy SOAP
Poniżej znajduje się lista implementacji błędów SOAP specyficznych dla WCF.

- B2121: Funkcja WCF zwraca następujące kody błędów SOAP 1,1: `s11:mustUnderstand` , `s11:Client` , i `s11:Server` .

- B2122: Funkcja WCF zwraca następujące kody błędów SOAP 1,2: `s12:MustUnderstand` , `s12:Sender` , i `s12:Receiver` .

### <a name="http-binding"></a>Powiązanie HTTP

#### <a name="soap-11-http-binding"></a>Powiązanie HTTP protokołu SOAP 1,1
Program WCF implementuje powiązanie HTTP 1.1 protokołu SOAP, postępując zgodnie z sekcją specyfikacji profilu podstawowego 1,1 3,4 z następującymi wyjaśnieniami:

- B2211: usługa WCF nie implementuje przekierowywania żądań POST protokołu HTTP.

- B2212: klienci WCF obsługują pliki cookie protokołu HTTP zgodnie z 3.4.8.

#### <a name="soap-12-http-binding"></a>Powiązanie HTTP protokołu SOAP 1,2
Funkcja WCF implementuje powiązania HTTP protokołu SOAP 1,2 zgodnie z opisem w specyfikacji SOAP 1,2-część 2 (SOAP12Part2) z następującymi wyjaśnieniami.

W protokole SOAP 1,2 wprowadzono opcjonalny parametr akcji dla `application/soap+xml` typu nośnika. Ten parametr jest przydatny do optymalizowania wysyłania komunikatów bez konieczności analizowania treści komunikatu protokołu SOAP, gdy nie jest używane adresowanie WS-Addressing.

- R2221: `application/soap+xml` parametr Action, gdy jest obecny w ŻĄDANIU SOAP 1,2, musi być zgodny z `soapAction` atrybutem `wsoap12:operation` elementu wewnątrz odpowiedniego powiązania WSDL.

- R2222: `application/soap+xml` parametr Action, gdy jest obecny w komunikacie protokołu SOAP 1,2, musi być zgodny, `wsa:Action` gdy używane są WS-addressing 2004/08 lub WS-addressing 1,0.

Gdy Usługa WS-Addressing jest wyłączona, a żądanie przychodzące nie zawiera parametru akcji, komunikat `Action` jest traktowany jako nieokreślony.

## <a name="ws-addressing"></a>Adresowanie WS-Addressing
Funkcja WCF implementuje 3 wersje WS-Addressing:

- WS-Addressing 2004/08

- W3C Web Services Addressing 1,0 Core (ADDR10-CORE) i powiązania SOAP (ADDR10-SOAP)

- WS-Addressing 1,0 — metadane

### <a name="endpoint-references"></a>Odwołania do punktu końcowego
Wszystkie wersje WS-Addressing, które obsługują program WCF, implementują odwołania do punktów końcowych, aby opisywać punkty końcowe.

#### <a name="endpoint-references-and-ws-addressing-versions"></a>Odwołania punktów końcowych i wersje WS-Addressing
Funkcja WCF implementuje szereg protokołów infrastruktury, które używają adresów WS-Addressing, w szczególności `EndpointReference` elementów i `W3C.WsAddressing.EndpointReferenceType` klas (na przykład WS-RELIABLEMESSAGING, WS-SECURECONVERSATION i WS-Trust). Usługa WCF obsługuje korzystanie z dowolnej wersji WS-Addressing z innymi protokołami infrastruktury. Punkty końcowe WCF obsługują jedną wersję WS-Addressing na punkt końcowy.

Dla R3111 przestrzeń nazw dla `EndpointReference` elementu lub typu używana w komunikatach wymienianych z punktem końcowym WCF musi być zgodna z wersją WS-Addressing implementowaną przez ten punkt końcowy.

Na przykład, jeśli punkt końcowy programu WCF implementuje protokół WS-ReliableMessaging, `AcksTo` nagłówek zwrócony przez ten punkt końcowy `CreateSequenceResponse` używa wersji WS-Addressing, która jest `EncodingBinding` określana przez element dla tego punktu końcowego.

#### <a name="endpoint-references-and-metadata"></a>Odwołania do punktów końcowych i metadane
Niektóre scenariusze wymagają komunikacji metadanych lub odwołania do metadanych dla danego punktu końcowego.

B3121: Funkcja WCF korzysta z mechanizmów opisanych w sekcji specyfikacji WS-MetadataExchange (MEX) 6, aby uwzględnić metadane dla odwołań do punktów końcowych przez wartość lub przez odwołanie.

Rozważmy scenariusz, w którym usługa WCF wymaga uwierzytelniania przy użyciu tokenu "Security Assertions Markup Language (SAML)" wystawionego przez wystawcę tokenów w `http://sts.fabrikam123.com` . Punkt końcowy WCF opisuje to wymaganie uwierzytelniania przy użyciu `sp:IssuedToken` potwierdzenia z zagnieżdżonym `sp:Issuer` potwierdzeniem wskazującym wystawcę tokenu. Aplikacje klienckie, które uzyskują dostęp do `sp:Issuer` potwierdzenia, muszą wiedzieć, jak komunikować się z punktem końcowym wystawcy tokenu. Klient musi znać metadane dotyczące wystawcy tokenu. Przy użyciu rozszerzeń metadanych odwołań punktów końcowych zdefiniowanych w MEX, WCF zawiera odwołanie do metadanych wystawcy tokenu.

```xml
<sp:IssuedToken>
  <sp:Issuer>
    <wsa10:Address>
      http://sts.fabrikam123.com
    </wsa10:Address>
    <wsa10:Metadata>
      <mex:Metadata>
        <mex:MetadataSection>
          <mex:MetadataReference>
            <wsa10:Address>
              http://sts.fabrikam123.com/mex
            </wsa10:Address>
          </mex:MetadataReference>
        </mex:MetadataSection>
      </mex:Metadata>
    </wsa10:Metadata>
  </sp:Issuer>
</sp:IssuedToken>
```

### <a name="message-addressing-headers"></a>Nagłówki adresów komunikatów

#### <a name="message-headers"></a>Nagłówki komunikatów
W przypadku wersji WS-Addressing WCF używa następujących nagłówków komunikatów zgodnie ze specyfikacją,, `wsa:To` , `wsa:ReplyTo` `wsa:Action` `wsa:MessageID` i `wsa:RelatesTo` .

B3211: dla wszystkich wersji WS-Addressing program WCF honoruje, ale nie wygenerował z Box nagłówków komunikatów WS-Addressing `wsa:FaultTo` i `wsa:From` .

Aplikacje, które współpracują z aplikacjami WCF, mogą dodawać te nagłówki komunikatów, a program WCF odpowiednio przetwarza je.

#### <a name="reference-parameters-and-properties"></a>Parametry odwołania i właściwości

WCF implementuje przetwarzanie parametrów odwołań punktów końcowych i właściwości odwołania zgodnie z odpowiednimi specyfikacjami.

B3221: gdy jest skonfigurowany do korzystania z WS-Addressing 2004/08, punkty końcowe WCF nie rozróżnią między przetwarzaniem właściwości odwołania i parametrów referencyjnych.

### <a name="message-exchange-patterns"></a>Wzorce wymiany komunikatów
Sekwencja komunikatów występujących w wywołaniu operacji usługi sieci Web jest nazywana *wzorcem wymiany komunikatów*. Usługa WCF obsługuje jednokierunkowe wzorce wymiany komunikatów z żądaniami i odpowiedziami. W tej sekcji objaśniono wymagania WS-Addressing dotyczące przetwarzania komunikatów w zależności od używanego wzorca wymiany komunikatów.

W tej sekcji Obiekt żądający wysyła pierwszy komunikat, a obiekt odpowiadający otrzymuje pierwszy komunikat.

#### <a name="one-way-message"></a>Komunikat jednokierunkowy
Gdy punkt końcowy programu WCF jest skonfigurowany do obsługi komunikatów, `Action` które mają być zgodne ze wzorcem jednokierunkowym, punkt końcowy programu WCF postępuje zgodnie z poniższymi zachowaniami i wymaganiami. O ile nie określono inaczej, zachowania i reguły mają zastosowanie w przypadku obu wersji WS-Addressing obsługiwanych w programie WCF:

- R3311: Obiekt żądający musi zawierać `wsa:To` `wsa:Action` nagłówki, i i dla wszystkich parametrów referencyjnych określonych przez odwołanie do punktu końcowego. W przypadku użycia protokołu WS-Addressing 2004/08 i [właściwości odwołania] są określone przez odwołanie do punktu końcowego, odpowiednie nagłówki należy dodać do komunikatu.

- B3312: Obiekt żądający może zawierać `MessageID` , `ReplyTo` , i `FaultTo` nagłówki. Infrastruktura odbiornika zignoruje je i zostanie przeniesiona do aplikacji.

- R3313: gdy jest używany protokół HTTP i nie jest wysyłany żaden komunikat w postawce odpowiedzi HTTP, obiekt odpowiadający musi wysłać odpowiedź HTTP z pustą treścią i kodem stanu HTTP 202.

     Gdy transport HTTP jest używany, a kontrakt operacji deklaruje komunikat jednokierunkowy, odpowiedź HTTP może być nadal używana do wysyłania komunikatów dotyczących infrastruktury — na przykład, niezawodne komunikaty mogą wysyłać `SequenceAcknowledgement` komunikat w odpowiedzi HTTP.

- B3314: obiekt odpowiadający WCF nie wysyła komunikatu o błędzie w odpowiedzi na komunikat jednokierunkowy.

#### <a name="request-reply"></a>Żądanie i odpowiedź
Gdy punkt końcowy programu WCF jest skonfigurowany dla komunikatu z danym `Action` do przestrzegania wzorca żądanie-odpowiedź, punkt końcowy WCF postępuje zgodnie z zachowaniem i wymaganiami poniżej. O ile nie określono inaczej, zachowania i reguły dotyczą obu wersji WS-Addressing obsługiwanych w programie WCF:

- R3321: Obiekt żądający musi zawierać w żądaniu `wsa:To` , `wsa:Action` , `wsa:MessageID` i nagłówkach wszystkie parametry odwołania lub właściwości odwołania (lub obie) określone przez odwołanie do punktu końcowego.

- R3322: w przypadku korzystania z protokołu WS-Addressing 2004/08 `ReplyTo` należy również uwzględnić je w żądaniu.

- R3323: gdy Usługa WS-Addressing 1,0 jest używana i `ReplyTo` nie występuje w żądaniu, zostanie użyte domyślne odwołanie do punktu końcowego z właściwością [address] równą `http://www.w3.org/2005/08/addressing/anonymous` .

- R3324: Obiekt żądający musi zawierać `wsa:To` , `wsa:Action` , i `wsa:RelatesTo` nagłówki w komunikacie odpowiedzi, a także nagłówki dla wszystkich parametrów odwołania lub właściwości odwołania (lub obu) określonych przez odwołanie do `ReplyTo` punktu końcowego w żądaniu.

### <a name="web-services-addressing-faults"></a>Błędy adresowania usług sieci Web
R3411: Funkcja WCF tworzy następujące błędy zdefiniowane przez WS-Addressing 2004/08.

| Kod | Przyczyna |
|----------|-----------|
| `wsa:DestinationUnreachable` | Wiadomość dotarła do `ReplyTo` , która różni się od adresu zwrotnego dla tego kanału; brak punktu końcowego nasłuchiwania pod adresem określonym w nagłówku do. |
| `wsa:ActionNotSupported` | kanały infrastruktury lub Dyspozytor skojarzony z punktem końcowym nie rozpoznają akcji określonej w `Action` nagłówku. |

R3412: Funkcja WCF tworzy następujące błędy zdefiniowane przez WS-Addressing 1,0.

| Kod | Przyczyna |
|----------|-----------|
| `wsa10:InvalidAddressingHeader` | Duplikuj `wsa:To` , `wsa:ReplyTo` `wsa:From` lub `wsa:MessageID` . Duplikat `wsa:RelatesTo` z tą samą `RelationshipType` . |
| `wsa10:MessageAddressingHeaderRequired` | Brak wymaganego nagłówka Addressing. |
| `wsa10:DestinationUnreachable` | Wiadomość dotarła do `ReplyTo` , która różni się od adresu odpowiedzi dla tego kanału. Brak punktu końcowego nasłuchiwania pod adresem określonym w nagłówku do. |
| `wsa10:ActionNotSupported` | Akcja określona w `Action` nagłówku nie jest rozpoznawana przez kanały infrastruktury ani dyspozytora skojarzone z punktem końcowym. |
| `wsa10:EndpointUnavailable` | Kanał RM wysyła ten błąd ponownie, wskazując, że punkt końcowy nie przetworzy sekwencji na podstawie badania `CreateSequence` nagłówków adresowania wiadomości. |

Kod w powyższych tabelach jest mapowany na `FaultCode` w protokole soap 1,1 i `SubCode` (z kodem = nadawca) w protokole SOAP 1,2.

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a>Powiązania WSDL 1,1 i potwierdzenia WS-Policy

#### <a name="indicating-use-of-ws-addressing"></a>Wskazywanie użycia protokołu WS-Addressing
Funkcja WCF używa potwierdzeń zasad, aby wskazać obsługę punktu końcowego dla określonej wersji WS-Addressing.

Następujące potwierdzenie zasad ma podmiot zasad punktu końcowego [WS-PA] i wskazuje, że komunikaty wysyłane i odbierane z punktu końcowego muszą używać WS-Addressing 2004/08.

```xml
<wsap:UsingAddressing />
```

To potwierdzenie zasad rozszerza specyfikację WS-Addressing 2004/08.

Poniższe potwierdzenie zasad wskazuje, że komunikaty wysyłane/odbierane muszą używać WS-Addressing 1,0.

```xml
<wsam:Addressing/>
```

Następujące potwierdzenie zasad ma podmiot zasad punktu końcowego [WS-PA] i wskazuje, że komunikaty wysyłane i odbierane z punktu końcowego muszą używać WS-Addressing 2004/08.

```xml
<wsaw10:UsingAddressing />
```

`wsaw10:UsingAddressing`Element jest popożyczony z [WS-Addressing-WSDL] i jest używany w kontekście protokołu WS-Policy zgodności z tą specyfikacją w sekcji 3.1.2.

Korzystanie z adresowania nie zmienia semantyki powiązań WSDL 1,1, SOAP 1,1 i SOAP 1,2 protokołu HTTP. Na przykład jeśli oczekuje się, że odpowiedź jest wysyłana do punktu końcowego, który używa adresu i powiązania HTTP w języku WSDL 1. x, należy wysłać odpowiedź przy użyciu odpowiedzi HTTP.

W przypadku odpowiedzi wysyłanych za pośrednictwem odpowiedzi HTTP, potwierdzenie WS-AM:

```xml
<wsam:AnonymousResponses/>
```

Kompletne potwierdzenie zasad może wyglądać następująco:

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

Istnieją jednak wzorce wymiany komunikatów, które korzystają z dwóch niezależnych połączeń HTTP, które są nawiązywane między obiektem żądającym a obiektem odpowiadającym, na przykład niechciane komunikaty jednokierunkowe wysyłane przez obiekt odpowiadający.

Program WCF oferuje funkcję, za pomocą której dwa bazowe kanały transportu mogą tworzyć złożony kanał dupleksowy, w którym jeden kanał jest używany do przesyłania komunikatów wejściowych, a drugi jest używany do przesyłania komunikatów wyjściowych. W przypadku transportu HTTP złożony dupleks oferuje dwa odwrotne połączenia HTTP. Żądający używa jednego połączenia do wysyłania komunikatów do obiektu odpowiadającego, a obiekt odpowiadający używa innego do wysyłania komunikatów z powrotem do osoby żądającej.

W przypadku odpowiedzi wysyłanych za pomocą oddzielnych żądań HTTP potwierdzenie protokołu WS-am to

```xml
<wsam:NonAnonymousResponses/>
```

Kompletne potwierdzenie zasad może wyglądać następująco:

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

Korzystanie z następującego potwierdzenia, który ma podmiot zasad punktu końcowego [WS-PA] w punktach końcowych korzystających z języka WSDL 1,1 SOAP 1. x powiązania HTTP wymaga, aby w przypadku komunikatów pływających od żądającego do obiektu odpowiadającego i obiektu odpowiadającego odpowiednio zażądano dwóch oddzielnych połączeń HTTP.

```xml
<cdp:CompositeDuplex/>
```

Poprzednia instrukcja prowadzi do następujących wymagań w `wsa:ReplyTo` nagłówku komunikatów żądania:

- R3514: komunikaty żądania wysyłane do punktu końcowego muszą mieć `ReplyTo` Nagłówek z `[address]` właściwością, która nie jest równa, `http://www.w3.org/2005/08/addressing/anonymous` Jeśli punkt końcowy używa powiązania HTTP języka WSDL 1,1 SOAP 1. x i ma alternatywę dla zasad z `wsap10:UsingAddressing` `wsap:UsingAddressing` załączonym parametrem lub z potwierdzeniem `cdp:CompositeDuplex` .

- R3515: komunikaty żądania wysyłane do punktu końcowego muszą mieć `ReplyTo` Nagłówek z `[address]` właściwością równą `http://www.w3.org/2005/08/addressing/anonymous` lub nie mieć `ReplyTo` nagłówka, jeśli punkt końcowy używa powiązania HTTP języka WSDL 1,1 SOAP 1. x i ma alternatywę dla zasad z `wsap10:UsingAddressing` potwierdzeniem i nie ma `cdp:CompositeDuplex` dołączonego potwierdzenia.

- R3516: komunikaty żądania wysyłane do punktu końcowego muszą mieć `ReplyTo` nagłówek o `[address]` Właściwości równej, `http://www.w3.org/2005/08/addressing/anonymous` Jeśli punkt końcowy używa powiązania HTTP języka WSDL 1,1 SOAP 1. x i ma alternatywę dla zasad z `wsap:UsingAddressing` potwierdzeniem i nie ma `cdp:CompositeDuplex` dołączonego potwierdzenia.

Specyfikacja specyfikacji WSDL WS-Addressing próbuje opisać podobne powiązania protokołów przez wprowadzenie elementu `<wsaw:Anonymous/>` z trzema wartościami tekstowymi (wymagane, opcjonalne i zabronione), aby wskazać wymagania dotyczące `wsa:ReplyTo` nagłówka (sekcja 3,2). Niestety, taka definicja elementu nie jest szczególnie użyteczna jako potwierdzenie w kontekście usługi WS-Policy, ponieważ wymaga rozszerzeń specyficznych dla domeny do obsługi przecięcia się z alternatywami przy użyciu takiego elementu jako potwierdzenia. Definicja elementu wskazuje również wartość `ReplyTo` nagłówka, a nie zachowanie punktu końcowego w sieci, co sprawia, że jest to specyficzne dla transportu HTTP.

#### <a name="action-definition"></a>Definicja akcji
WS-Addressing 2004/08 definiuje `wsa:Action` atrybut dla `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elementów. Powiązanie WSDL WS-Addressing 1,0 (WS-ADDR10-WSDL) definiuje podobny atrybut, `wsaw10:Action` .

Jedyną różnicą między nimi jest domyślna semantyka wzorca akcji opisana w sekcji 3.3.2 protokołu WS-ADDR i sekcja 4.4.4 protokołu WS-ADDR10-WSDL.

Rozsądne jest posiadanie dwóch punktów końcowych, które współużytkują ten sam `portType` (lub kontrakt, w terminologii WCF), ale korzystają z różnych wersji WS-Addressing. Jeśli jednak dana akcja jest definiowana przez `portType` i nie powinna się zmieniać w punktach końcowych implementujących `portType` , nie można obsługiwać obu domyślnych wzorców akcji.

Aby rozwiązać ten controversy, WCF obsługuje jedną wersję `Action` atrybutu.

B3521: Funkcja WCF używa `wsaw10:Action` atrybutu dla `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elementów, zgodnie z definicją w specyfikacji WS-ADDR10-WSDL, w celu określenia `Action` identyfikatora URI dla odpowiednich komunikatów niezależnie od wersji WS-Addressing używanej przez punkt końcowy.

#### <a name="use-endpoint-reference-inside-wsdl-port"></a>Użyj odwołania do punktu końcowego w porcie WSDL
Usługa WS-ADDR10 — WSDL sekcja 4,1 rozszerza `wsdl:port` element w celu uwzględnienia `<wsa10:EndpointReference…/>` elementu podrzędnego opisującego punkt końcowy w warunkach WS-Addressing. Funkcja WCF rozszerza to narzędzie na WS-Addressing 2004/08, co umożliwia `<wsa:EndpointReference…/>` Wyświetlanie jako elementu podrzędnego `wsdl:port` .

- R3531: Jeśli punkt końcowy ma dołączoną zasadę alternatywną z `<wsaw10:UsingAddressing/>` potwierdzeniem zasad, odpowiadający `wsdl:port` element może zawierać element podrzędny `<wsa10:EndpointReference …/>` .

- R3532: Jeśli `wsdl:port` zawiera element podrzędny `<wsa10:EndpointReference …/>` , `wsa10:EndpointReference/wsa10:Address` wartość elementu podrzędnego musi być zgodna z wartością `@address` atrybutu elementu równorzędnego `wsdl:port` / `wsdl:location` .

- R3533: Jeśli punkt końcowy ma dołączoną zasadę alternatywną z `<wsap:UsingAddressing/>` potwierdzeniem zasad, odpowiadający `wsdl:port` element może zawierać element podrzędny `<wsa:EndpointReference …/>` .

- R3534: Jeśli `wsdl:port` zawiera element podrzędny `<wsa:EndpointReference …/>` , `wsa:EndpointReference/wsa:Address` wartość elementu podrzędnego musi być zgodna z wartością `@address` atrybutu elementu równorzędnego `wsdl:port` / `wsdl:location` .

### <a name="composition-with-ws-security"></a>Tworzenie kompozycji przy użyciu protokołu WS-Security
Zgodnie z sekcjami dotyczącymi zagadnień związanych z bezpieczeństwem w usłudze WS-ADDR i WS-ADDR10 zaleca się, aby wszystkie nagłówki komunikatów adresowych były podpisane razem z treścią komunikatu w celu powiązania ich ze sobą.

Gdy Usługa WS-Security jest używana do ochrony integralności komunikatów, nagłówki komunikatów WS-Addressing, a także nagłówki, które wynikają z parametrów odwołania lub właściwości (lub obu), muszą być podpisane razem z treścią wiadomości.

### <a name="examples"></a>Przykłady

#### <a name="one-way-message"></a>Komunikat jednokierunkowy
W tym scenariuszu nadawca wysyła wiadomość jednokierunkową do odbiorcy. Używane są protokół SOAP 1,2, HTTP 1,1 i W3C WS-Addressing 1,0.

Struktura komunikatu żądania: nagłówki wiadomości obejmują `wsa10:To` `wsa10:Action` elementy i. Treść wiadomości zawiera określony `<app:Ping>` element z przestrzeni nazw aplikacji.

Nagłówki HTTP: miejsce docelowe w WPISie dopasowuje identyfikator URI w `wsa10:To` elemencie.

Nagłówek Content-Type ma wartość `application/soap+xml` , zgodnie z wymaganiami protokołu SOAP 1,2. Parametry `charset` i `action` są dołączone. `action`Parametr nagłówka Content-Type jest zgodny z wartością `wsa10:Action` nagłówka komunikatu.

```http
POST http://fabrikam123.com/Service HTTP/1.1
Content-Type: application/soap+xml; charset=utf-8;  
              action="http://fabrikam123.com/Service/OneWay"
Host: 131.107.72.15
Content-Length: 1501
Expect: 100-continue
Proxy-Connection: Keep-Alive
<s12:Envelope>
  <s12:Header>
    <wsa10:To s12:mustUnderstand="1">
        http://fabrikam123.com/Service
    </wsa10:To>
    <wsa10:Action s12:mustUnderstand="1">
        http://fabrikam123.com/Service/OneWay
    </wsa10:Action>
  </s12:Header>
  <s12:Body>
    <Ping xmlns="http://fabrikam123.com/Service/">
      <Text>Hello World</Text>
    </Ping>
  </s12:Body>
</s12:Envelope>
```

Odbiornik reaguje na pustą odpowiedź HTTP i status 202. Przykład odpowiedzi HTTP:

```http
HTTP/1.1 202 Accepted
Date: Fri, 15 Jul 2005 08:56:07 GMT
Server: Microsoft-IIS/6.0
MicrosoftOfficeWebServer: 5.0_Pub
X-Powered-By: ASP.NET
X-AspNet-Version: 2.0.50215
Cache-Control: private
Content-Length: 0
```

## <a name="soap-message-transmission-optimization-mechanism"></a>Mechanizm optymalizacji transmisji komunikatów SOAP
W tej sekcji opisano szczegóły implementacji programu WCF dotyczące protokołu SOAP protokołu HTTP. Technologia MTOM to mechanizm kodowania komunikatów protokołu SOAP tej samej klasy, co tradycyjne kodowanie tekstu/XML lub kodowanie binarne WCF. MTOM obejmuje następujące elementy:

- Mechanizm kodowania i pakowania XML opisany przez [XOP], który optymalizuje elementy informacji XML zawierające dane binarne kodowane algorytmem Base64 do oddzielnych części binarnych.

- Hermetyzacja MIME pakietu XOP, która serializować sprawdzonych XML i każdej binarnej części pakietu XOP do oddzielnej części MIME.

- Kodowanie MIME XOP zastosowane do koperty SOAP 1. x.

- Powiązanie transportu HTTP.

Możliwe jest korzystanie z mechanizmu MTOM z transportem innym niż HTTP z funkcją WCF. Jednak w tym temacie będziemy skupić się na protokole HTTP.

Format MTOM wykorzystuje duży zestaw specyfikacji obejmujących sam MTOM, XOP i MIME. Modularność tego zestawu specyfikacji sprawia, że jest nieco trudno odtworzyć dokładne wymagania dotyczące formatu i semantyki przetwarzania. W tej sekcji opisano wymagania dotyczące formatu i przetwarzania dla powiązania HTTP MTOM.

### <a name="mtom-message-encoding"></a>Kodowanie komunikatów MTOM

#### <a name="generating-mtom-messages"></a>Generowanie komunikatów mechanizmu MTOM
Sekcja [XOP] 3,1 opisuje proces kodowania XML z elementami informacji o elementach, które zawierają wartości Base64 do zdefiniowanego w sposób abstrakcyjny pakietu XOP.

Poniższa sekwencja kroków opisuje proces kodowania dotyczący mechanizmu MTOM:

1. Upewnij się, że koperta protokołu SOAP do zakodowania nie zawiera elementu informacji o elemencie z `[namespace name]` `http://www.w3.org/2004/08/xop/include` i z `[local name]` `Include` .

2. Utwórz pusty pakiet MIME.

3. Zidentyfikuj w oryginalnym kodzie XML sprawdzonych elementy informacji, które mają być zoptymalizowane. W przypadku elementów, które mają być optymalizowane, znaki wchodzące w `[children]` skład elementu informacji o elemencie muszą mieć postać kanoniczną `xs:base64Binary` (patrz XSD-2, 3.2.16 base64Binary) i nie może zawierać żadnych znaków białych poprzedzających, wbudowanych w lub następujących niebiałych zawartości.

4. Utwórz kopertę protokołu SOAP XOP, która jest kopią oryginalnej koperty protokołu SOAP, ale z elementami podrzędnymi każdego elementu informacji o elemencie zidentyfikowanym w poprzednim kroku zamienionym przez `xop:Include` element informacji o elemencie utworzony w następujący sposób:

    1. Przekształć zamienione znaki na dane binarne, przetwarzając je jako dane zakodowane algorytmem Base64.

    2. Wygeneruj unikatową wartość nagłówka Content-ID spełniającą wymagania R3133 i R3134.

    3. Wygeneruj nagłówek MIME Content-Transfer-Encoding z wartością binarną.

    4. Jeśli element informacji o elemencie, który jest zoptymalizowany ([nadrzędny] nowo wstawionego elementu `xop:Include` informacji o elemencie) zawiera `xmime:contentType` element informacji o atrybucie, wygeneruj nagłówek MIME typu zawartości z wartością `xmime:contentType` atrybutu.

    5. Generowanie nowej binarnej części MIME z zawartością utworzoną przez dane binarne, zdekodowaną od zastąpionych znaków przetworzonych jako algorytm Base64, Content-ID z nagłówka 4B, Content-Transfer-Encoding z 4.

    6. Dodaj `href` atrybut do `xop:Include` elementu z wartością CID: URI pochodzącą z wartości nagłówka Content-ID wygenerowanej w kroku 4B. Usuń otaczające znaki " \<" and "> ", adres URL-Escape pozostałego ciągu i Dodaj prefiks `cid:` . Następujący minimalny zestaw znaków musi być zmieniony przez RFC1738 i RFC2396. Inne znaki można zmienić.

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. Utwórz główną część MIME z kopertą protokołu SOAP XOP z kroku 4.

6. Napisz nagłówki HTTP, w tym nagłówek Content-Type.

7. Napisz pakiet MIME.

#### <a name="processing-mtom-messages"></a>Przetwarzanie komunikatów MTOM
Przetwarzanie komunikatu MTOM to dokładne odwrócenie procesu opisanego w poprzedniej sekcji "Generowanie komunikatów mechanizmu MTOM":

1. Upewnij się, że główna część MIME ma typ Content-Type `application/xop+xml` .

2. Konstruowanie koperty protokołu SOAP przez przeanalizowanie głównej części MIME pakietu jako dokumentu XML. Kodowanie znaków jest określane przez `charset` parametr typu zawartości głównej części MIME.

3. Dla każdego elementu informacji o elemencie w konstruowanej kopercie SOAP, która ma jako jedyny element członkowski właściwości [Children] elementu `xop:Include` informacji o elemencie:

    1. Usuń `cid:` prefiks i Anuluj ucieczkę wszystkich sekwencji URI i ucieczki (RFC 2396) w wartości `@href` atrybutu `xop:Include` elementu. Ujmij ciąg wynikowy w " \<", "> ".

    2. Znajdź część MIME z wartością nagłówka Content-ID zgodną z ciągiem pochodzącym z kroku 3a.

    3. Zastąp `xop:Include` element informacji o elemencie, który pojawia się we `children` właściwości każdego elementu z elementami informacji o znakach, które reprezentują kanoniczne kodowanie Base64 (patrz XSD-2, 3.2.16 base64Binary) treści jednostki części MIME wymienionej w kroku 3B (efektywnie Zastąp `xop:Include` element informacji o elemencie danymi przetworzonymi z części pakietu).

#### <a name="http-content-type-header"></a>Nagłówek zawartości HTTP-Type
Poniżej znajduje się lista wyjaśnień programu WCF dla formatu nagłówka Content-Type w formacie SOAP 1. x zakodowanych na podstawie wymagań określonych w samej specyfikacji MTOM i pochodzących od MTOM i RFC 2387.

- R4131: nagłówek Content-Type typu HTTP musi mieć wartość wieloczęściowego/powiązanego (bez uwzględniania wielkości liter) i jego parametrów. W nazwach parametrów jest rozróżniana wielkość liter. Kolejność parametrów nie jest istotna.

- Pełna kopia zapasowa-Naura (BNF) nagłówka Content-Type dla komunikatów MIME jest wymieniona w dokumencie RFC 2045, sekcja 5,1.

- R4132: nagłówek Content-Type typu HTTP musi mieć parametr typu z wartością `application/xop+xml` ujętą w znaki podwójnego cudzysłowu.

Chociaż wymóg używania podwójnego cudzysłowu nie jest jawny w dokumencie RFC 2387, tekst przestrzega, że wszystkie parametry typu nośnika wieloczęściowego/powiązanego najprawdopodobniej zawierają zastrzeżone znaki, takie jak " \@ " lub "/", a w związku z tym potrzebują podwójnych cudzysłowów.

- R4133: nagłówek Content-Type w formacie HTTP powinien mieć parametr początkowy z wartością nagłówka Content-ID części MIME, która zawiera kopertę SOAP 1. x ujętą w znaki podwójnego cudzysłowu. Jeśli parametr Start zostanie pominięty, pierwsza część MIME musi zawierać kopertę SOAP 1. x.

- R4134: nagłówek Content-Type typu HTTP dla komunikatu zakodowanego za pomocą mechanizmu MTOM protokołu SOAP 1,1 musi zawierać parametr Start-info z wartością text/xml ujętą w znaki podwójnego cudzysłowu.

- R4135: nagłówek Content-Type typu HTTP dla komunikatu kodowanego przy użyciu mechanizmu MTOM protokołu SOAP 1,2 musi zawierać parametr Start-info z wartością `application/soap+xml` ujętą w znaki podwójnego cudzysłowu.

- R4136: nagłówek Content-Type dla protokołu SOAP 1. x kodowany algorytmem MTOM musi mieć parametr granicy z wartością (ujętą w znaki podwójnego cudzysłowu), która pasuje do granicy MIME BNF zdefiniowanej w dokumencie RFC 2046, sekcja 5.1.1

    ```
    boundary := 0*69<bchars> bcharsnospace
    bchars := bcharsnospace / " "
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     Przykłady:

     NIEPOPRAWNE

    ```http
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     NIEPOPRAWNE

    ```http
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     PRAWIDŁOWY

    ```http
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

#### <a name="infoset-mime-part"></a>Sprawdzonych — składnik MIME
Koperta protokołu SOAP 1. x jest hermetyzowana jako część główna pakietu XOP MIME i jest często nazywana `infoset` częścią.

- R4141: Koperta protokołu SOAP 1. x musi być hermetyzowana jako część główna pakietu XOP MIME, nazywana `infoset` częścią i przywoływaną przez typ zawartości http.

- R4142: część protokołu SOAP `Infoset` musi zawierać następujące nagłówki MIME: `Content-ID` , `Content-Transfer-Encoding` , i `Content-Type` .

Format nagłówka Content-ID jest definiowany przez RFC 2045 jako

```
"Content-ID" ":" msg-id
```

gdzie `msg-id` jest zdefiniowana w dokumencie rfc 2822 (zastępuje dokument rfc 822, do którego odwołuje się dokument rfc 2045) jako:

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

i efektywnie jest adresem e-mail ujętym w " \<" and  "> ". `[CFWS]`Prefiks i sufiks zostały dodane w dokumencie RFC 2822 do przenoszenia komentarzy i nie powinny być używane w celu zachowania współdziałania.

R4143: wartość nagłówka Content-ID dla części MIME sprawdzonych musi być zgodna `msg-id` z produkcją RFC 2822 z `[CFWS]` pominiętymi częściami prefiksu i sufiksów.

Wiele implementacji MIME spełnia wymagania dotyczące wartości ujętej w nawiasy " \<" and "> " jako adresu e-mail, a nie `absoluteURI` \<" , "> adresu e-mail. Ta wersja programu WCF używa wartości nagłówka MIME Content-ID formularza:

```
Content-ID: <http://tempuri.org/0>
```

R4144: procesor MTOM powinien akceptować wartości nagłówka Content-ID, które pasują do poniższego swobodnego `msg-id` .

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

MIME (RFC 2045) zawiera nagłówek Content-Transfer-Encoding do przekazywania kodowania zawartości części MIME. Domyślnie zdefiniowane dla kodowania Content-Transfer-Encoding to 7-bitowe, które nie jest odpowiednie dla większości komunikatów protokołu SOAP, więc nagłówek Content-Transfer-Encoding jest wymagany w celu uzyskania większej współdziałania:

- R4145: część sprawdzonych protokołu SOAP musi zawierać nagłówek Content-Transfer-Encoding.

- R4146: Jeśli kodowanie znaków koperty protokołu SOAP to UTF-8, wartość nagłówka Content-Transfer-Encoding musi być 8-bitowa.

- R4147: Jeśli kodowanie znaków koperty protokołu SOAP to UTF-16, wartość nagłówka Content-Transfer-Encoding musi być binarna.

- Zgodnie z sekcją [XOP] 5,

- R4148: część sprawdzonych protokołu SOAP 1.1 musi zawierać nagłówek Content-Type z typem nośnika Application/XOP + XML i Parameters Type = "text/xml" i charset

    ```http
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- R4149: część sprawdzonych protokołu SOAP 1,2 musi zawierać nagłówek Content-Type z typem nośnika `application/xop+xml` i parametrami Type = " `application/soap+xml` " i `charset` .

    ```http
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     Chociaż XOP definiuje `charset` parametr jako `application/xop+xml` opcjonalny, jest wymagany do współdziałania podobnej do wymagania 1,1 BP dla `charset` `text/xml` typu nośnika.

- R41410: `type` Parametry i `charset` muszą być obecne w nagłówku Content-Type składnika SOAP 1. x sprawdzonych.

#### <a name="wcf-endpoint-support-for-mtom"></a>Obsługa punktów końcowych WCF dla mechanizmu MTOM
Celem MTOM jest zakodowanie komunikatu protokołu SOAP w celu zoptymalizowania danych zakodowanych algorytmem Base64. Poniżej znajduje się lista ograniczeń:

- R4151: każdy element informacji o elemencie, który zawiera dane zakodowane w formacie Base64, może być zoptymalizowany.

- B4152: Funkcja WCF optymalizuje elementy informacji o elementach, które zawierają dane zakodowane w formacie base64 i przekracza 1024 bajtów.

Punkt końcowy programu WCF skonfigurowany do korzystania z mechanizmu MTOM zawsze będzie wysyłać komunikaty kodowane przez MTOM. Nawet jeśli żadna część nie spełnia wymaganych kryteriów, komunikat jest nadal zakodowany za pomocą mechanizmu MTOM (Serializacja jako pakiet MIME z pojedynczą częścią MIME zawierającą kopertę protokołu SOAP).

### <a name="ws-policy-assertion-for-mtom"></a>Potwierdzenie usługi WS-Policy dla mechanizmu MTOM
W celu wskazania użycia usługi MTOM przez punkt końcowy w programie WCF jest stosowane następujące potwierdzenie zasad:

```xml
<wsoma:OptimizedMimeSerialization />
```

- R4211: powyższe potwierdzenie zasad ma podmiot zasad punktu końcowego i określa, że wszystkie komunikaty wysyłane do i odbierane z punktu końcowego muszą być zoptymalizowane przy użyciu mechanizmu MTOM.

- B4212: Jeśli skonfigurowano używanie optymalizacji MTOM, punkt końcowy programu WCF dodaje potwierdzenie zasad MTOM do zasad dołączonych do odpowiednich `wsdl:binding` .

### <a name="composition-with-ws-security"></a>Tworzenie kompozycji przy użyciu protokołu WS-Security
MTOM jest mechanizmem kodowania podobnym do `text/xml` kodu XML danych binarnych WCF. MTOM oferuje naturalną kompozycję przy użyciu protokołu WS-Security i innych protokołów WS-*: komunikat zabezpieczony przy użyciu protokołu WS-Security można zoptymalizować za pomocą mechanizmu MTOM.

### <a name="examples"></a>Przykłady

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a>Komunikat protokołu SOAP 1,1 WCF zakodowany przy użyciu mechanizmu MTOM

```http
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"
Content-Type: multipart/related;type="application/xop+xml";
              start="<http://tempuri.org/0>";start-info="text/xml";
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
Host: 131.107.72.15
Content-Length: 1501
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">
      <array>
        <xop:Include
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </array>
    </EchoBinaryAsString>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/1/632618206521093670>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
…Binary Content..
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
```

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a>Bezpieczny komunikat protokołu SOAP 1,2 WCF zakodowany przy użyciu mechanizmu MTOM
W tym przykładzie komunikat jest szyfrowany przy użyciu mechanizmu MTOM i protokołu SOAP 1,2, który jest chroniony przy użyciu protokołu WS-Security. Części binarne identyfikowane na potrzeby kodowania to zawartość `BinarySecurityToken` , `CipherValue` `EncryptedData` odpowiadająca zaszyfrowanemu podpisowi i treści zaszyfrowanej. Należy zauważyć, że program `CipherValue` `EncryptedKey` nie został zidentyfikowany do optymalizacji przez WCF, ponieważ jego długość jest mniejsza niż 1024 bajtów.

```http
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1
Content-Type: multipart/related; type="application/xop+xml";
              start="<http://tempuri.org/0>";
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";
              start-info="application/soap+xml";
              action="http://xmlsoap.org/echoBinaryAsString"
Host: 131.107.72.15
Content-Length: 1941
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
  <s:Header>
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>
      </u:Timestamp>
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </o:BinarySecurityToken>
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>
        </e:CipherData>
      </e:EncryptedKey>
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">
        <o:SecurityTokenReference>
          <o:Reference URI="#_1"/>
        </o:SecurityTokenReference>
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>
      </c:DerivedKeyToken>
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:DataReference URI="#_3"/>
        <e:DataReference URI="#_4"/>
      </e:ReferenceList>
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:Reference URI="#_2"/>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>
          <e:CipherValue>
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
          </e:CipherValue>
        </e:CipherData>
      </e:EncryptedData>
    </o:Security>
  </s:Header>
  <s:Body u:Id="_0">
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
          <o:Reference URI="#_2"/>
        </o:SecurityTokenReference>
      </KeyInfo>
      <e:CipherData>
        <e:CipherValue>
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
        </e:CipherValue>
      </e:CipherData>
    </e:EncryptedData>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/1/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary content of BinarySecurityToken - X509 Certificate...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/2/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted primary signature...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/3/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted Body...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--
```
