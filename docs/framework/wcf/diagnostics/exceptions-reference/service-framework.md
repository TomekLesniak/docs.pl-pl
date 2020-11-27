---
title: Struktura usługi
ms.date: 03/30/2017
ms.assetid: 75f60b87-f80e-4377-ba7c-8e6becaa2b28
ms.openlocfilehash: 1fb39f2106e027cc5d4125cfb0bc89f3e5983cec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285723"
---
# <a name="service-framework"></a>Struktura usługi

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez dane struktury usługi.  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|ABindingInstanceHasAlreadyBeenAssociatedTo1|Wystąpienie powiązania zostało już skojarzone, aby nasłuchiwać określonego identyfikatora Uniform Resource. Jeśli dwa punkty końcowe chcą współdzielić ten sam wskaźnik zasobów ListenUniform, muszą także mieć to samo wystąpienie obiektu powiązania. Dwa punkty końcowe powodujące konflikt zostały określone w wywołaniach AddServiceEndpoint (), w pliku konfiguracyjnym lub kombinacji metody AddServiceEndpoint () i konfiguracji.|  
|AChannelServiceEndpointIsNull0|Punkt końcowy kanału lub usługi ma wartość null.|  
|AChannelServiceEndpointSContractSNameIsNull0|Nazwa kontraktu punktu końcowego kanału/usługi ma wartość null lub jest pusta.|  
|AChannelServiceEndpointSContractSNamespace0|Przestrzeń nazw kontraktu punktu końcowego kanału/usługi ma wartość null.|  
|BaseAddressCannotHaveFragment|Adres podstawowy nie może zawierać fragmentu jednolite identyfikatora zasobu.|  
|BaseAddressCannotHaveQuery|Adres podstawowy nie może zawierać ciągu zapytania o jednolity identyfikator zasobu.|  
|BaseAddressCannotHaveUserInfo|Adres podstawowy nie może zawierać sekcji informacji o użytkowniku o jednolitym identyfikatorze zasobu.|  
|BaseAddressDuplicateScheme|Ta kolekcja zawiera już adres z określonym schematem. Dla każdego schematu w tej kolekcji dozwolony jest tylko jeden adres.|  
|BaseAddressMustBeAbsolute|Jako adres podstawowy może być używany tylko bezwzględny jednolity identyfikator zasobu.|  
|BindingDoesnTSupportAnyChannelTypes1|Określone powiązanie nie obsługuje tworzenia żadnych typów kanałów. Elementy powiązania w niestandardowym powiązaniu są nieprawidłowo ułożone lub w niewłaściwej kolejności. Na końcu stosu jest wymagany transport. Zalecana kolejność dla elementów wiązania to: TransactionFlow, ReliableSession, Security, CompositeDuplex, OneWay, StreamSecurity, MessageEncoding, transport.|  
|BindingDoesnTSupportDuplexButContractRequires1|Kontrakt wymaga dupleksu. Określone powiązanie nie obsługuje go lub nie jest prawidłowo skonfigurowane do jego obsługi.|  
|BindingDoesnTSupportOneWayButContractRequires1|Kontrakt wymaga OneWay. Określone powiązanie nie obsługuje go lub nie jest prawidłowo skonfigurowane do jego obsługi.|  
|BindingDoesnTSupportRequestReplyButContract1|Kontrakt wymaga żądania/odpowiedzi. Określone powiązanie nie obsługuje go lub nie jest prawidłowo skonfigurowane do jego obsługi.|  
|BindingDoesnTSupportSessionButContractRequires1|Kontrakt wymaga sesji.  Określone powiązanie nie obsługuje go lub nie jest prawidłowo skonfigurowane do jego obsługi.|  
|BindingDoesnTSupportTwoWayButContractRequires1|Kontrakt wymaga Two-Way (żądanie-odpowiedź lub dupleks). Określone powiązanie nie obsługuje go lub nie jest prawidłowo skonfigurowane do jego obsługi.|  
|BindingRequirementsAttributeDisallowsQueuedDelivery1|Element DeliveryRequirementsAttribute nie zezwala na QueuedDelivery. Powiąże się z punktem końcowym z określonym kontraktem.|  
|BindingRequirementsAttributeRequiresQueuedDelivery1|Element DeliveryRequirementsAttribute wymaga QueuedDelivery. Powiązanie punktu końcowego z określonym kontraktem nie obsługuje go lub nie jest prawidłowo skonfigurowane do jego obsługi.|  
|channelDoesNotHaveADuplexSession0|Bieżący kanał nie obsługuje zamykania sesji wyjściowej. Ten kanał nie implementuje zaimplementowanego ISessionChannel \<IDuplexSession> .|  
|ClientRuntimeRequiresFormatter0|Określony ClientOperation wymaga elementu formatującego, ponieważ wartości SerializeRequest i DeserializeReply mają nie są jednocześnie fałszywe.|  
|CommunicationObjectAborted1|Nie można użyć określonego obiektu komunikacyjnego do komunikacji, ponieważ został zatrzymany.|  
|CommunicationObjectAbortedStack2|Nie można użyć określonego obiektu komunikacyjnego do komunikacji, ponieważ został zatrzymany: {1}|  
|CommunicationObjectBaseClassMethodNotCalled|Określony obiekt komunikacyjny przesłonił funkcję wirtualną, {1} ale nie wywołuje wersji zdefiniowanej w klasie bazowej.|  
|ContractIsNotSelfConsistentItHasOneOrMore2|Określony kontrakt zawiera jedną lub więcej operacji IsTerminating lub nie inicjujących. Właściwość SessionMode nie ma ustawionej wartości SessionMode. Required. Atrybutów IsInitiating i iskończona można używać tylko w kontekście sesji.|  
|CouldnTCreateChannelForChannelType2|Zażądano określonego typu kanału, ale określone powiązanie nie obsługuje go lub nie jest prawidłowo skonfigurowane do jego obsługi.|  
|DispatchRuntimeRequiresFormatter0|Określony element DispatchOperation wymaga elementu formatującego, ponieważ wartości właściwości DeserializeRequest i SerializeReply nie są jednocześnie fałszywe.|  
|EndMethodsCannotBeDecoratedWithOperationContractAttribute|Nie można używać metody end z atrybutem OperationContractAttribute w przypadku używania wzorca projektu IAsyncResult. Tylko odpowiadająca Metoda BEGIN może być używana z atrybutem OperationContractAttribute. Ten atrybut ma zastosowanie do pary Begin-End metod.|  
|EndpointListenerRequirementsCannotBeMetBy3|Wymagania elementu ChannelDispatcher nie mogą być spełnione przez ChannelDispatcher dla określonego powiązania, ponieważ kontrakt wymaga obsługi jednego z określonych typów kanałów. Ale powiązanie obsługuje tylko te określone typy kanałów.|  
|EndpointsMustHaveAValidBinding0|Punkty końcowe muszą mieć prawidłowe powiązanie.|  
|InvalidOrUnrecognizedAction|Nie można przetworzyć komunikatu, ponieważ określona akcja jest nieprawidłowa lub nie została rozpoznana.|  
|MultipleMebesInParameters|W właściwości BindingParameters BindingContext znaleziono więcej niż jeden MessageEncodingBindingElement. Element CustomBinding nie może mieć wielu MessageEncodingBindingElements. Usuń wszystkie oprócz jednego z tych elementów.|  
|MultipleStreamUpgradeProvidersInParameters|W właściwości BindingParameters BindingContext znaleziono więcej niż jeden IStreamUpgradeProviderElement. Element CustomBinding nie może mieć więcej niż jednego IStreamUpgradeProviderElements. Usuń wszystkie oprócz jednego z tych elementów.|  
|NoChannelBuilderAvailable|Nie można użyć powiązania do utworzenia fabryki kanałów lub odbiornika kanałów, ponieważ nie ma on elementu TransportBindingElement. Każde powiązanie musi zawierać co najmniej jeden element powiązania pochodzący z elementu TransportBindingElement.|  
|NotAllBindingElementsBuilt|Niektóre elementy powiązania w tym powiązaniu nie były używane podczas budowania fabryki kanałów i odbiornika kanałów. Elementy powiązania nie są prawidłowo uporządkowane. Zalecana kolejność dla elementów wiązania to: TransactionFlow, ReliableSession, Security, CompositeDuplex, OneWay, StreamSecurity, MessageEncoding, transport.  Należy pamiętać, że element TransportBindingElement musi być ostatni. Określone elementy powiązania nie zostały skompilowane.|  
|RuntimeRequiresInvoker0|Operacja wysyłania wymaga elementu Źródło.|  
|ServiceHasZeroAppEndpoints|Określona usługa nie ma punktów końcowych aplikacji (niezwiązanych z infrastrukturą). Może to być spowodowane tym, że nie znaleziono pliku konfiguracyjnego dla aplikacji lub nie znaleziono żadnego elementu usługi pasującego do nazwy usługi w pliku konfiguracji lub ponieważ nie zdefiniowano żadnych punktów końcowych w elemencie usługi.|  
|SFxActionMismatch|Nie można utworzyć komunikatu z typem z powodu niezgodności akcji. Oczekiwano określonej akcji, ale napotkano inną|  
|SFxAnonymousTypeNotSupported|Określonej części w określonym komunikacie nie można wyeksportować za pomocą wywołania RPC ani zakodować, ponieważ jej typ jest anonimowy.|  
|SFxBadMetadataLocationNoAppropriateBaseAddress|Adres URL podany do ServiceMetadataBehavior przy użyciu właściwości ExternalMetadataLocation lub atrybutu externalMetadataLocation w sekcji ServiceMetadata w sekcji Configuration był względnym adresem URL i nie ma adresu podstawowego, z którym można go rozpoznać.|  
|SFxBadMetadataMustBePolicy|Należy podać element XmlElement, który ma określoną przestrzeń nazw i nazwę. Ten element XmlElement ma określoną przestrzeń nazw i nazwę.|  
|SFxBodyObjectTypeCannotBeInherited|Określony typ nie może dziedziczyć z żadnej klasy innej niż obiekt, który ma być używany jako obiekt treści w stylu wywołania RPC.|  
|SFxBodyObjectTypeCannotBeInterface|Określony typ implementuje określony interfejs, który nie jest obsługiwany dla obiektu treści w stylu wywołania RPC.|  
|SFxCallbackBehaviorAttributeOnlyOnDuplex|CallbackBehaviorAttribute można uruchomić tylko jako zachowanie w punkcie końcowym z umową dupleksową. Określony kontrakt nie jest dupleksowy i nie zawiera żadnych operacji wywołania zwrotnego.|  
|SFxCallbackRequestReplyInOrder1|Nie można odebrać odpowiedzi z tej operacji, dopóki bieżący komunikat nie zostanie przetworzony. Jeśli chcesz zezwolić na przetwarzanie komunikatów poza kolejnością, określ wartość Concurrencytype lub wielokrotność dla określonego elementu.|  
|SfxCallbackTypeCannotBeNull|Aby można było użyć określonego kontraktu z obiektem DuplexChannelFactory, kontrakt musi określać prawidłowy kontrakt wywołania zwrotnego. Jeśli kontrakt ma kontrakt wywołania zwrotnego, użyj elementu ChannelFactory zamiast DuplexChannelFactory.|  
|SFxCannotGetMetadataFromLocation|Obiekt MetadataExchangeClient może uzyskać tylko metadane z MetadataLocations HTTP i HTTPS. Nie można pobrać metadanych z określonego.|  
|SFxCannotHttpGetMetadataFromAddress|Obiekt MetadataExchangeClient może uzyskać tylko metadane z adresów HTTP lub HTTPS, gdy jest używany obiekt MetadataExchangeClientmode narzędzia HttpGet. Nie można pobrać metadanych z określonego.|  
|SFxCannotImportAsParameters_Bare|Trwa generowanie kontraktu komunikatu, ponieważ określona operacja nie jest w wywołaniu RPC ani w dokumencie.|  
|SFxCannotImportAsParameters_DifferentWrapperName|Trwa generowanie kontraktu komunikatu, ponieważ nazwa otoki określonego komunikatu nie jest zgodna z wartością domyślną.|  
|SFxCannotImportAsParameters_DifferentWrapperNs|Trwa generowanie kontraktu komunikatu, ponieważ przestrzeń nazw otoki określonego komunikatu nie jest zgodna z wartością domyślną.|  
|SFxCannotImportAsParameters_ElementIsNotNillable|Trwa generowanie kontraktu komunikatu, ponieważ określona nazwa elementu z określonego obszaru nazw nie jest oznaczona jako nillable.|  
|SFxCannotImportAsParameters_HeadersAreUnsupported|Trwa generowanie kontraktu komunikatu, ponieważ określony komunikat ma nagłówki.|  
|SFxCannotImportAsParameters_Message|Trwa generowanie kontraktu komunikatu, ponieważ określona operacja zawiera komunikat nieokreślony jako argument lub zwracany typ.|  
|SFxCannotImportAsParameters_MessageHasProtectionLevel|Trwa generowanie kontraktu komunikatu, ponieważ określony komunikat wymaga ochrony.|  
|SFxCannotImportAsParameters_NamespaceMismatch|Trwa generowanie kontraktu komunikatu, ponieważ określona przestrzeń nazw części komunikatu nie jest zgodna z wartością domyślną.|  
|SFxCannotRequireBothSessionAndDatagram3|Określony kontrakt Określa element SessionMode. nołójd, a określony kontrakt Określa element SessionMode. Required. Zmień jedną z wartości SessionMode lub określ inny adres lub ListenURI dla każdego punktu końcowego.|  
|SFxCannotSetExtensionsByIndex|Ta kolekcja nie obsługuje ustawiania rozszerzeń według indeksu. Użyj metod InsertItem lub RemoveItem.|  
|SFxChannelDispatcherDifferentHost0|Element ChannelDispatcher nie jest obecnie dołączony do podanego ServiceHost.|  
|SFxChannelDispatcherMultipleHost0|Elementu ChannelDispatcher nie można dodać do więcej niż jednego elementu ServiceHost.|  
|SFxChannelDispatcherNoHost0|Nie można otworzyć elementu ChannelDispatcher, ponieważ nie jest on dołączony do ServiceHost.|  
|SfxChannelFactoryDisposed|Nie można otworzyć tego elementu ChannelFactory, ponieważ element ChannelFactory został już usunięty. Ponownie utwórz element ChannelFactory przed jego użyciem.|  
|SFxChannelFactoryNoBinding|Nie można otworzyć elementu ChannelFactory, ponieważ nie skojarzono żadnego powiązania z punktem końcowym. Określ powiązanie z konstruktorem lub właściwością Endpoint.|  
|SFxChannelTerminated0|Operacja oznaczona jako isterminate została już wywołana w tym kanale, co spowodowało przerwanie połączenia kanału. Nie można wywołać więcej operacji w tym kanale. Utwórz ponownie kanał, aby kontynuować komunikację.|  
|SFxCloseTimedOut1|Operacja zamknięcia ServiceHost została zatrzymana po określonym elemencie. Może to być spowodowane tym, że klient nie może zamknąć kanału sesji w wymaganym czasie. Czas dozwolony dla tej operacji mógł być częścią dłuższego limitu czasu.|  
|SfxCloseTimedOutWaitingForDispatchToComplete|Proces zamykania przekroczył limit czasu podczas oczekiwania na zakończenie wysyłania usługi.|  
|SFxCodeGenIsNotAssignableFrom|Nie można przypisać określonego.|  
|SFxConfigChannelConfigurationNotFound|Nie można znaleźć elementu punktu końcowego z określoną nazwą i umową w sekcji konfiguracji klienta ServiceModel.|  
|SFxConflictingGlobalElement|Element XML najwyższego poziomu o określonej nazwie w określonym obszarze nazw nie może odwoływać się do określonego typu. Odwołuje się już do innego typu. Użyj innej nazwy operacji lub MessageBodyAttribute, aby określić inną nazwę dla części wiadomości lub komunikatów.|  
|SFxContractHasZeroInitiatingOperations|Kontrakt musi zawierać co najmniej jedną operację IsInitiating = true.|  
|SFxContractHasZeroOperations|Kontrakt musi zawierać co najmniej jedną operację.|  
|SFxContractInheritanceRequiresInterfaces|Klasa usługi określonego typu definiuje element ServiceContract i dziedziczy go z określonego typu. Dziedziczenie kontraktu może być używane tylko między typami interfejsów. Jeśli klasa jest oznaczona przy użyciu atrybutu ServiceContractAttribute, musi być jedynym typem w hierarchii z atrybutem ServiceContractAttribute.  Przenieś atrybut ServiceContractAttribute określonego typu do oddzielnego interfejsu, który implementuje określony typ.|  
|SFxCreateDuplexChannel1|Kontrakt wywołania zwrotnego określonego kontraktu nie istnieje lub nie definiuje żadnych operacji. Jeśli nie jest to kontrakt dupleksowy, użyj elementu ChannelFactory zamiast DuplexChannelFactory.|  
|SFxCreateDuplexChannelNoCallback|Nie można wywołać tego przeciążenia CreateChannel w tym wystąpieniu elementu DuplexChannelFactory. Obiekt DuplexChannelFactory nie został zainicjowany przy użyciu elementu InstanceContext. Wywołaj Przeciążenie CreateChannel, które pobiera obiekt InstanceContext.|  
|SFxCreateDuplexChannelNoCallback1|Nie można wywołać tego przeciążenia CreateChannel w tym wystąpieniu elementu DuplexChannelFactory. Obiekt DuplexChannelFactory został zainicjowany z typem i nie podano prawidłowego elementu InstanceContext. Wywołaj Przeciążenie CreateChannel, które pobiera obiekt InstanceContext.|  
|SFxCreateDuplexChannelNoCallbackUserObject|Nie można wywołać tego przeciążenia CreateChannel w tym wystąpieniu elementu DuplexChannelFactory. Obiekt InstanceContext podany w kanale DuplexChannelFactory nie zawiera prawidłowego obiektu UserObject.|  
|SFxCreateNonDuplexChannel1|Obiekt ChannelFactory nie obsługuje określonego kontraktu. Element ChannelFactory definiuje kontrakt wywołania zwrotnego z co najmniej jedną operacją. Użyj obiektu DuplexChannelFactory zamiast elementu ChannelFactory.|  
|SFxCustomBindingNeedsTransport1|Niestandardowy elementbinding w punkcie końcowego z określonym kontraktem nie zawiera elementu TransportBindingElement. Każde powiązanie musi zawierać co najmniej jeden element powiązania pochodzący z elementu TransportBindingElement.|  
|SFxCustomBindingWithoutTransport|Nie można obliczyć schematu dla tego powiązania niestandardowego, ponieważ nie ma on elementu TransportBindingElement. Każde powiązanie musi zawierać co najmniej jeden element powiązania pochodzący z elementu TransportBindingElement.|  
|SFxDataContractSerializerDoesNotSupportBareArray|Obiekt DataContractSerializer nie obsługuje kolekcji określonej w określonym elemencie.|  
|SFxDictionaryIsEmpty|Nie można wykonać operacji, ponieważ słownik jest pusty.|  
|SFxDocEncodedNotSupported|Błąd odzwierciedlający określony. Document-Encoded nie jest obsługiwana. Zmień element "use" na Literal lub "Style" na RPC.|  
|SFxDuplicateInitiatingActionAtSameVia|Ta usługa ma wiele punktów końcowych nasłuchujących w określonym. Punkty końcowe mają tę samą określoną akcję inicjującą. Komunikaty z tą akcją zostałyby porzucone, ponieważ Dyspozytor nie będzie w stanie ustalić prawidłowego punktu końcowego do obsługi wiadomości.|  
|SFXEndpointBehaviorUsedOnWrongSide|Nie można użyć określonego interfejsu IEndpointBehavior na serwerze. To zachowanie może dotyczyć tylko klientów.|  
|SFxEndpointNoMatchingScheme|Nie można znaleźć adresu podstawowego pasującego do określonego schematu dla punktu końcowego z określonym powiązaniem. Określono zarejestrowane schematy adresów podstawowych.|  
|SFxErrorCreatingMtomReader|Wystąpił błąd podczas tworzenia czytnika dla komunikatu mechanizmu optymalizacji transmisji komunikatów.|  
|SFxErrorDeserializingFault|Serwer zwrócił błąd nieprawidłowego protokołu prostego dostępu do obiektów. Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxErrorDeserializingHeader|Wystąpił błąd podczas deserializacji jednego z nagłówków w określonym komunikacie. Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxErrorReflectingOnMethod3|Wystąpił błąd podczas ładowania określonego atrybutu w określonej metodzie w określonym typie.  Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxErrorReflectingOnParameter4|Wystąpił błąd podczas ładowania określonego atrybutu dla określonego parametru określonej metody w określonym typie. Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxErrorReflectingOnType2|Wystąpił błąd podczas ładowania określonego atrybutu dla określonego typu.  Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxErrorSerializingBody|Wystąpił błąd podczas serializowania treści podanej wiadomości. Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxErrorSerializingHeader|Wystąpił błąd podczas serializacji jednego z nagłówków w określonym komunikacie. Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxExpectedIMethodCallMessage|Błąd wewnętrzny. Komunikat musi być prawidłowym IMethodCallMessage.|  
|SFxExportMustHaveType|Nie można wyeksportować określonej części określonej operacji, ponieważ nie ma ona prawidłowego typu CLR.|  
|SFxHeaderNotUnderstood|Komunikat nie został przetworzony. Określony nagłówek z określonego obszaru nazw nie został zrozumiany przez odbiorcę tej wiadomości. Ten błąd zazwyczaj wskazuje, że nadawca tej wiadomości włączył protokół komunikacyjny, którego odbiorca nie może przetworzyć. Upewnij się, że konfiguracja powiązania klienta jest spójna z powiązaniem usługi.|  
|SFxHeadersAreNotSupportedInEncoded|Określony komunikat nie może mieć nagłówków, aby można było używać go w stylu zaszyfrowanego wywołania procedury zdalnej.|  
|SFxInconsistentWsdlOperationStyleInMessageParts|Wszystkie części komunikatu w określonej operacji muszą zawierać typ lub element.|  
|SFxInconsistentWsdlOperationStyleInOperationMessages|Określony styl wywnioskowany na podstawie komunikatów w określonej operacji nie jest zgodny z określonym oczekiwanym stylem określonym przy użyciu powiązań.|  
|SFxInvalidCallbackIAsyncResult|Nie podano parametru IAsyncResult lub jego typ jest nieprawidłowy.|  
|SFxInvalidMessageBody|Obiekt OperationFormatter napotkał nieprawidłową treść wiadomości. Oczekiwano typu węzła "element" z określoną nazwą i przestrzenią nazw. Znaleziono określony typ węzła z określoną nazwą i przestrzenią nazw.|  
|SFxInvalidMessageBodyEmptyMessage|Obiekt OperationFormatter nie może zdeserializować żadnych informacji z komunikatu, ponieważ komunikat jest pusty.|  
|SFxInvalidMessageBodyErrorDeserializingParameter|Wystąpił błąd podczas próby deserializacji określonego parametru. Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxInvalidMessageBodyErrorSerializingParameter|Wystąpił błąd podczas próby serializacji określonego parametru. Określono komunikat Wewnętrznyexception.  Aby uzyskać więcej informacji, zobacz wyjątek wewnętrzny.|  
|SFxInvalidMessageBodyUnexpectedNode|Napotkano określony nieoczekiwany węzeł z określonego obszaru nazw podczas deserializacji parametrów.|  
|SFxInvalidMessageContractSignature|Określona operacja ma parametr lub zwracany typ, który jest oznaczony atrybutem MessageContractAttribute. W przypadku używania kontraktu komunikatu do reprezentowania komunikatu żądania, operacja musi mieć pojedynczy parametr, który jest oznaczony atrybutem MessageContractAttribute. W przypadku używania kontraktu komunikatu do reprezentowania komunikatu odpowiedzi, wartość zwracana przez operację musi być typem, który jest oznaczony atrybutem MessageContractAttribute. Operacja nie może zawierać żadnych parametrów "out" lub "ref".|  
|SFxInvalidReplyAction|Komunikat odpowiedzi wychodzącej dla operacji ma określoną akcję, ale kontrakt dla tej operacji określa inny ReplyAction. Akcja określona w komunikacie musi być zgodna z ReplyAction w kontrakcie lub kontrakt operacji musi określać ReplyAction = "*".|  
|SFxInvalidRequestAction|Komunikat żądania wychodzącego dla operacji ma określoną akcję, ale kontrakt dla tej operacji określa inny RequestAction. Akcja określona w komunikacie musi być zgodna z RequestAction w kontrakcie lub kontrakt operacji musi określać RequestAction = "*".|  
|SFxInvalidStaticOverloadCalledForDuplexChannelFactory1|Nie można użyć statycznej metody CreateChannel z określonym kontraktem, ponieważ ten kontrakt definiuje kontrakt wywołania zwrotnego. Użyj jednego z statycznych przeciążeń CreateChannel na kanale DuplexChannelFactory \<TChannel> .|  
|SFxInvalidStreamInRequest|Aby żądanie w określonej operacji było strumieniem, operacja musi mieć pojedynczy parametr, którego typem jest Stream.|  
|SFxInvalidStreamInResponse|Aby odpowiedź w określonej operacji była strumieniem, operacja musi mieć pojedynczy parametr out lub wartość zwracaną typu Stream.|  
|SFxInvalidStreamInTypedMessage|Aby użyć strumieni z modelem programowania kontraktu wiadomości, określony typ musi mieć pojedynczy element członkowski MessageBody, którego typem jest Stream.|  
|SFxInvalidUseOfPrimitiveOperationFormatter|PrimitiveOperationFormatter podano parametr lub zwracany typ, który nie jest obsługiwany.|  
|SFxMessageContractBaseTypeNotValid|Określony typ definiuje element MessageContract i pochodzi z określonego typu, który nie definiuje elementu MessageContract. Wszystkie obiekty w określonej hierarchii dziedziczenia muszą definiować MessageContract.|  
|SFxMethodNotSupported1|Określona metoda nie jest obsługiwana dla tego obiektu. Może się tak zdarzyć, jeśli metoda nie jest oznaczona atrybutem OperationContractAttribute lub jeśli typ interfejsu nie jest oznaczony atrybutem ServiceContractAttribute.|  
|SFxMethodNotSupportedByType2|Określony typ implementacji ServiceHost nie implementuje określonego kontraktu usługi.|  
|SFxMethodNotSupportedOnCallback1|Określona metoda wywołania zwrotnego nie jest obsługiwana. Taka sytuacja może wystąpić, jeśli metoda nie jest oznaczona atrybutem OperationContractAttribute lub jeśli typ interfejsu nie jest obiektem docelowym elementu ServiceContractAttribute CallbackContract.|  
|SFxMismatchedOperationParent|Element element DispatchOperation lub ClientOperation może zostać dodany tylko do jego elementu nadrzędnego DispatchRuntime lub ClientRuntime.|  
|SFxNameCannotBeEmpty|Właściwość Name nie może być pustym ciągiem.|  
|SfxNoTypeSpecifiedForParameter|Nie określono typu CLR dla parametru, co uniemożliwia wygenerowanie operacji.|  
|SFxOperationBehaviorAttributeOnlyOnServiceClass|OperationBehaviorAttribute będący może przejść tylko do klasy usługi. Nie można go umieścić w interfejsie ServiceContract. Określona metoda dla określonego typu narusza ten sposób.|  
|SFxOperationContractOnNonServiceContract|Określona metoda jest oznaczona atrybutem OperationContractAttribute, ale otaczający określony typ nie jest oznaczony atrybutem ServiceContractAttribute. Atrybut OperationContractAttribute może być używany tylko w przypadku metod w typach ServiceContractAttribute lub w ich typach CallbackContract.|  
|SFxParameterCountMismatch|Wystąpił niezgodność między liczbą podanych argumentów i liczbą oczekiwanych argumentów. Określony argument ma określoną liczbę elementów, podczas gdy oczekiwany argument ma określoną liczbę elementów.|  
|SFxPartNameMustBeUniqueInRpc|Określona nazwa części komunikatu nie jest unikatowa w komunikacie zdalnego wywołania procedury.|  
|SFxReplyActionMismatch3|Odebrano komunikat odpowiedzi dla określonej operacji z określoną akcją. Jednak kod klienta wymaga określonej akcji.|  
|SFxRequestReplyNone|Odebrano komunikat z nagłówkiem WS-Addressing ReplyTo lub FaultTo wskazywanym jako adres "none". Te wartości nie są prawidłowe dla operacji żądanie-odpowiedź. Użyj operacji jednokierunkowej lub Włącz funkcję ManualAddressing, jeśli potrzebujesz obsługi ReplyTo lub FaultTo wartości "none".|  
|SFxRequestTimedOut1|Ta operacja żądania nie otrzymała odpowiedzi w określonym skonfigurowanym czasie. Dozwolony czas może być częścią dłuższego limitu czasu. Może to być spowodowane tym, że usługa nadal przetwarza operację lub usługa nie mogła wysłać komunikatu odpowiedzi.|  
|SFxRequestTimedOut2|Operacja żądania wysłana do określonej lokalizacji nie otrzymała odpowiedzi w określonym skonfigurowanym czasie. Dozwolony czas może być częścią dłuższego limitu czasu. Może to być spowodowane tym, że usługa nadal przetwarza operację lub usługa nie mogła wysłać komunikatu odpowiedzi.|  
|SFxSchemaDoesNotContainType|Schemat z określoną docelową przestrzenią nazw nie zawiera typu o określonej nazwie.|  
|SfxServiceContractAttributeNotFound|Określony typ kontraktu nie ma atrybutu ServiceContractAttribute. Aby zdefiniować prawidłowy kontrakt, określony typ musi mieć atrybut ServiceContractAttribute. Typ może być interfejsem kontraktu lub klasą usługi.|  
|SFxServiceContractGeneratorConfigRequired|Aby wygenerować informacje o konfiguracji przy użyciu metody GenerateServiceEndpoint, wystąpienie ServiceContractGenerator musi zostać zainicjowane z prawidłowym obiektem konfiguracji.|  
|SFxServiceHostBaseCannotAddEndpointAfterOpen|Nie można dodać punktów końcowych, gdy element ServiceHost ma jeden z następujących stanów:<br /><br /> -Otwarte<br />-Błąd<br />— Zakończono<br />-Zamknięte|  
|SFxServiceHostBaseCannotAddEndpointWithoutDescription|Nie można dodać punktów końcowych przed zainicjowaniem właściwości Description.|  
|SFxServiceMetadataBehaviorNoHttpBaseAddress|Właściwość HttpGetEnabled ServiceMetadataBehavior ma wartość true, a właściwość HttpGetUrl jest adresem względnym, ale nie ma podstawowego adresu HTTP. Podaj adres podstawowy HTTP lub ustaw HttpGetUrl na adres bezwzględny.|  
|SFxServiceMetadataBehaviorNoHttpsBaseAddress|Właściwość HttpsGetEnabled ServiceMetadataBehavior ma wartość true, a właściwość HttpsGetUrl jest adresem względnym, ale nie ma adresu podstawowego HTTPS. Podaj adres podstawowy HTTPS lub Ustaw HttpsGetUrl na adres bezwzględny.|  
|SFxServiceMetadataBehaviorUrlMustBeHttpOrRelative|Adres URL zachowania musi być względnym identyfikatorem zasobu lub bezwzględnym identyfikatorem zasobu z określonym schematem. Określony adres URL jest bezwzględnym identyfikatorem zasobu z określonym schematem.|  
|SFxStreamRequestMessageClosed|Komunikat zawierający ten strumień został zamknięty. Nie można uzyskać dostępu do strumieni żądań po powrocie operacji usługi.|  
|SFxStreamResponseMessageClosed|Komunikat zawierający ten strumień został zamknięty.|  
|SFxTerminateRequestProcessingException|Rozszerzenie w potoku operacji musi zakończyć przetwarzanie tej wiadomości.|  
|SFxTerminatingOperationAlreadyCalled1|Ten kanał nie może wysłać więcej komunikatów, ponieważ operacja IsTerminating została wywołana.|  
|SFxThrottleLimitMustBeGreaterThanZero0|Limit ograniczania musi być większy od zera. Aby wyłączyć limit ograniczania przepustowości, ustaw wartość na Int32. MaxValue.|  
|SFxTypedOrUntypedMessageCannotBeMixedWithVoidInRpc|W przypadku używania stylu RPC-Encoded typy kontraktu komunikatu lub typ System. ServiceModel. Channels. Message nie mogą być używane, jeśli operacja nie ma parametrów lub ma pustą wartość zwracaną. Dodaj pusty typ kontraktu wiadomości jako parametr lub typ zwracany do określonej operacji.|  
|SFxUserCodeThrewException|Określona operacja użytkownika zgłosiła wyjątek, który jest nieobsługiwany w kodzie użytkownika. Jeśli jest to problem cykliczny, może to wskazywać na błąd w implementacji określonej metody.|  
|SfxUseTypedMessageForCustomAttributes|Określony parametr nie może zostać zmapowany do parametru operacji, ponieważ wymaga dodatkowych atrybutów.|  
|SFxVersionMismatchInOperationContextAndMessage2|Nie można dodać nagłówków wychodzących do komunikatu, ponieważ element MessageVersion w elemencie OperationContext. Current nie jest zgodny z wersją nagłówka przetwarzanego komunikatu|  
|SFxWellKnownNonSingleton0|Aby użyć jednego z konstruktorów ServiceHost, które Pobiera wystąpienie usługi, właściwość InstanceContextmode usługi musi być ustawiona na InstanceContextmode. Single. Można to skonfigurować przy użyciu ServiceBehaviorAttribute. W przeciwnym razie użyj konstruktorów ServiceHost, które przyjmują argument typu.|  
|SFxWrapperTypeHasMultipleNamespaces|Typ otoki dla określonego komunikatu nie może być rzutowany jako typ kontraktu danych, ponieważ ma wiele przestrzeni nazw. Użyj elementu XmlSerializer.|  
|UriMustBeAbsolute|Identyfikator URI musi być bezwzględny.|
