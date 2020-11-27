---
title: Odwołania do elementu ServiceDescription i kodu WSDL
ms.date: 03/30/2017
ms.assetid: eedc025d-abd9-46b1-bf3b-61d2d5c95fd6
ms.openlocfilehash: 11a5d65026d13db56d1d349c130861094c3e123b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253885"
---
# <a name="servicedescription-and-wsdl-reference"></a>Odwołania do elementu ServiceDescription i kodu WSDL

W tym temacie opisano sposób, w jaki Windows Communication Foundation (WCF) mapuje dokumenty Web Services Description Language (WSDL) do i z <xref:System.ServiceModel.Description.ServiceDescription> wystąpień.  
  
## <a name="how-servicedescription-maps-to-wsdl-11"></a>Jak element ServiceDescription mapuje do języka WSDL 1,1  

 Za pomocą programu WCF można eksportować dokumenty WSDL z <xref:System.ServiceModel.Description.ServiceDescription> wystąpienia usługi. Dokumenty WSDL są generowane automatycznie dla usługi podczas publikowania punktów końcowych metadanych.  
  
 Możesz również zaimportować <xref:System.ServiceModel.Description.ServiceEndpoint> wystąpienia, <xref:System.ServiceModel.Description.ContractDescription> wystąpienia i <xref:System.ServiceModel.Channels.Binding> wystąpienia z dokumentów WSDL przy użyciu `WsdlImporter` typu.  
  
 Dokumenty WSDL, eksportowane przez WCF, zaimportuj wszystkie definicje schematu XML używane z zewnętrznych dokumentów schematu XML. Oddzielny dokument schematu XML jest eksportowany dla każdej docelowej przestrzeni nazw używanej przez typy danych w usłudze. Analogicznie, oddzielny dokument WSDL jest eksportowany dla każdej docelowej przestrzeni nazw używanej przez kontrakty usługi.  
  
### <a name="servicedescription"></a>ServiceDescription  

 <xref:System.ServiceModel.Description.ServiceDescription>Wystąpienie jest mapowane na `wsdl:service` element. <xref:System.ServiceModel.Description.ServiceDescription>Wystąpienie zawiera kolekcję <xref:System.ServiceModel.Description.ServiceEndpoint> wystąpień, które są mapowane do poszczególnych `wsdl:port` elementów.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:service` /@name Wartość dla usługi.|  
|`Namespace`|Przestrzeń nazw dla `wsdl:service` definicji usługi.|  
|`Endpoints`|`wsdl:port`Definicje dla usługi.|  
  
### <a name="serviceendpoint"></a>ServiceEndpoint  

 <xref:System.ServiceModel.Description.ServiceEndpoint>Wystąpienie jest mapowane na `wsdl:port` element. <xref:System.ServiceModel.Description.ServiceEndpoint>Wystąpienie zawiera adres, powiązanie i kontrakt.  
  
 Zachowania punktów końcowych, które implementują <xref:System.ServiceModel.Description.IWsdlExportExtension> interfejs, mogą zmodyfikować `wsdl:port` element dla punktu końcowego, do którego są dołączone.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:port` /@name Wartość punktu końcowego i `wsdl:binding` /@name wartość dla powiązania punktu końcowego.|  
|`Address`|Adres `wsdl:port` definicji punktu końcowego.<br /><br /> Transport dla punktu końcowego określa format adresu. Na przykład w przypadku transportów obsługiwanych przez funkcję WCF może to być adres protokołu SOAP lub odwołanie do punktu końcowego.|  
|`Binding`|`wsdl:binding`Definicja punktu końcowego.<br /><br /> W przeciwieństwie `wsdl:binding` do definicji powiązania w programie WCF nie są powiązane z żadną umową.|  
|`Contract`|`wsdl:portType`Definicja punktu końcowego.|  
|`Behaviors`|Zachowania punktu końcowego, które implementują <xref:System.ServiceModel.Description.IWsdlExportExtension> interfejs, mogą modyfikować `wsdl:port` dla punktu końcowego.|  
  
### <a name="bindings"></a>Powiązania  

 Wystąpienie powiązania dla wystąpienia jest `ServiceEndpoint` mapowane na `wsdl:binding` definicję. W przeciwieństwie do `wsdl:binding` definicji, które muszą być skojarzone z określoną `wsdl:portType` definicją, powiązania WCF są niezależne od umowy.  
  
 Powiązanie składa się z kolekcji elementów powiązania. Każdy element opisuje pewne aspekty, w jaki punkt końcowy komunikuje się z klientami. Ponadto powiązanie ma <xref:System.ServiceModel.Channels.MessageVersion> wskazujące <xref:System.ServiceModel.EnvelopeVersion> i <xref:System.ServiceModel.Channels.AddressingVersion> dla punktu końcowego.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`Name`|Używane w domyślnej nazwie punktu końcowego, który jest nazwą powiązania z nazwą kontraktu dołączoną przez znak podkreślenia.|  
|`Namespace`|`targetNamespace`Dla `wsdl:binding` definicji.<br /><br /> Po zaimportowaniu, jeśli zasady są dołączone do portu WSDL, zaimportowana przestrzeń nazw powiązania jest mapowana na `targetNamespace` dla `wsdl:port` definicji.|  
|`BindingElementCollection`, w wyniku zwrócenia przez `CreateBindingElements` metodę ()|Różne rozszerzenia specyficzne dla domeny do `wsdl:binding` definicji, zazwyczaj potwierdzenia zasad.|  
|`MessageVersion`|`EnvelopeVersion`I `AddressingVersion` dla punktu końcowego.<br /><br /> Gdy `MessageVersion.None` jest określony, powiązanie WSDL nie zawiera powiązania SOAP, a port WSDL nie zawiera WS-Addressing Content. To ustawienie jest zwykle używane w przypadku zwykłych, starych punktów końcowych XML (POX).|  
  
#### <a name="bindingelements"></a>BindingElements  

 Elementy powiązania dla powiązania punktu końcowego są mapowane na różne rozszerzenia WSDL w programie `wsdl:binding` , takie jak potwierdzenia zasad.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement>Dla powiązania określa Uniform Resource Identifier transportu (URI) dla powiązania protokołu SOAP.  
  
#### <a name="addressingversion"></a>AddressingVersion  

 `AddressingVersion`W ramach powiązania są mapowane na wersję adresowania używaną w programie `wsd:port` . Program WCF obsługuje adresy SOAP 1,1 i SOAP 1,2 oraz WS-Addressing 08/2004 i WS-Addressing punktów końcowych 1,0.  
  
#### <a name="envelopeversion"></a>EnvelopeVersion  

 `EnvelopeVersion`W ramach powiązania są mapowane na wersję protokołu SOAP używaną w programie `wsdl:binding` . Usługa WCF obsługuje powiązania SOAP 1,1 i SOAP 1,2.  
  
### <a name="contracts"></a>Kontrakty  

 <xref:System.ServiceModel.Description.ContractDescription>Wystąpienie dla wystąpienia jest `ServiceEndpoint` mapowane na `wsdl:portType` . `ContractDescription`Wystąpienie opisuje wszystkie operacje dla danego kontraktu.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:portType` /@name Wartość dla kontraktu.|  
|`Namespace`|Przestrzeń nazw dla `wsdl:portType` definicji.|  
|`SessionMode`|`wsdl:portType` /@msc:usingSession Wartość dla kontraktu. Ten atrybut jest rozszerzeniem WCF dla języka WSDL 1,1.|  
|`Operations`|`wsdl:operation`Definicje kontraktu.|  
  
### <a name="operations"></a>Operacje  

 <xref:System.ServiceModel.Description.OperationDescription>Wystąpienie jest mapowane na `wsdl:portType` / `wsdl:operation` . `OperationDescription`Zawiera kolekcję `MessageDescription` wystąpień opisujących komunikaty dla operacji.  
  
 Dwa zachowania operacji często uczestniczyły w sposobie `OperationDescription` mapowania do dokumentu WSDL: `DataContractSerializerOperationBehavior` i `XmlSerializerOperationBehavior` .  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:portType` / `wsdl:operation` /@name Wartość dla operacji.|  
|`ProtectionLevel`|Potwierdzenia ochrony w zasadach zabezpieczeń dołączone do `wsdl:binding/wsdl:operation` komunikatów dla tej operacji.|  
|`IsInitiating`|`wsdl:portType` / `wsdl:operation` /@msc:isInitiating Wartość dla operacji. Ten atrybut jest rozszerzeniem WCF dla języka WSDL 1,1.|  
|`IsTerminating`|`wsdl:portType` / `wsdl:operation` /@msc:isTerminating Wartość dla operacji. Ten atrybut jest rozszerzeniem WCF dla języka WSDL 1,1.|  
|`Messages`|`wsdl:portType` / `wsdl:operation` / `wsdl:input` Wiadomości i `wsdl:portType` / `wsdl:operation` / `wsdl:output` dla operacji.|  
|`Faults`|`wsdl:portType` / `wsdl:operation` / `wsdl:fault` Definicje operacji.|  
|`Behaviors`|`DataContractSerializerOperationBehavior`I `XmlSerializerOperationBehavior` dotyczy powiązań operacji i komunikatów operacji.|  
  
#### <a name="the-datacontractserializeroperationbehavior"></a>DataContractSerializerOperationBehavior  

 `DataContractSerializerOperationBehavior`Dla operacji jest `IWsdlExportExtension` implementacją, która eksportuje komunikaty WSDL i powiązania dla tej operacji. Typy schematu XML są eksportowane przy użyciu `XsdDataContractExporter` . `DataContractSerializerOperationBehavior`Określa również sposób użycia, stylu i eksportu schematu oraz importera, który ma być używany dla tej operacji.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`DataContractFormatAttribute`|`Style`Właściwość tego atrybutu jest mapowana na `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style wartość dla operacji.<br /><br /> `DataContractSerializerOperationBehavior`Obsługuje tylko literały użycia typów schematu w języku WSDL.|  
  
#### <a name="the-xmlserializeroperationbehavior"></a>XmlSerializerOperationBehavior  

 `XmlSerializerOperationBehavior`Dla operacji jest `IWsdlExportExtension` implementacją, która eksportuje komunikaty WSDL i powiązania dla tej operacji. Typy schematu XML są eksportowane przy użyciu `XmlSchemaExporter` . `XmlSerializerOperationBehavior`Określa również sposób użycia, stylu i eksportu schematu oraz importera, który ma być używany dla tej operacji.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`XmlSerializerFormatAttribute`|`Style`Właściwość tego atrybutu jest mapowana na `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style wartość dla operacji.<br /><br /> `Use`Właściwość tego atrybutu jest mapowana na `wsdl:binding` / `wsdl:operation` / `soap:operation` wartości/* /@use dla wszystkich komunikatów w operacji.|  
  
### <a name="messages"></a>Komunikaty  

 `MessageDescription`Wystąpienie mapuje do `wsdl:message` , do którego odwołuje się `wsdl:portType` / `wsdl:operation` / `wsdl:input` lub `wsdl:portType` / `wsdl:operation` / `wsdl:output` komunikat w operacji. `MessageDescription`Ma treść i nagłówki.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`Action`|Akcja SOAP lub WS-Addressing dla wiadomości.<br /><br /> Należy zauważyć, że operacje, które używają ciągu akcji "*", nie są reprezentowane w języku WSDL.|  
|`Direction`|`MessageDirection.Input` mapuje do `wsdl:input` .<br /><br /> `MessageDirection.Output` mapuje do `wsdl:output` .|  
|`ProtectionLevel`|Potwierdzenia ochrony w zasadach zabezpieczeń dołączone do `wsdl:message` definicji dla tej wiadomości.|  
|`Body`|Treść komunikatu.|  
|`Headers`|Nagłówki wiadomości.|  
|`ContractDescription.Name`, `OperationContract.Name`|Przy eksporcie używany do uzyskania `wsdl:message` /@name wartości.|  
  
#### <a name="message-body"></a>Treść komunikatu  

 `MessageBodyDescription`Wystąpienie jest mapowane na `wsdl:message` / `wsdl:part` definicje treści wiadomości. Treść komunikatu może być opakowana lub bez systemu operacyjnego.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`WrapperName`|Jeśli styl nie jest wywoływany jako RPC, `WrapperName` mapuje do nazwy elementu, do którego odwołuje się element `wsdl:message` / `wsdl:part` with o @name wartości "Parameters".|  
|`WrapperNamespace`|Jeśli styl nie jest wywoływany jako RPC, `WrapperNamespace` mapuje do przestrzeni nazw elementów dla elementu `wsdl:message` / `wsdl:part` with o @name wartości "Parameters".|  
|`Parts`|Części wiadomości dla tej treści wiadomości.|  
|`ReturnValue`|Element podrzędny elementu otoki, jeśli istnieje element otoki (styl opakowany dokument lub styl wywołania RPC), w przeciwnym razie pierwszy `wsdl:message` / `wsdl:part` w komunikacie.|  
  
#### <a name="message-parts"></a>Części komunikatów  

 `MessagePartDescription`Wystąpienie jest mapowane na `wsdl:message` / `wsdl:part` i typ schematu XML lub element, do którego część wiadomości wskazuje.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`Name`|`wsd:message` / `wsdl:part` /@name Wartość części wiadomości i nazwa elementu wskazywanego przez część komunikatu.|  
|`Namespace`|Przestrzeń nazw elementu, do którego wskazuje część komunikatu.|  
|`Index`|Indeks `wsdl:message` / `wsdl:part` dla wiadomości.|  
|`ProtectionLevel`|Potwierdzenia ochrony w zasadach zabezpieczeń dołączone do `wsdl:message` definicji dla tej części wiadomości. Zasady są sparametryzowane, aby wskazywały konkretną część wiadomości.|  
|`MessageType`|Typ schematu XML elementu, do którego wskazuje część komunikatu.|  
  
#### <a name="message-headers"></a>Nagłówki komunikatów  

 `MessageHeaderDescription`Wystąpienie jest częścią komunikatu, która również jest mapowana na `soap:header` powiązanie dla części wiadomości.  
  
### <a name="faults"></a>Błędy  

 `FaultDescription`Wystąpienie jest mapowane do `wsdl:portType` / `wsdl:operation` / `wsdl:fault` definicji i skojarzonej `wsdl:message` definicji. `wsdl:message`Element jest dodawany do tej samej docelowej przestrzeni nazw, co skojarzony z nim typ portu WSDL. `wsdl:message`Zawiera pojedynczy komunikat o nazwie "Detail" wskazujący element schematu XML, który odpowiada `DefaultType` wartości właściwości dla tego `FaultDescription` wystąpienia.  
  
|Właściwości|Mapowanie WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:portType` / `wsdl:operation` / `wsdl:fault` /@name Wartość błędu.|  
|`Namespace`|Przestrzeń nazw elementu schematu XML, do którego odwołuje się część komunikatu szczegóły błędu.|  
|`Action`|Akcja SOAP lub WS-Addressing dla błędu.|  
|`ProtectionLevel`|Potwierdzenia ochrony w zasadach zabezpieczeń dołączone do `wsdl:message` definicji tego błędu.|  
|`DetailType`|Typ schematu XML elementu, do którego wskazuje część komunikatu szczegółowego.|  
|`Name, ContractDescription.Name, OperationDescription.Name,`|Służy do uzyskania `wsdl:message` /@name wartości dla komunikatu o błędzie.|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description>
