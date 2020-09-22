---
title: Literał CDATA XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 4447ad6cf0fb251b0d2d1387c109b06d32f69cb8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866095"
---
# <a name="xml-cdata-literal-visual-basic"></a>Literał CDATA XML (Visual Basic)

Literał reprezentujący <xref:System.Xml.Linq.XCData> obiekt.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Części  

 `<![CDATA[`  
 Wymagany. Wskazuje początek sekcji CDATA XML.  
  
 `content`  
 Wymagany. Zawartość tekstowa do wyświetlenia w sekcji CDATA XML.  
  
 `]]>`  
 Wymagany. Oznacza koniec sekcji.  
  
## <a name="return-value"></a>Wartość zwracana  

 Obiekt <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Uwagi  

 Sekcje CDATA XML zawierają nieprzetworzony tekst, który powinien być uwzględniony, ale nie jest analizowany, z XML, który zawiera. Sekcja CDATA XML może zawierać dowolny tekst. Obejmuje to zastrzeżone znaki XML. Sekcja CDATA XML zostanie zakończona z sekwencją "]] >". Oznacza to następujące kwestie:  
  
- Nie można użyć wyrażenia osadzonego w literale CDATA XML, ponieważ ogranicznik wyrażenia osadzonego są prawidłową zawartością elementu XML CDATA.  
  
- Sekcje CDATA XML nie mogą być zagnieżdżane, ponieważ `content` nie mogą zawierać wartości "]] >".  
  
 Do zmiennej można przypisać literał XML CDATA lub dodać go do literału elementu XML.  
  
> [!NOTE]
> Literał XML może obejmować wiele wierszy, ale nie używa znaków kontynuacji wiersza. Dzięki temu można skopiować zawartość z dokumentu XML i wkleić ją bezpośrednio do programu Visual Basic.  
  
 Kompilator Visual Basic konwertuje literał XML CDATA na wywołanie <xref:System.Xml.Linq.XCData.%23ctor%2A> konstruktora.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład tworzy sekcję CDATA, która zawiera tekst "może zawierać Tagi literału \<XML> ".  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.Linq.XCData>
- [Literał elementu XML](xml-element-literal.md)
- [Literały XML](index.md)
- [Tworzenie XML w Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
