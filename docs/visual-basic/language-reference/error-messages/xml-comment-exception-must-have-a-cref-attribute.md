---
title: Wyjątek komentarza XML musi mieć atrybut „cref”
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 18e7aa5f6905eaa9c509aa21fe6f5bfcd54d46f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163301"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a>BC42319: wyjątek komentarza XML musi mieć atrybut "cref"

\<exception>Tag umożliwia dokumentowanie wyjątków, które mogą być zgłaszane przez metodę. Wymagany `cref` atrybut określa nazwę elementu członkowskiego, który jest sprawdzany przez generator dokumentacji. Jeśli element członkowski istnieje, jest tłumaczony na nazwę elementu kanonicznego w pliku dokumentacji.

**Identyfikator błędu:** BC42319

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

Dodaj `cref` atrybut do wyjątku w następujący sposób:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Zobacz też

- [\<exception>](../xmldoc/exception.md)
- [Instrukcje: tworzenie dokumentacji XML](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Tagi komentarza XML](../xmldoc/index.md)
