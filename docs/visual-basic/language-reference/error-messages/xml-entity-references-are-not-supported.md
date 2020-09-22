---
title: Odwołania do jednostek XML nie są obsługiwane
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 470e5577654ce8b6bbc2732a41c130a85ddc96e5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874991"
---
# <a name="xml-entity-references-are-not-supported"></a>Odwołania do jednostek XML nie są obsługiwane

Odwołanie do jednostki (na przykład `©` ), które nie jest zdefiniowane w specyfikacji xml 1,0, jest uwzględniane jako wartość literału XML. `&` `"` `<` `>` `'` Literały XML obsługują tylko odwołania do jednostek XML,,, i.  
  
 **Identyfikator błędu:** BC31180  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Usuń nieobsługiwane odwołanie do jednostki.  
  
## <a name="see-also"></a>Zobacz też

- [Literały XML i specyfikacja XML 1.0](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [Literały XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
