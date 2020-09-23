---
title: 'Porady: dostęp do elementów podrzędnych XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: dcbaf1f9022d86f40a90ef6a1e0033f627caeef2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058212"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Porady: dostęp do elementów podrzędnych XML (Visual Basic)

Ten przykład pokazuje, jak używać właściwości osi elementu podrzędnego w celu uzyskania dostępu do wszystkich elementów XML, które mają określoną nazwę i które są zawarte w elemencie XML. W szczególności używa `Value` właściwości, aby pobrać wartość pierwszego elementu w kolekcji, która `name` zwraca właściwość osi elementu podrzędnego. `name`Właściwość osi elementu podrzędnego pobiera wszystkie elementy o nazwie `name` , które są zawarte w `contacts` obiekcie. W tym przykładzie jest również stosowana `phone` Właściwość osi elementu podrzędnego, aby uzyskać dostęp do wszystkich elementów podrzędnych o nazwie `phone` , które są zawarte w `contacts` obiekcie.  
  
## <a name="example"></a>Przykład  

 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a>Kompiluj kod  

 Ten przykład wymaga:  
  
- Odwołanie do <xref:System.Xml.Linq> przestrzeni nazw.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [Właściwości osi obiektu podrzędnego XML](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [Właściwość wartości XML](../../../language-reference/xml-axis/xml-value-property.md)
- [Uzyskiwanie dostępu do XML w Visual Basic](accessing-xml.md)
- [XML](index.md)
