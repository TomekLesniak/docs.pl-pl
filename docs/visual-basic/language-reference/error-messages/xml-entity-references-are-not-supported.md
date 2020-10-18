---
title: Odwołania do jednostek XML nie są obsługiwane
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 37e72dbd6de61a50b4192a0151db40cb4be49d1c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163275"
---
# <a name="bc31180-xml-entity-references-are-not-supported"></a>BC31180: odwołania do jednostek XML nie są obsługiwane

Odwołanie do jednostki (na przykład `©` ), które nie jest zdefiniowane w specyfikacji xml 1,0, jest uwzględniane jako wartość literału XML. `&` `"` `<` `>` `'` Literały XML obsługują tylko odwołania do jednostek XML,,, i.

 **Identyfikator błędu:** BC31180

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń nieobsługiwane odwołanie do jednostki.

## <a name="see-also"></a>Zobacz też

- [Literały XML i specyfikacja XML 1.0](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [Literały XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
