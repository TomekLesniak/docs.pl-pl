---
title: Parametrów typu nie można używać jako kwalifikatorów
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 14e6094b0cc129eba86db1808c0f0575955f5e75
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161195"
---
# <a name="bc32098-type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="0ec43-102">BC32098: parametry typu nie mogą być używane jako kwalifikatory</span><span class="sxs-lookup"><span data-stu-id="0ec43-102">BC32098: Type parameters cannot be used as qualifiers</span></span>

<span data-ttu-id="0ec43-103">Element programistyczny jest kwalifikowana za pomocą ciągu kwalifikacji, który zawiera parametr typu.</span><span class="sxs-lookup"><span data-stu-id="0ec43-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>

<span data-ttu-id="0ec43-104">Parametr typu reprezentuje wymaganie dla typu, który ma zostać dostarczony podczas konstruowania typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="0ec43-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="0ec43-105">Nie reprezentuje określonego zdefiniowanego typu.</span><span class="sxs-lookup"><span data-stu-id="0ec43-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="0ec43-106">Ciąg kwalifikacji musi zawierać tylko elementy, które są zdefiniowane w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="0ec43-106">A qualification string must include only elements that are defined at compile time.</span></span>

<span data-ttu-id="0ec43-107">Następujący kod może generować ten błąd:</span><span class="sxs-lookup"><span data-stu-id="0ec43-107">The following code can generate this error:</span></span>

```vb
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean

    Dim saveText As c.Text
    ' Insert code to look for badText within saveText.
End Function
```

 <span data-ttu-id="0ec43-108">**Identyfikator błędu:** BC32098</span><span class="sxs-lookup"><span data-stu-id="0ec43-108">**Error ID:** BC32098</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0ec43-109">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="0ec43-109">To correct this error</span></span>

1. <span data-ttu-id="0ec43-110">Usuń parametr typu z ciągu kwalifikacji lub zastąp go zdefiniowanym typem.</span><span class="sxs-lookup"><span data-stu-id="0ec43-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>

2. <span data-ttu-id="0ec43-111">Jeśli musisz użyć skonstruowanego typu do zlokalizowania kwalifikowanego elementu programistycznego, musisz użyć dodatkowej logiki programu.</span><span class="sxs-lookup"><span data-stu-id="0ec43-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ec43-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0ec43-112">See also</span></span>

- [<span data-ttu-id="0ec43-113">Odwołania do elementów zadeklarowanych</span><span class="sxs-lookup"><span data-stu-id="0ec43-113">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="0ec43-114">Typy ogólne w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ec43-114">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="0ec43-115">Lista typów</span><span class="sxs-lookup"><span data-stu-id="0ec43-115">Type List</span></span>](../statements/type-list.md)
