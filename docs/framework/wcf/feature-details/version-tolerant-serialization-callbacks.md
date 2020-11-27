---
title: Wywołania zwrotne serializacji z tolerancją dla wersji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
ms.openlocfilehash: ad162f24042f30eabee7a1fad2025072b26d9af5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289376"
---
# <a name="version-tolerant-serialization-callbacks"></a>Wywołania zwrotne serializacji z tolerancją dla wersji

Model programowania kontraktu danych w pełni obsługuje metody wywołania zwrotnego serializacji odporne na wersje, które <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> obsługują klasy i.  
  
## <a name="version-tolerant-attributes"></a>Atrybuty Version-Tolerant  

 Istnieją cztery atrybuty wywołania zwrotnego. Każdy atrybut może być stosowany do metody, którą aparat serializacji/deserializacji wywołuje w różnym czasie. W poniższej tabeli objaśniono, kiedy używać każdego atrybutu.  
  
|Atrybut|Po wywołaniu odpowiedniej metody|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|Wywołuje się przed serializowaniem typu.|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|Wywołuje się po serializacji typu.|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|Wywołuje się przed deserializacji typu.|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|Wywołuje się po deserializacji typu.|  
  
 Metody muszą akceptować <xref:System.Runtime.Serialization.StreamingContext> parametr.  
  
 Te metody są przeznaczone głównie do użytku z wersjami lub inicjalizacją. Podczas deserializacji nie są wywoływane konstruktory. W związku z tym elementy członkowskie danych mogą nie być prawidłowo zainicjowane (do zamierzonych wartości domyślnych), jeśli w strumieniu przychodzącym brakuje danych dla tych elementów członkowskich, na przykład jeśli dane pochodzą z poprzedniej wersji typu, w którym brakuje niektórych elementów członkowskich danych. Aby rozwiązać ten wynik, użyj metody wywołania zwrotnego oznaczonej przy użyciu <xref:System.Runtime.Serialization.OnDeserializingAttribute> , jak pokazano w poniższym przykładzie.  
  
 Można oznaczyć tylko jedną metodę na typ z każdym z powyższych atrybutów wywołania zwrotnego.  
  
### <a name="example"></a>Przykład  

 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- [Serializacja z tolerancją wersji](../../../standard/serialization/version-tolerant-serialization.md)
