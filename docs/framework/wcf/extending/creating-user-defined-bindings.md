---
title: Tworzenie wiązań zdefiniowanych przez użytkownika
ms.date: 03/30/2017
helpviewer_keywords:
- user-defined bindings [WCF]
ms.assetid: c4960675-d701-4bc9-b400-36a752fdd08b
ms.openlocfilehash: ba40bcfd8a9e9fea1a422ed124b9a966819bf184
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257857"
---
# <a name="creating-user-defined-bindings"></a>Tworzenie wiązań zdefiniowanych przez użytkownika

Istnieje kilka sposobów tworzenia powiązań niedostarczonych przez system:  
  
- Utwórz niestandardowe powiązanie na podstawie <xref:System.ServiceModel.Channels.CustomBinding> klasy, która jest kontenerem, który wypełnia elementy powiązania. Niestandardowe powiązanie jest następnie dodawane do punktu końcowego usługi. Niestandardowe powiązanie można utworzyć programowo lub w pliku konfiguracyjnym aplikacji. Aby użyć elementu powiązania z pliku konfiguracyjnego aplikacji, element Binding musi być rozszerzany <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> . Aby uzyskać więcej informacji na temat powiązań niestandardowych, zobacz [niestandardowe powiązania](custom-bindings.md) i <xref:System.ServiceModel.Channels.CustomBinding> .  
  
- Można utworzyć klasę, która pochodzi ze standardowego powiązania. Na przykład można utworzyć klasę z <xref:System.ServiceModel.WSHttpBinding> i zastąpić <xref:System.ServiceModel.Channels.CustomBinding.CreateBindingElements%2A> metodę, aby uzyskać elementy powiązania i wstawić niestandardowy element powiązania lub określić określoną wartość zabezpieczeń.  
  
- Można utworzyć nowy <xref:System.ServiceModel.Channels.Binding> Typ, aby całkowicie kontrolować całą implementację wdrożenia.  
  
## <a name="the-order-of-binding-elements"></a>Kolejność elementów powiązania  

 Każdy element powiązania reprezentuje etap przetwarzania podczas wysyłania lub otrzymywania wiadomości. W czasie wykonywania elementy powiązania tworzą kanały i odbiorniki niezbędne do tworzenia stosów kanałów wychodzących i przychodzących.  
  
 Istnieją trzy główne typy elementów powiązania: elementy powiązania protokołów, elementy powiązania kodowania i elementy powiązania transportowego.  
  
 Elementy powiązania protokołów — te elementy reprezentują kroki przetwarzania wyższego poziomu, które działają w przypadku komunikatów. Kanały i odbiorniki utworzone przez te elementy powiązania mogą dodawać, usuwać lub modyfikować zawartość wiadomości. Określone powiązanie może mieć dowolną liczbę elementów powiązania protokołów, z których każdy dziedziczy z <xref:System.ServiceModel.Channels.BindingElement> . Windows Communication Foundation (WCF) zawiera kilka elementów powiązania protokołów, w tym <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> i <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> .  
  
 Element powiązania kodowania — te elementy reprezentują przekształcenia między komunikatem a kodowaniem gotowym do transmisji w sieci. Typowe powiązania WCF obejmują dokładnie jeden element powiązania kodowania. Przykłady elementów powiązania kodowania obejmują,, <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> i <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> . Jeśli element powiązania kodowania nie jest określony dla powiązania, używane jest domyślne kodowanie. Wartość domyślna to Text, gdy transport jest HTTP i binarny w przeciwnym razie.  
  
 Element powiązania transportu — te elementy reprezentują transmisję komunikatu kodowania na protokole transportowym. Typowe powiązania WCF obejmują dokładnie jeden element powiązania transportu, który dziedziczy z <xref:System.ServiceModel.Channels.TransportBindingElement> . Przykłady elementów powiązania transportowego obejmują <xref:System.ServiceModel.Channels.TcpTransportBindingElement> ,, <xref:System.ServiceModel.Channels.HttpTransportBindingElement> i <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> .  
  
 W przypadku tworzenia nowych powiązań kolejność dodanych elementów powiązania jest ważna. Zawsze dodawaj elementy powiązania w następującej kolejności:  
  
|Warstwa|Opcje|Wymagany|  
|-----------|-------------|--------------|  
|Przepływ transakcji|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement?displayProperty=nameWithType>|Nie|  
|Niezawodność|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType>|Nie|  
|Zabezpieczenia|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|Nie|  
|Złożony dupleks|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement?displayProperty=nameWithType>|Nie|  
|Encoding|Tekst, dane binarne, MTOM, niestandardowe|Tak\*|  
|Transport|TCP, nazwane potoki, HTTP, HTTPS, MSMQ, niestandardowe|Tak|  
  
\*Ponieważ kodowanie jest wymagane dla każdego powiązania, w przypadku, gdy kodowanie nie jest określone, WCF dodaje domyślne kodowanie. Wartość domyślna to Text/XML dla transportów HTTP i HTTPS, a w przeciwnym razie dane binarne.  
  
## <a name="creating-a-new-binding-element"></a>Tworzenie nowego elementu powiązania  

 Oprócz typów pochodnych <xref:System.ServiceModel.Channels.BindingElement> dostarczonych przez program WCF można tworzyć własne elementy powiązania. Dzięki temu można dostosować sposób tworzenia stosu powiązań oraz składniki, które go tworzą, tworząc własne <xref:System.ServiceModel.Channels.BindingElement> , które mogą być składane z innymi typami udostępnionymi przez system w stosie.  
  
 Na przykład w przypadku zaimplementowania programu `LoggingBindingElement` , który zapewnia możliwość rejestrowania komunikatu w bazie danych, należy umieścić go powyżej kanału transportu w stosie kanałów. W takim przypadku aplikacja tworzy niestandardowe powiązanie, które składa się `LoggingBindingElement` z `TcpTransportBindingElement` , jak w poniższym przykładzie.  
  
```csharp  
Binding customBinding = new CustomBinding(  
  new LoggingBindingElement(),
  new TcpTransportBindingElement()  
);  
```  
  
 Sposób pisania nowego elementu powiązania zależy od jego dokładnej funkcjonalności. Jeden z przykładów, [transport: UDP](../samples/transport-udp.md), zawiera szczegółowy opis sposobu implementacji jednego rodzaju elementu powiązania.  
  
## <a name="creating-a-new-binding"></a>Tworzenie nowego powiązania  

 Element powiązania utworzony przez użytkownika może być używany na dwa sposoby. Poprzednia sekcja ilustruje pierwszy sposób: za pomocą niestandardowego powiązania. Niestandardowe powiązanie umożliwia użytkownikowi tworzenie własnych powiązań na podstawie dowolnego zestawu elementów powiązania, w tym utworzonych przez użytkownika.  
  
 Jeśli używasz powiązania w więcej niż jednej aplikacji, Utwórz własne powiązanie i rozszerzaj <xref:System.ServiceModel.Channels.Binding> . Pozwala to uniknąć ręcznego tworzenia powiązania niestandardowego za każdym razem, gdy chcesz go używać. Powiązanie zdefiniowane przez użytkownika umożliwia zdefiniowanie zachowania powiązania i uwzględnienie elementów powiązania zdefiniowanych przez użytkownika. I jest on *wstępnie spakowany*: nie trzeba ponownie kompilować powiązania za każdym razem, gdy jest on używany.  
  
 Jako minimum, zdefiniowane przez użytkownika powiązanie musi implementować <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> metodę i <xref:System.ServiceModel.Channels.Binding.Scheme%2A> Właściwość.  
  
 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>Metoda zwraca nowy <xref:System.ServiceModel.Channels.BindingElementCollection> , który zawiera elementy powiązania dla powiązania. Kolekcja jest uporządkowana i powinna zawierać najpierw elementy powiązania protokołów, a następnie element powiązania kodowania, a następnie element powiązania transportu. W przypadku używania elementów powiązania dostarczonych przez system WCF należy przestrzegać reguł porządkowania elementów powiązania określonych w [powiązaniach niestandardowych](custom-bindings.md). Ta kolekcja nigdy nie powinna odwoływać się do obiektów, do których odwołuje się Klasa powiązań zdefiniowana przez użytkownika; w związku z tym, autorzy powiązań muszą zwrócić `Clone()` z <xref:System.ServiceModel.Channels.BindingElementCollection> każdego wywołania do <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> .  
  
 <xref:System.ServiceModel.Channels.Binding.Scheme%2A>Właściwość reprezentuje schemat URI dla używanego protokołu transportowego w ramach powiązania. Na przykład *WSHttpBinding* i *NetTcpBinding* zwracają "http" i "net. TCP" z odpowiednich <xref:System.ServiceModel.Channels.Binding.Scheme%2A> właściwości.  
  
 Aby uzyskać pełną listę opcjonalnych metod i właściwości dla powiązań zdefiniowanych przez użytkownika, zobacz <xref:System.ServiceModel.Channels.Binding> .  
  
### <a name="example"></a>Przykład  

 Ten przykład implementuje powiązanie profilu w `SampleProfileUdpBinding` , który pochodzi od <xref:System.ServiceModel.Channels.Binding> . `SampleProfileUdpBinding`Zawiera maksymalnie cztery elementy powiązań w obrębie siebie: jeden utworzony przez użytkownika `UdpTransportBindingElement` i trzy systemy: `TextMessageEncodingBindingElement` , `CompositeDuplexBindingElement` , i `ReliableSessionBindingElement` .  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
## <a name="security-restrictions-with-duplex-contracts"></a>Ograniczenia zabezpieczeń z kontraktami dwustronnymi  

 Nie wszystkie elementy powiązania są zgodne ze sobą. W szczególności istnieją pewne ograniczenia dotyczące elementów powiązań zabezpieczeń, gdy są używane z kontraktami dwustronnymi.  
  
### <a name="one-shot-security"></a>Zabezpieczenia One-Shot  

 Możesz zaimplementować zabezpieczenia "z jednym zrzutem", gdzie wszystkie niezbędne poświadczenia zabezpieczeń są wysyłane w jednym komunikacie, ustawiając `negotiateServiceCredential` atrybut \<message> elementu konfiguracji na `false` .  
  
 Uwierzytelnianie z użyciem jednego z zrzutów nie działa z kontraktami dwustronnymi.  
  
 W przypadku kontraktów Request-Reply uwierzytelnianie jednokrotne działa tylko wtedy, gdy stos powiązań poniżej elementu powiązania zabezpieczeń obsługuje <xref:System.ServiceModel.Channels.IRequestChannel> Tworzenie <xref:System.ServiceModel.Channels.IRequestSessionChannel> wystąpień lub.  
  
 W przypadku zamówień jednokierunkowych uwierzytelnianie z zastosowaniem jednego z nich działa, jeśli stos powiązań poniżej elementu powiązania zabezpieczeń obsługuje tworzenie <xref:System.ServiceModel.Channels.IRequestChannel> , <xref:System.ServiceModel.Channels.IRequestSessionChannel> <xref:System.ServiceModel.Channels.IOutputChannel> lub <xref:System.ServiceModel.Channels.IOutputSessionChannel> wystąpień.  
  
### <a name="cookie-mode-security-context-tokens"></a>Tokeny kontekstu zabezpieczeń trybu cookie  

 Tokeny kontekstu zabezpieczeń trybu plików cookie nie mogą być używane z kontraktami dwustronnymi.  
  
 W przypadku kontraktów Request-Reply tokeny kontekstu zabezpieczeń trybu cookie działają tylko wtedy, gdy stos powiązań poniżej elementu powiązania zabezpieczeń obsługuje <xref:System.ServiceModel.Channels.IRequestChannel> Tworzenie <xref:System.ServiceModel.Channels.IRequestSessionChannel> wystąpień lub.  
  
 W przypadku kontraktów jednokierunkowych tokeny kontekstu zabezpieczeń trybu cookie działają, jeśli stos powiązań poniżej elementu powiązania zabezpieczeń obsługuje tworzenie <xref:System.ServiceModel.Channels.IRequestChannel> <xref:System.ServiceModel.Channels.IRequestSessionChannel> wystąpień lub.  
  
### <a name="session-mode-security-context-tokens"></a>Tokeny kontekstu zabezpieczeń trybu sesji  

 Tryb sesji SCT działa w przypadku kontraktów dwustronnych, jeśli stos powiązań poniżej elementu powiązania zabezpieczeń obsługuje tworzenie <xref:System.ServiceModel.Channels.IDuplexChannel> <xref:System.ServiceModel.Channels.IDuplexSessionChannel> wystąpień lub.  
  
 Tryb sesji SCT działa dla kontraktów Request-Reply, jeśli stos powiązań poniżej elementu powiązania zabezpieczeń obsługuje tworzenie <xref:System.ServiceModel.Channels.IDuplexChannel> , <xref:System.ServiceModel.Channels.IDuplexSessionChannel> , <xref:System.ServiceModel.Channels.IRequestChannel> lub <xref:System.ServiceModel.Channels.IRequestSessionChannel> , wystąpienia.  
  
 Tryb sesji SCT działa dla kontraktów jednokierunkowych, jeśli stos powiązań poniżej elementu powiązania zabezpieczeń obsługuje tworzenie <xref:System.ServiceModel.Channels.IDuplexChannel> , <xref:System.ServiceModel.Channels.IDuplexSessionChannel> <xref:System.ServiceModel.Channels.IRequestChannel> lub <xref:System.ServiceModel.Channels.IRequestSessionChannel> wystąpień.  
  
## <a name="deriving-from-a-standard-binding"></a>Wyprowadzanie ze standardowego powiązania  

 Zamiast tworzyć zupełnie nową klasę powiązań, może być możliwe rozszerzanie jednego z istniejących powiązań dostarczonych przez system. Podobnie jak w przypadku poprzedniego przypadku, należy zastąpić <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> metodę i <xref:System.ServiceModel.Channels.Binding.Scheme%2A> Właściwość.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.Binding>
- [Powiązania niestandardowe](custom-bindings.md)
