---
title: Nie można wielokrotnie zastosować atrybutu „<attributename>”.
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 27cbe6d0043179c4a5d52baae06bad805f9d1d3a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162664"
---
# <a name="bc30663-attribute-attributename-cannot-be-applied-multiple-times"></a>BC30663: \<attributename> nie można wielokrotnie zastosować atrybutu ""

Ten atrybut może być stosowany tylko raz. Ten `AttributeUsage` atrybut określa, czy atrybut może być stosowany więcej niż jeden raz.

 **Identyfikator błędu:** BC30663

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Upewnij się, że atrybut jest stosowany tylko raz.

2. Jeśli używasz niestandardowych atrybutów, Rozważ zmianę ich `AttributeUsage` atrybutu w celu zezwolenia na użycie wielu atrybutów, jak w poniższym przykładzie.

```vb
<AttributeUsage(AllowMultiple := True)>
```

## <a name="see-also"></a>Zobacz też

- <xref:System.AttributeUsageAttribute>
- [Tworzenie atrybutów niestandardowych](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../programming-guide/concepts/attributes/attributeusage.md)
