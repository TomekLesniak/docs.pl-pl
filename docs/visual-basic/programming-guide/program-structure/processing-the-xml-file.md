---
title: Przetwarzanie pliku XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 9e12f6f5d86957a7f9aaea6047a79957fac8ce1e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072135"
---
# <a name="processing-the-xml-file-visual-basic"></a>Przetwarzanie pliku XML (Visual Basic)

Kompilator generuje ciąg identyfikatora dla każdej konstrukcji w kodzie, który jest oznaczony do generowania dokumentacji. (Aby uzyskać informacje na temat znakowania kodu, zobacz [Tagi komentarza XML](../../language-reference/xmldoc/index.md)). Ciąg identyfikatora jednoznacznie identyfikuje konstrukcję. Programy, które przetwarzają plik XML, mogą używać ciągu identyfikatora do identyfikowania odpowiednich .NET Framework metadanych/elementu odbicia.  
  
 Plik XML nie jest hierarchiczną reprezentacją kodu; jest to płaska lista z wygenerowanym IDENTYFIKATORem dla każdego elementu.  
  
 Podczas generowania ciągów identyfikatorów kompilator przestrzega następujących reguł:  
  
- Brak białego znaku w ciągu.  
  
- Pierwsza część ciągu identyfikatora identyfikuje rodzaj identyfikowanego elementu członkowskiego z pojedynczym znakiem, po którym następuje dwukropek. Używane są następujące typy elementów członkowskich.  
  
|Znak|Opis|  
|---|---|  
|N|namespace<br /><br /> Nie można dodać komentarzy do dokumentacji do przestrzeni nazw, ale możesz wprowadzić do nich odwołania CREF, jeśli są obsługiwane.|  
|T|Typ: `Class` , `Module` ,,, `Interface` `Structure` `Enum` , `Delegate`|  
|F|polami `Dim`|  
|P|Właściwość: `Property` (łącznie z właściwościami domyślnymi)|  
|M|Metoda: `Sub` , `Function` , `Declare` , `Operator`|  
|E|wydarzen `Event`|  
|!|ciąg błędu<br /><br /> Pozostała część ciągu zawiera informacje o błędzie. Kompilator Visual Basic generuje informacje o błędach dla linków, których nie można rozpoznać.|  
  
- Druga część `String` to w pełni kwalifikowana nazwa elementu, rozpoczynając od elementu głównego przestrzeni nazw. Nazwa elementu, jego typy otaczające i przestrzeń nazw są oddzielone kropkami. Jeśli nazwa samego elementu zawiera okresy, są one zastępowane znakiem numeru (#). Przyjęto założenie, że żaden element nie ma znaku cyfry bezpośrednio w nazwie. Na przykład w pełni kwalifikowana nazwa `String` konstruktora będzie `System.String.#ctor` .  
  
- W przypadku właściwości i metod, jeśli istnieją argumenty metody, lista argumentów ujęta w nawiasy. Jeśli nie ma żadnych argumentów, nie ma nawiasów. Argumenty są rozdzielone przecinkami. Kodowanie każdego argumentu następuje bezpośrednio po zakodowaniu w sygnaturze .NET Framework.  
  
## <a name="example"></a>Przykład  

 Poniższy kod pokazuje, jak generowane są ciągi identyfikatorów dla klasy i jej elementów członkowskich.  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>Zobacz także

- [-doc](../../reference/command-line-compiler/doc.md)
- [Instrukcje: tworzenie dokumentacji XML](how-to-create-xml-documentation.md)
