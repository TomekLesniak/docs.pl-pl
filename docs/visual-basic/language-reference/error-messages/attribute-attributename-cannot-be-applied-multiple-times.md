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
# <a name="bc30663-attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="0ec90-102">BC30663: \<attributename> nie można wielokrotnie zastosować atrybutu ""</span><span class="sxs-lookup"><span data-stu-id="0ec90-102">BC30663: Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="0ec90-103">Ten atrybut może być stosowany tylko raz.</span><span class="sxs-lookup"><span data-stu-id="0ec90-103">The attribute can only be applied once.</span></span> <span data-ttu-id="0ec90-104">Ten `AttributeUsage` atrybut określa, czy atrybut może być stosowany więcej niż jeden raz.</span><span class="sxs-lookup"><span data-stu-id="0ec90-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>

 <span data-ttu-id="0ec90-105">**Identyfikator błędu:** BC30663</span><span class="sxs-lookup"><span data-stu-id="0ec90-105">**Error ID:** BC30663</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0ec90-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="0ec90-106">To correct this error</span></span>

1. <span data-ttu-id="0ec90-107">Upewnij się, że atrybut jest stosowany tylko raz.</span><span class="sxs-lookup"><span data-stu-id="0ec90-107">Make sure the attribute is only applied once.</span></span>

2. <span data-ttu-id="0ec90-108">Jeśli używasz niestandardowych atrybutów, Rozważ zmianę ich `AttributeUsage` atrybutu w celu zezwolenia na użycie wielu atrybutów, jak w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0ec90-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>

```vb
<AttributeUsage(AllowMultiple := True)>
```

## <a name="see-also"></a><span data-ttu-id="0ec90-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0ec90-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="0ec90-110">Tworzenie atrybutów niestandardowych</span><span class="sxs-lookup"><span data-stu-id="0ec90-110">Creating Custom Attributes</span></span>](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="0ec90-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="0ec90-111">AttributeUsage</span></span>](../../programming-guide/concepts/attributes/attributeusage.md)
