---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0846efbaf2afacd3d0783a2d2d8e4dae3fc8b715
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872703"
---
# <a name="para-visual-basic"></a>\<para> (Visual Basic)

Określa, że zawartość jest sformatowana w akapicie.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Parametry  

 `content`  
 Tekst akapitu.  
  
## <a name="remarks"></a>Uwagi  

 `<para>`Tag jest używany wewnątrz tagu, takiego jak [\<summary>](summary.md) , [\<remarks>](remarks.md) , lub [\<returns>](returns.md) , i umożliwia dodanie struktury do tekstu.  
  
 Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.  
  
## <a name="example"></a>Przykład  

 Ten przykład używa `<para>` znacznika, aby podzielić sekcję Uwagi dla `UpdateRecord` metody na dwa akapity.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Zobacz też

- [Tagi komentarza XML](index.md)
