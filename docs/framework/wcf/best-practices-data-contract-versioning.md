---
title: 'Najlepsze rozwiązania: Przechowywanie wersji kontraktów danych'
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- service contracts
- best practices [WCF], data contract versioning
- Windows Communication Foundation, data contracts
ms.assetid: bf0ab338-4d36-4e12-8002-8ebfdeb346cb
ms.openlocfilehash: d6a1eef949e30a1a6d9a1c5971d33c788cc548b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277910"
---
# <a name="best-practices-data-contract-versioning"></a>Najlepsze rozwiązania: Przechowywanie wersji kontraktów danych

W tym temacie przedstawiono najlepsze rozwiązania dotyczące tworzenia kontraktów danych, które mogą być łatwo rozmieszczone w czasie. Aby uzyskać więcej informacji na temat umów dotyczących danych, zobacz tematy dotyczące [korzystania z kontraktów danych](./feature-details/using-data-contracts.md).  
  
## <a name="note-on-schema-validation"></a>Uwaga dotycząca weryfikacji schematu  

 W omawianiu wersji kontraktu danych należy zauważyć, że schemat kontraktu danych wyeksportowany przez Windows Communication Foundation (WCF) nie ma żadnej obsługi wersji, inne niż fakt, że elementy są domyślnie oznaczone jako opcjonalne.  
  
 Oznacza to, że nawet najbardziej typowy scenariusz obsługi wersji, taki jak dodanie nowego elementu członkowskiego danych, nie może być zaimplementowany w sposób, który jest bezproblemowy w odniesieniu do danego schematu. Nowsze wersje kontraktu danych (na przykład z nowym elementem członkowskim danych) nie weryfikują się przy użyciu starego schematu.  
  
 Istnieje jednak wiele scenariuszy, w których ścisła zgodność schematu nie jest wymagana. Wiele platform usług sieci Web, w tym usług sieci Web WCF i XML utworzonych za pomocą ASP.NET, nie przeprowadzaj walidacji schematu domyślnie, dlatego można tolerować dodatkowe elementy, które nie są opisane przez schemat. Podczas pracy z takimi platformami scenariusze wielu wersji są łatwiejsze do wdrożenia.  
  
 W ten sposób istnieją dwa zestawy wytycznych dotyczących wersji kontraktu danych: jeden zestaw dla scenariuszy, w których ważna jest ścisła ważność schematu i inny zestaw dla scenariuszy, gdy nie jest.  
  
## <a name="versioning-when-schema-validation-is-required"></a>Przechowywanie wersji, gdy wymagana jest Walidacja schematu  

 Jeśli wymagana jest ścisła ważność schematu we wszystkich kierunkach (od nowa do starych i starych do nowych), kontrakty danych należy traktować jako niezmienne. Jeśli wymagana jest obsługa wersji, należy utworzyć nowy kontrakt danych z inną nazwą lub przestrzenią nazw, a kontrakt usługi przy użyciu typu danych powinien mieć odpowiednią wersję.  
  
 Na przykład kontrakt usługi przetwarzania zamówień zakupu o nazwie `PoProcessing` z `PostPurchaseOrder` operacją przyjmuje parametr, który jest zgodny z `PurchaseOrder` kontraktem danych. Jeśli `PurchaseOrder` umowa musi ulec zmianie, należy utworzyć nowy kontrakt danych, czyli, `PurchaseOrder2` który zawiera zmiany. Następnie należy obsłużyć obsługę wersji na poziomie kontraktu usługi. Na przykład przez utworzenie `PostPurchaseOrder2` operacji pobierającej `PurchaseOrder2` parametr lub przez utworzenie `PoProcessing2` kontraktu usługi, w którym `PostPurchaseOrder` operacja przyjmuje `PurchaseOrder2` kontrakt danych.  
  
 Należy zauważyć, że zmiany umów dotyczących danych, do których odwołują się inne kontrakty danych, również przechodzą do warstwy modelu usług. Na przykład w poprzednim scenariuszu `PurchaseOrder` nie trzeba zmieniać kontraktu danych. Jednak zawiera element członkowski danych `Customer` kontraktu danych, który z kolei zawierał element członkowski danych `Address` kontraktu danych, który należy zmienić. W takim przypadku konieczne będzie utworzenie `Address2` kontraktu danych z wymaganymi zmianami, `Customer2` kontraktem danych zawierającym `Address2` element członkowski danych i `PurchaseOrder2` kontraktem danych zawierającym `Customer2` element członkowski danych. Tak jak w poprzednim przypadku, kontrakt usługi będzie musiał również mieć wersję.  
  
 Chociaż w tych przykładach nazwy zostały zmienione (poprzez dołączenie "2"), zaleca się zmianę przestrzeni nazw zamiast nazw przez dołączenie nowych przestrzeni nazw z numerem wersji lub datą. Na przykład `http://schemas.contoso.com/2005/05/21/PurchaseOrder` kontrakt danych zmieni się na `http://schemas.contoso.com/2005/10/14/PurchaseOrder` kontrakt danych.  
  
 Aby uzyskać więcej informacji, Zobacz najlepsze rozwiązania: [przechowywanie wersji usługi](service-versioning.md).  
  
 Czasami należy zagwarantować ścisłą zgodność schematu dla komunikatów wysyłanych przez aplikację, ale nie można polegać na komunikatach przychodzących, które są ściśle zgodne ze schematem. W takim przypadku istnieje zagrożenie, że komunikat przychodzący może zawierać dane nadmiarowe. Nadmiarowe wartości są przechowywane i zwracane przez program WCF i w rezultacie są wysyłane komunikaty nieprawidłowe w schemacie. Aby uniknąć tego problemu, funkcja okrężna musi być wyłączona. Istnieją dwa sposoby, aby to zrobić.  
  
- Nie należy implementować <xref:System.Runtime.Serialization.IExtensibleDataObject> interfejsu na żadnym z typów.  
  
- Zastosuj <xref:System.ServiceModel.ServiceBehaviorAttribute> atrybut do kontraktu usługi z <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> właściwością ustawioną na `true` .  
  
 Aby uzyskać więcej informacji na temat rundy, zobacz [Kontrakty danych zgodne z przekazywaniem dalej](./feature-details/forward-compatible-data-contracts.md).  
  
## <a name="versioning-when-schema-validation-is-not-required"></a>Przechowywanie wersji, gdy Walidacja schematu nie jest wymagana  

 Ścisła zgodność schematu jest rzadko wymagana. Wiele platform tolerowanie dodatkowych elementów nieopisanych przez schemat. Tak długo, jak to jest dopuszczalne, można użyć pełnego zestawu funkcji opisanych w temacie [przechowywanie wersji kontraktu danych](./feature-details/data-contract-versioning.md) i [Kontrakty danych zgodne z przekazaniem dalej](./feature-details/forward-compatible-data-contracts.md) . Zalecane są następujące wskazówki.  
  
 Aby można było wysyłać nowe wersje typu, w przypadku których oczekiwany jest starszy lub wysyłany jest stary, w niektórych przypadkach należy wykonać tylko te wskazówki. Inne wskazówki nie są ściśle wymagane, ale są wymienione w tym miejscu, ponieważ mogą one mieć wpływ na przyszłą wersję schematu.  
  
1. Nie należy próbować uzyskać wersji kontraktów danych przez dziedziczenie typu. Aby utworzyć późniejsze wersje, należy zmienić kontrakt danych na istniejącym typie lub utworzyć nowy niepowiązany typ.  
  
2. Użycie dziedziczenia wraz z kontraktami danych jest dozwolone, pod warunkiem, że dziedziczenie nie jest używane jako mechanizm obsługi wersji i że są stosowane pewne reguły. Jeśli typ pochodzi od określonego typu podstawowego, nie należy dziedziczyć go z innego typu podstawowego w przyszłej wersji (chyba że ma ten sam kontrakt danych). Istnieje jeden wyjątek: można wstawić typ do hierarchii między typem kontraktu danych i jego typem bazowym, ale tylko wtedy, gdy nie zawiera składowych danych o takich samych nazwach jak inne elementy członkowskie w innych typach w hierarchii. Ogólnie rzecz biorąc, używanie elementów członkowskich danych o takich samych nazwach na różnych poziomach hierarchii dziedziczenia może prowadzić do poważnych problemów z wersją i należy je unikać.  
  
3. Począwszy od pierwszej wersji kontraktu danych, zawsze Wdrażaj, <xref:System.Runtime.Serialization.IExtensibleDataObject> Aby umożliwić wykonywanie rundy. Aby uzyskać więcej informacji, zobacz [Kontrakty danych zgodne z przekazywaniem dalej](./feature-details/forward-compatible-data-contracts.md). Jeśli wydano co najmniej jedną wersję typu bez implementowania tego interfejsu, należy zaimplementować ją w następnej wersji typu.  
  
4. W nowszych wersjach nie należy zmieniać nazwy kontraktu danych ani przestrzeni nazw. Jeśli zmieniasz nazwę lub przestrzeń nazw typu podstawowego kontraktu danych, pamiętaj, aby zachować nazwę i przestrzeń nazw kontraktu danych przy użyciu odpowiednich mechanizmów, takich jak <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> Właściwość <xref:System.Runtime.Serialization.DataContractAttribute> . Aby uzyskać więcej informacji o nazewnictwie, zobacz [nazwy kontraktów danych](./feature-details/data-contract-names.md).  
  
5. W nowszych wersjach nie należy zmieniać nazw żadnych elementów członkowskich danych. W przypadku zmiany nazwy pola, właściwości lub zdarzenia będącego elementem członkowskim danych Użyj `Name` właściwości, <xref:System.Runtime.Serialization.DataMemberAttribute> Aby zachować istniejącą nazwę elementu członkowskiego danych.  
  
6. W nowszych wersjach nie należy zmieniać typu żadnego pola, właściwości ani zdarzenia będącego członkiem danych, w taki sposób, że kontrakt danych uzyskanych dla tego elementu członkowskiego danych ulega zmianie. Należy pamiętać, że typy interfejsów są równoważne do <xref:System.Object> celów określania oczekiwanego kontraktu danych.  
  
7. W nowszych wersjach nie zmieniaj kolejności istniejących elementów członkowskich danych przez dostosowanie <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> właściwości <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutu.  
  
8. W nowszych wersjach można dodać nowe składowe danych. Należy zawsze przestrzegać następujących zasad:  
  
    1. <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>Właściwość powinna zawsze pozostać w pozostałej wartości domyślnej `false` .  
  
    2. Jeśli wartość domyślna `null` lub zero dla elementu członkowskiego jest nieakceptowalna, należy podać metodę wywołania zwrotnego przy użyciu polecenia, <xref:System.Runtime.Serialization.OnDeserializingAttribute> Aby zapewnić rozsądne ustawienie domyślne na wypadek, gdyby element członkowski nie był obecny w strumieniu przychodzącym. Aby uzyskać więcej informacji na temat wywołania zwrotnego, zobacz [wywołania zwrotne serializacji odporne na wersje](./feature-details/version-tolerant-serialization-callbacks.md).  
  
    3. <xref:System.Runtime.Serialization.DataMemberAttribute.Order?displayProperty=nameWithType>Właściwość powinna być używana do upewnienia się, że wszystkie nowo dodane elementy członkowskie danych są wyświetlane po istniejących elementach członkowskich danych. W tym celu zaleca się wykonanie następujących czynności: żaden z elementów członkowskich danych w pierwszej wersji kontraktu danych nie powinien mieć `Order` ustawionej właściwości. Wszystkie elementy członkowskie danych dodane w wersji 2 kontraktu danych powinny mieć `Order` ustawioną właściwość na 2. Wszyscy członkowie danych dodani w wersji 3 kontraktu danych powinni mieć `Order` ustawioną wartość 3 i tak dalej. Dozwolone jest posiadanie więcej niż jednego elementu członkowskiego danych na tym samym `Order` numerze.  
  
9. Nie usuwaj elementów członkowskich danych w nowszych wersjach, nawet jeśli <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> Właściwość została pozostawiona z domyślną właściwością `false` w poprzednich wersjach.  
  
10. Nie należy zmieniać `IsRequired` właściwości dla żadnych istniejących elementów członkowskich danych z wersji do wersji.  
  
11. W przypadku wymaganych składowych danych (gdzie `IsRequired` is `true` ) nie zmieniaj `EmitDefaultValue` właściwości z wersji na wersję.  
  
12. Nie należy podejmować próby utworzenia gałęziowych hierarchii wersji. Oznacza to, że zawsze powinna być ścieżką w co najmniej jednym kierunku od dowolnej wersji do innej wersji, używając tylko zmian dozwolonych w tych wytycznych.  
  
     Na przykład jeśli wersja 1 kontraktu danych osoby zawiera tylko element członkowski danych, nie należy tworzyć wersji 2a kontraktu, dodając tylko członka wieku i wersji 2b, dodając tylko członka adresu. Przejście od od 2A do 2b spowoduje usunięcie wieku i dodanie adresu; przejście w inne kierunki spowoduje usunięcie adresu i dodanie wieku. Te wytyczne nie zezwalają na usuwanie członków.  
  
13. Zazwyczaj nie należy tworzyć nowych podtypów istniejących typów kontraktu danych w nowej wersji aplikacji. Podobnie nie należy tworzyć nowych kontraktów danych, które są używane zamiast składowych danych zadeklarowanych jako obiekt lub jako typy interfejsów. Tworzenie tych nowych klas jest dozwolone tylko wtedy, gdy wiadomo, że można dodać nowe typy do listy znanych typów wszystkich wystąpień starego aplikacji. Na przykład w wersji 1 aplikacji może istnieć typ kontraktu danych LibraryItem z podtypem kontraktu i danych dotyczących książki i gazetowej. Następnie LibraryItem będzie zawierać listę znanych typów, która zawiera książkę i gazetę. Załóżmy, że teraz dodasz typ magazynu w wersji 2, która jest podtypem LibraryItem. Jeśli wyślesz wystąpienie magazynu z wersji 2 do wersji 1, kontrakt danych magazynu nie zostanie znaleziony na liście znanych typów i zostanie zgłoszony wyjątek.  
  
14. Nie należy dodawać ani usuwać elementów członkowskich wyliczenia między wersjami. Nie należy również zmieniać nazw elementów członkowskich wyliczenia, chyba że jest używana Właściwość Name w `EnumMemberAttribute` atrybucie, aby zachować swoje nazwy w modelu kontraktu danych.  
  
15. Kolekcje są zamienne w modelu kontraktu danych, zgodnie z opisem w obszarze [typy kolekcji w kontraktach danych](./feature-details/collection-types-in-data-contracts.md). Pozwala to na doskonałe elastyczność. Należy jednak pamiętać, że nie można przypadkowo zmienić typu kolekcji w sposób niewymienny z wersji na wersję. Na przykład nie należy zmieniać kolekcji dostosowanej (to oznacza, że bez `CollectionDataContractAttribute` atrybutu) do dostosowanej kolekcji, która jest dostosowana do niedostosowanego elementu. Ponadto nie należy zmieniać właściwości z wersji na wersję `CollectionDataContractAttribute` . Jedyną dozwoloną zmianą jest dodanie nazwy lub właściwości przestrzeni nazw, jeśli nazwa lub przestrzeń nazw odpowiedniego typu kolekcji uległy zmianie i należy wprowadzić swoją nazwę kontraktu danych i przestrzeń nazw tak samo jak w poprzedniej wersji.  
  
 Niektóre z wymienionych poniżej wskazówek można bezpiecznie zignorować w przypadku zastosowania specjalnych okoliczności. Upewnij się, że w pełni rozumiesz mechanizmy serializacji, deserializacji i schematu, które są wykorzystywane przed odchyleniami od wytycznych.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>
- <xref:System.Runtime.Serialization.IExtensibleDataObject>
- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>
- <xref:System.Runtime.Serialization.ExtensionDataObject>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- [Używanie kontraktów danych](./feature-details/using-data-contracts.md)
- [Przechowywanie wersji kontraktów danych](./feature-details/data-contract-versioning.md)
- [Nazwy kontraktów danych](./feature-details/data-contract-names.md)
- [Kontrakty danych zgodne z nowszymi wersjami](./feature-details/forward-compatible-data-contracts.md)
- [Wywołania zwrotne serializacji z tolerancją dla wersji](./feature-details/version-tolerant-serialization-callbacks.md)
