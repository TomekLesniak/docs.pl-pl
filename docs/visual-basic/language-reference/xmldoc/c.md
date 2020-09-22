---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 969df339eb766d2edb444ab5626af4e69accddba
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871696"
---
# <a name="c-visual-basic"></a>\<c> (Visual Basic)

Wskazuje, że tekst w opisie ma kod.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Parametry  
  
|Parametr|Opis|  
|---|---|  
|`text`|Tekst, który ma być wskazywany jako kod.|  
  
## <a name="remarks"></a>Uwagi  

 `<c>`Tag umożliwia wskazanie, że tekst w opisie powinien być oznaczony jako kod. Użyj [\<code>](code.md) , aby wskazać wiele wierszy jako kod.  
  
 Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.  
  
## <a name="example"></a>Przykład  

 Ten przykład używa `<c>` znacznika w sekcji podsumowania, aby wskazać, że `Counter` jest to kod.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Tagi komentarza XML](index.md)
