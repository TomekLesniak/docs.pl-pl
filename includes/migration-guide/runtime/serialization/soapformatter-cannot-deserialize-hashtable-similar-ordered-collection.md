---
ms.openlocfilehash: 71cc7119710a2b381626dd9cf4ab66265eb3deba
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496755"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>SoapFormatter nie może rozszeregować obiektów Hashtable i podobnej kolejności kolekcji

#### <a name="details"></a>Szczegóły

Program nie <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> gwarantuje, że Serializacja obiektów w jednej wersji .NET Framework zostanie pomyślnie rozszeregowana w ramach innej wersji. W przypadku niektórych uporządkowanych kolekcji (takich jak <xref:System.Collections.Hashtable?displayProperty=fullName> ) dodano członków między 4,0 i 4,5 takich, że obiekty tych typów nie mogą deserializować z .NET Framework 4,0, jeśli zostały zserializowane z .NET Framework 4,5. Należy pamiętać, że jeśli serializowane dane są serializowane i deserializowane z tą samą wersją .NET Framework, żaden problem nie wystąpi.

#### <a name="suggestion"></a>Sugestia

<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> Serializacja powinna zostać zastąpiona <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serializacją lub <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> być odporna na zmiany .NET Framework.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
