---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 550f8b63928f80878ba316bfaf09077e14091305
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875178"
---
# <a name="value-visual-basic"></a>\<value> (Visual Basic)

Określa opis właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Parametry  

 `property-description`  
 Opis właściwości.  
  
## <a name="remarks"></a>Uwagi  

 Użyj `<value>` znacznika, aby opisać właściwość. Należy pamiętać, że po dodaniu właściwości przy użyciu kreatora kodu w środowisku deweloperskim programu Visual Studio zostanie dodany [\<summary>](summary.md) tag nowej właściwości. Następnie należy ręcznie dodać tag, `<value>` aby opisać wartość, którą reprezentuje właściwość.  
  
 Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie używa `<value>` znacznika do opisania wartości, jaką `Counter` zawiera właściwość.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Tagi komentarza XML](index.md)
