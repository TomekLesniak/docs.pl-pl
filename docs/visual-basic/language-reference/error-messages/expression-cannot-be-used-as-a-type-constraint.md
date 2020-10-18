---
title: Elementu „<expression>” nie można użyć jako ograniczenia typu
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 6e55bfdc175f285b335512e64f4c2407bdb0e8c7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163093"
---
# <a name="bc32061-expression-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="dfd14-102">BC32061: element " \<expression> " nie może być używany jako ograniczenie typu</span><span class="sxs-lookup"><span data-stu-id="dfd14-102">BC32061: '\<expression>' cannot be used as a type constraint</span></span>

<span data-ttu-id="dfd14-103">Lista ograniczeń zawiera wyrażenie, które nie reprezentuje prawidłowego ograniczenia w parametrze typu.</span><span class="sxs-lookup"><span data-stu-id="dfd14-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>

 <span data-ttu-id="dfd14-104">Lista ograniczeń nakłada wymagania dotyczące argumentu typu przekazaną do parametru typu.</span><span class="sxs-lookup"><span data-stu-id="dfd14-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="dfd14-105">W dowolnej kombinacji można określić następujące wymagania:</span><span class="sxs-lookup"><span data-stu-id="dfd14-105">You can specify the following requirements in any combination:</span></span>

- <span data-ttu-id="dfd14-106">Argument typu musi implementować jeden lub więcej interfejsów</span><span class="sxs-lookup"><span data-stu-id="dfd14-106">The type argument must implement one or more interfaces</span></span>

- <span data-ttu-id="dfd14-107">Argument typu musi dziedziczyć z co najwyżej jednej klasy</span><span class="sxs-lookup"><span data-stu-id="dfd14-107">The type argument must inherit from at most one class</span></span>

- <span data-ttu-id="dfd14-108">Argument typu musi ujawniać Konstruktor bez parametrów, który może uzyskać dostęp do kodu (Uwzględnij `New` ograniczenie)</span><span class="sxs-lookup"><span data-stu-id="dfd14-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>

 <span data-ttu-id="dfd14-109">Jeśli na liście ograniczeń nie dołączysz żadnej konkretnej klasy lub interfejsu, możesz wprowadzić bardziej ogólne wymagania, określając jedną z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="dfd14-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>

- <span data-ttu-id="dfd14-110">Argument typu musi być typem wartości (Uwzględnij `Structure` ograniczenie)</span><span class="sxs-lookup"><span data-stu-id="dfd14-110">The type argument must be a value type (include the `Structure` constraint)</span></span>

- <span data-ttu-id="dfd14-111">Argument typu musi być typem referencyjnym (Uwzględnij `Class` ograniczenie)</span><span class="sxs-lookup"><span data-stu-id="dfd14-111">The type argument must be a reference type (include the `Class` constraint)</span></span>

 <span data-ttu-id="dfd14-112">Nie można określić jednocześnie `Structure` i `Class` dla tego samego parametru typu. nie można określić jednego więcej niż raz.</span><span class="sxs-lookup"><span data-stu-id="dfd14-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>

 <span data-ttu-id="dfd14-113">**Identyfikator błędu:** BC32061</span><span class="sxs-lookup"><span data-stu-id="dfd14-113">**Error ID:** BC32061</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="dfd14-114">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="dfd14-114">To correct this error</span></span>

- <span data-ttu-id="dfd14-115">Sprawdź, czy wyrażenie i jego elementy są poprawnie napisane.</span><span class="sxs-lookup"><span data-stu-id="dfd14-115">Verify that the expression and its elements are spelled correctly.</span></span>

- <span data-ttu-id="dfd14-116">Jeśli wyrażenie nie kwalifikuje się do powyższej listy wymagań, usuń je z listy ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="dfd14-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>

- <span data-ttu-id="dfd14-117">Jeśli wyrażenie odwołuje się do interfejsu lub klasy, należy sprawdzić, czy kompilator ma dostęp do tego interfejsu lub klasy.</span><span class="sxs-lookup"><span data-stu-id="dfd14-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="dfd14-118">Może być konieczne zakwalifikowanie nazwy i może być konieczne dodanie odwołania do projektu.</span><span class="sxs-lookup"><span data-stu-id="dfd14-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="dfd14-119">Aby uzyskać więcej informacji, zobacz "odwołania do projektów" w [odwołaniach do zadeklarowanych elementów](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="dfd14-119">For more information, see "References to Projects" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfd14-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dfd14-120">See also</span></span>

- [<span data-ttu-id="dfd14-121">Typy ogólne w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfd14-121">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="dfd14-122">Typy wartości i odwołań</span><span class="sxs-lookup"><span data-stu-id="dfd14-122">Value Types and Reference Types</span></span>](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="dfd14-123">Odwołania do elementów zadeklarowanych</span><span class="sxs-lookup"><span data-stu-id="dfd14-123">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
