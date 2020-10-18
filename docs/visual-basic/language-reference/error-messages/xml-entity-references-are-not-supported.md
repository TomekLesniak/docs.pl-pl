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
# <a name="bc31180-xml-entity-references-are-not-supported"></a><span data-ttu-id="565b5-102">BC31180: odwołania do jednostek XML nie są obsługiwane</span><span class="sxs-lookup"><span data-stu-id="565b5-102">BC31180: XML entity references are not supported</span></span>

<span data-ttu-id="565b5-103">Odwołanie do jednostki (na przykład `©` ), które nie jest zdefiniowane w specyfikacji xml 1,0, jest uwzględniane jako wartość literału XML.</span><span class="sxs-lookup"><span data-stu-id="565b5-103">An entity reference (for example, `©`) that is not defined in the XML 1.0 specification is included as a value for an XML literal.</span></span> <span data-ttu-id="565b5-104">`&` `"` `<` `>` `'` Literały XML obsługują tylko odwołania do jednostek XML,,, i.</span><span class="sxs-lookup"><span data-stu-id="565b5-104">Only `&`, `"`, `<`, `>`, and `'` XML entity references are supported in XML literals.</span></span>

 <span data-ttu-id="565b5-105">**Identyfikator błędu:** BC31180</span><span class="sxs-lookup"><span data-stu-id="565b5-105">**Error ID:** BC31180</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="565b5-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="565b5-106">To correct this error</span></span>

- <span data-ttu-id="565b5-107">Usuń nieobsługiwane odwołanie do jednostki.</span><span class="sxs-lookup"><span data-stu-id="565b5-107">Remove the unsupported entity reference.</span></span>

## <a name="see-also"></a><span data-ttu-id="565b5-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="565b5-108">See also</span></span>

- [<span data-ttu-id="565b5-109">Literały XML i specyfikacja XML 1.0</span><span class="sxs-lookup"><span data-stu-id="565b5-109">XML Literals and the XML 1.0 Specification</span></span>](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [<span data-ttu-id="565b5-110">Literały XML</span><span class="sxs-lookup"><span data-stu-id="565b5-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="565b5-111">XML</span><span class="sxs-lookup"><span data-stu-id="565b5-111">XML</span></span>](../../programming-guide/language-features/xml/index.md)
