---
title: Niestandardowe uaktualnienia strumienia
ms.date: 03/30/2017
ms.assetid: e3da85c8-57f3-4e32-a4cb-50123f30fea6
ms.openlocfilehash: 3ef0f59a5d63c24188b29cb7a38db2d6323d80ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295587"
---
# <a name="custom-stream-upgrades"></a>Niestandardowe uaktualnienia strumienia

Transporty ukierunkowane na strumień, takie jak TCP i nazwane potoki, działają na ciągłym strumieniu bajtów między klientem a serwerem. Ten strumień jest realizowany przez  <xref:System.IO.Stream> obiekt. W przypadku uaktualnienia strumienia klient chce dodać opcjonalną warstwę protokołu do stosu kanału i poprosi o podanie drugiego końca kanału komunikacyjnego. Uaktualnienie strumienia obejmuje zastępowanie oryginalnego <xref:System.IO.Stream> obiektu uaktualnioną wersją.  
  
 Na przykład można skompilować strumień kompresji bezpośrednio na górze strumienia transportowego. W takim przypadku oryginalny transport <xref:System.IO.Stream> jest zastępowany, który otacza kompresję <xref:System.IO.Stream> wokół oryginalnej.  
  
 Można zastosować wiele uaktualnień strumienia, z których każdy otacza poprzedni.  
  
## <a name="how-stream-upgrades-work"></a>Jak działają uaktualnienia strumienia  

 Proces uaktualniania strumienia obejmuje cztery składniki.  
  
1. *Inicjator* strumienia uaktualnienia rozpoczyna proces: w czasie wykonywania można zainicjować żądanie do drugiego końca jego połączenia w celu uaktualnienia warstwy transportu kanału.  
  
2. Element *akceptujący* strumień uaktualnienia przeprowadzi uaktualnienie: w czasie wykonywania otrzyma żądanie uaktualnienia z innej maszyny, a jeśli to możliwe, akceptuje uaktualnienie.  
  
3. *Dostawca* uaktualnienia tworzy *inicjatora* na kliencie *i na serwerze* .  
  
4. *Element powiązania* uaktualnienia strumienia jest dodawany do powiązań usługi i klienta, a następnie tworzony jest dostawca w czasie wykonywania.  
  
 Należy zauważyć, że w przypadku wielu uaktualnień inicjator i element akceptujący hermetyzowają automaty stanu, aby wymusić, które przejścia uaktualnienia są prawidłowe dla każdej inicjacji.  
  
## <a name="how-to-implement-a-stream-upgrade"></a>Jak zaimplementować uaktualnienie strumienia  

 Windows Communication Foundation (WCF) oferuje cztery `abstract` klasy, które można zaimplementować:  
  
- <xref:System.ServiceModel.Channels.StreamUpgradeInitiator?displayProperty=nameWithType>  
  
- <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor?displayProperty=nameWithType>  
  
- <xref:System.ServiceModel.Channels.StreamUpgradeProvider?displayProperty=nameWithType>  
  
- <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement?displayProperty=nameWithType>  
  
 Aby zaimplementować niestandardowe uaktualnienie strumienia, wykonaj następujące czynności. Ta procedura implementuje minimalny proces uaktualniania strumienia na komputerach klienckich i serwerach.  
  
1. Utwórz klasę implementującą <xref:System.ServiceModel.Channels.StreamUpgradeInitiator> .  
  
    1. Zastąp <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.InitiateUpgrade%2A> metodę, aby wykonać uaktualnienie strumienia i zwrócić uaktualniony strumień. Ta metoda działa synchronicznie; istnieją podobne metody inicjowania asynchronicznego uaktualniania.  
  
    2. Zastąp <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> metodę, aby wyszukać dodatkowe uaktualnienia.  
  
2. Utwórz klasę implementującą <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor> .  
  
    1. Zastąp <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.AcceptUpgrade%2A> metodę, aby wykonać uaktualnienie strumienia i zwrócić uaktualniony strumień. Ta metoda działa synchronicznie; istnieją podobne metody do asynchronicznego zaakceptowania uaktualnienia.  
  
    2. Zastąp <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> metodę, aby określić, czy żądanie uaktualnienia jest obsługiwane przez ten program akceptujący uaktualnienie w tym momencie w procesie uaktualniania.  
  
3. Utwórz klasę implementującą <xref:System.ServiceModel.Channels.StreamUpgradeProvider> . Zastąp <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeAcceptor%2A> metody i, <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeInitiator%2A> aby zwracać wystąpienia obiektu akceptującego i inicjatora zdefiniowane w krokach 2 i 1.  
  
4. Utwórz klasę implementującą <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> .  
  
    1. Zastąp <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildClientStreamUpgradeProvider%2A> metodę na kliencie i <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildServerStreamUpgradeProvider%2A> metodą w usłudze.  
  
    2. Zastąp <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> metodę na kliencie i <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> metodę w usłudze, aby dodać element powiązania uaktualnienia do programu <xref:System.ServiceModel.Channels.BindingContext.BindingParameters%2A> .  
  
5. Dodaj nowy element powiązania uaktualniania strumienia do powiązań na serwerze i na komputerach klienckich.  
  
## <a name="security-upgrades"></a>Uaktualnienia zabezpieczeń  

 Dodanie uaktualnienia zabezpieczeń to wyspecjalizowana wersja ogólnego procesu uaktualniania strumienia.  
  
 Funkcja WCF udostępnia już dwa elementy powiązania do uaktualniania zabezpieczeń strumienia. Konfiguracja zabezpieczeń na poziomie transportu jest hermetyzowana przez program <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> i, <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement> który można skonfigurować i dodać do niestandardowego powiązania. Te elementy powiązania rozszerzają <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> klasę, która kompiluje dostawców uaktualnienia strumienia klienta i serwera. Te elementy powiązania mają metody, które tworzą wyspecjalizowane klasy dostawcy uaktualnienia strumienia zabezpieczeń, które nie są `public` Tak więc dla tych dwóch przypadków należy dodać element powiązania do powiązania.  
  
 W przypadku scenariuszy zabezpieczeń, które nie są spełnione przez powyższe dwa elementy powiązania, trzy `abstract` klasy powiązane z zabezpieczeniami pochodzą z powyższej klasy inicjatora, elementu akceptującego i klas podstawowych dostawcy:  
  
1. <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator?displayProperty=nameWithType>  
  
2. <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor?displayProperty=nameWithType>  
  
3. <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider?displayProperty=nameWithType>  
  
 Proces implementowania uaktualnienia strumienia zabezpieczeń jest taki sam jak poprzednio, z różnicą, jaką można utworzyć przy użyciu tych trzech klas. Zastąp dodatkowe właściwości w tych klasach, aby dostarczyć informacje o zabezpieczeniach do środowiska uruchomieniowego.  
  
## <a name="multiple-upgrades"></a>Wiele uaktualnień  

 Aby utworzyć dodatkowe żądania uaktualnienia, powtórz powyższy proces: Utwórz dodatkowe rozszerzenia <xref:System.ServiceModel.Channels.StreamUpgradeProvider> elementów i powiązania. Dodaj elementy powiązania do powiązania. Dodatkowe elementy powiązania są przetwarzane sekwencyjnie, rozpoczynając od pierwszego elementu powiązania dodanego do powiązania. W <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> systemach i każdy dostawca uaktualnienia może określić, jak należy wykonać warstwę dla wszystkich istniejących parametrów powiązań uaktualnienia. Następnie należy zastąpić istniejący parametr powiązania uaktualnienia nowym parametrem powiązania uaktualnienia złożonego.  
  
 Alternatywnie jeden dostawca uaktualnienia może obsługiwać wiele uaktualnień. Na przykład możesz chcieć zaimplementować niestandardowego dostawcę uaktualnienia strumienia, który obsługuje zabezpieczenia i kompresję. Wykonaj następujące czynności:  
  
1. Podklasa <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider> do zapisania klasy dostawcy, która tworzy inicjatora i odpowiednika.  
  
2. Podklasa, która <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator> zapewnia zastąpienie <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> metody w celu zwrócenia typów zawartości dla strumienia kompresji i bezpiecznego strumienia w kolejności.  
  
3. Podklasa, <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor> która rozumie niestandardowe typy zawartości w swojej <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> metodzie.  
  
4. Strumień zostanie uaktualniony po każdym wywołaniu do <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> i <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> .  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator>
- <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor>
- <xref:System.ServiceModel.Channels.StreamUpgradeProvider>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider>
- <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
