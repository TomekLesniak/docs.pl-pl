---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 6e9f63e4d31df7790f51ae4d166b606f2c63f14b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872971"
---
# <a name="example-visual-basic"></a>\<example> (Visual Basic)

Określa przykład dla elementu członkowskiego.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a>Parametry  

 `description`  
 Opis przykładu kodu.  
  
## <a name="remarks"></a>Uwagi  

 `<example>`Tag pozwala określić przykład użycia metody lub innego elementu członkowskiego biblioteki. Zwykle obejmuje to użycie [\<code>](code.md) znacznika.  
  
 Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie użyto `<example>` znacznika, aby dołączyć przykład do użycia `ID` pola.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Zobacz też

- [Tagi komentarza XML](index.md)
