---
title: Element „<keyword>” jest prawidłowy tylko wewnątrz metody wystąpienia
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: ad39ade294b362b20f2dfb93455445bf41d056cd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163327"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="10fcd-102">BC30043: element " \<keyword> " jest prawidłowy tylko wewnątrz metody wystąpienia</span><span class="sxs-lookup"><span data-stu-id="10fcd-102">BC30043: '\<keyword>' is valid only within an instance method</span></span>

<span data-ttu-id="10fcd-103">`Me` `MyClass` Słowa kluczowe, i `MyBase` odwołują się do określonych wystąpień klasy.</span><span class="sxs-lookup"><span data-stu-id="10fcd-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="10fcd-104">Nie można ich używać wewnątrz wspólnej `Function` procedury lub `Sub` .</span><span class="sxs-lookup"><span data-stu-id="10fcd-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>

<span data-ttu-id="10fcd-105">*Identyfikator błędu:*\* BC30043</span><span class="sxs-lookup"><span data-stu-id="10fcd-105">*Error ID:*\* BC30043</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="10fcd-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="10fcd-106">To correct this error</span></span>

- <span data-ttu-id="10fcd-107">Usuń słowo kluczowe z procedury lub Usuń `Shared` słowo kluczowe z deklaracji procedury.</span><span class="sxs-lookup"><span data-stu-id="10fcd-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="10fcd-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="10fcd-108">See also</span></span>

- [<span data-ttu-id="10fcd-109">Przypisanie zmiennej obiektu</span><span class="sxs-lookup"><span data-stu-id="10fcd-109">Object Variable Assignment</span></span>](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="10fcd-110">Me, My, MyBase i MyClass</span><span class="sxs-lookup"><span data-stu-id="10fcd-110">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="10fcd-111">Podstawowe informacje o dziedziczeniu</span><span class="sxs-lookup"><span data-stu-id="10fcd-111">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
