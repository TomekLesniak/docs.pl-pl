---
title: Literał instrukcji przetwarzającej kod XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3d18e58cb643fa075f6eb08eb6fe909d27a6737b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866394"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Literał instrukcji przetwarzającej kod XML (Visual Basic)

Literał reprezentujący <xref:System.Xml.Linq.XProcessingInstruction> obiekt.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Części  

 `<?`  
 Wymagany. Wskazuje początek literału instrukcji przetwarzania XML.  
  
 `piName`  
 Wymagany. Nazwa wskazująca, która aplikacja jest celem instrukcji przetwarzania. Nie można rozpocząć od "XML" lub "XML".  
  
 `piData`  
 Opcjonalny. Ciąg wskazujący sposób przetwarzania dokumentu XML przez aplikację, do której `piName` należy aplikacja.  
  
 `?>`  
 Wymagany. Oznacza koniec instrukcji przetwarzania.  
  
## <a name="return-value"></a>Wartość zwracana  

 Obiekt <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Uwagi  

 Literały instrukcji przetwarzania XML wskazują, w jaki sposób aplikacje powinny przetwarzać dokument XML. Gdy aplikacja ładuje dokument XML, aplikacja może sprawdzić instrukcje przetwarzania XML, aby określić sposób przetwarzania dokumentu. Aplikacja interpretuje znaczenie `piName` i `piData` .  
  
 Literał dokumentu XML używa składni podobnej do tej instrukcji przetwarzania XML. Aby uzyskać więcej informacji, zobacz [literał dokumentu XML](xml-document-literal.md).  
  
> [!NOTE]
> `piName`Element nie może rozpoczynać się od ciągu "XML" lub "XML", ponieważ Specyfikacja xml 1,0 rezerwuje te identyfikatory.  
  
 Do zmiennej można przypisać literał instrukcji przetwarzania XML lub dodać go do literału dokumentu XML.  
  
> [!NOTE]
> Literał XML może obejmować wiele wierszy bez znaków kontynuacji wiersza. Dzięki temu można skopiować zawartość z dokumentu XML i wkleić ją bezpośrednio do programu Visual Basic.  
  
 Kompilator Visual Basic konwertuje literał instrukcji przetwarzania XML na wywołanie <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> konstruktora.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład tworzy instrukcję przetwarzania identyfikującą arkusz stylów dla dokumentu XML.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.Linq.XProcessingInstruction>
- [Literał dokumentu XML](xml-document-literal.md)
- [Literały XML](index.md)
- [Tworzenie XML w Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
