---
title: Wnioskowanie typu zerowalnego nie jest obsługiwane w tym kontekście
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 610d2dc427d882c412b87eb67f021a8a86025f25
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159930"
---
# <a name="bc36629-nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="8b7c6-102">BC36629: wnioskowanie o typie dopuszczające wartość null nie jest obsługiwane w tym kontekście</span><span class="sxs-lookup"><span data-stu-id="8b7c6-102">BC36629: Nullable type inference is not supported in this context</span></span>

<span data-ttu-id="8b7c6-103">Typy wartości i struktury mogą być deklarowane jako dopuszczające wartość null.</span><span class="sxs-lookup"><span data-stu-id="8b7c6-103">Value types and structures can be declared nullable.</span></span>

```vb
Dim a? As Integer
Dim b As Integer?
```

 <span data-ttu-id="8b7c6-104">Nie można jednak używać deklaracji wartości null w połączeniu z wnioskami o typie.</span><span class="sxs-lookup"><span data-stu-id="8b7c6-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="8b7c6-105">Poniższe przykłady powodują wystąpienie tego błędu.</span><span class="sxs-lookup"><span data-stu-id="8b7c6-105">The following examples cause this error.</span></span>

```vb
' Not valid.
' Dim c? = 10
' Dim d? = a
```

 <span data-ttu-id="8b7c6-106">**Identyfikator błędu:** BC36629</span><span class="sxs-lookup"><span data-stu-id="8b7c6-106">**Error ID:** BC36629</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8b7c6-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="8b7c6-107">To correct this error</span></span>

- <span data-ttu-id="8b7c6-108">Użyj `As` klauzuli, aby zadeklarować zmienną jako typ wartości null.</span><span class="sxs-lookup"><span data-stu-id="8b7c6-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b7c6-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8b7c6-109">See also</span></span>

- [<span data-ttu-id="8b7c6-110">Typy wartości null</span><span class="sxs-lookup"><span data-stu-id="8b7c6-110">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="8b7c6-111">Wnioskowanie o typie lokalnym</span><span class="sxs-lookup"><span data-stu-id="8b7c6-111">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
