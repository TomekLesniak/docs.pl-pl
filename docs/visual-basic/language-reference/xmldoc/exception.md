---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e3f386d2a1e15ea3e1519d6e1e5e31c34c73fb99
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872904"
---
# <a name="exception-visual-basic"></a>\<exception> (Visual Basic)

Określa, które wyjątki mogą być zgłaszane.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a>Parametry  

 `member`  
 Odwołanie do wyjątku, które jest dostępne w bieżącym środowisku kompilacji. Kompilator sprawdza, czy dany wyjątek istnieje i tłumaczy `member` na nazwę elementu kanonicznego w wyjściowym kodzie XML. `member` musi znajdować się w podwójnym cudzysłowie ("").  
  
 `description`  
 Opis.  
  
## <a name="remarks"></a>Uwagi  

 Użyj `<exception>` znacznika, aby określić, które wyjątki mogą być zgłaszane. Ten tag jest stosowany do definicji metody.  
  
 Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie używa `<exception>` znacznika do opisywania wyjątku, który `IntDivide` Funkcja może zgłosić.  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- [Tagi komentarza XML](index.md)
