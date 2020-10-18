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
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="c6082-102">BC42319: wyjątek komentarza XML musi mieć atrybut "cref"</span><span class="sxs-lookup"><span data-stu-id="c6082-102">BC42319: XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="c6082-103">\<exception>Tag umożliwia dokumentowanie wyjątków, które mogą być zgłaszane przez metodę.</span><span class="sxs-lookup"><span data-stu-id="c6082-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="c6082-104">Wymagany `cref` atrybut określa nazwę elementu członkowskiego, który jest sprawdzany przez generator dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="c6082-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="c6082-105">Jeśli element członkowski istnieje, jest tłumaczony na nazwę elementu kanonicznego w pliku dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="c6082-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="c6082-106">**Identyfikator błędu:** BC42319</span><span class="sxs-lookup"><span data-stu-id="c6082-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c6082-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="c6082-107">To correct this error</span></span>

<span data-ttu-id="c6082-108">Dodaj `cref` atrybut do wyjątku w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c6082-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="c6082-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c6082-109">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="c6082-110">Instrukcje: tworzenie dokumentacji XML</span><span class="sxs-lookup"><span data-stu-id="c6082-110">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="c6082-111">Tagi komentarza XML</span><span class="sxs-lookup"><span data-stu-id="c6082-111">XML Comment Tags</span></span>](../xmldoc/index.md)
