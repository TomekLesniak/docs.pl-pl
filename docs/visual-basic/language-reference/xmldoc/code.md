---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d058663213cf02f2142bff740aeec1b60791362c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873026"
---
# <a name="code-visual-basic"></a>\<code> (Visual Basic)

Wskazuje, że tekst jest wieloma wierszami kodu.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Parametry  

 `content`  
 Tekst, który ma zostać oznaczony jako kod.  
  
## <a name="remarks"></a>Uwagi  

 Użyj `<code>` znacznika, aby wskazać wiele wierszy jako kod. Użyj, [\<c>](c.md) Aby wskazać, że tekst w opisie powinien być oznaczony jako kod.  
  
 Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie użyto \<code> znacznika, aby dołączyć przykładowy kod do użycia `ID` pola.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Zobacz też

- [Tagi komentarza XML](index.md)
