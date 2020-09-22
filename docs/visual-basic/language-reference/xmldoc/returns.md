---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 37b110cc6e12f11196d2a1c5cc6026d87b453626
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866411"
---
# <a name="returns-visual-basic"></a>\<returns> (Visual Basic)

Określa wartość zwracaną przez właściwość lub funkcję.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parametry  

 `description`  
 Opis wartości zwracanej.  
  
## <a name="remarks"></a>Uwagi  

 Użyj `<returns>` znacznika w komentarzu dla deklaracji metody, aby opisać wartość zwracaną.  
  
 Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie używa `<returns>` znacznika, aby wyjaśnić, co `DoesRecordExist` zwraca funkcja.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Zobacz też

- [Tagi komentarza XML](index.md)
