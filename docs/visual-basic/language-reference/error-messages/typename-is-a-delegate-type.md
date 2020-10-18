---
title: Typ „<typename>” jest typem delegowanym
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: dcb52188c53b38ac14de0002b5212bb33c9f7203
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161780"
---
# <a name="bc32008-typename-is-a-delegate-type"></a><span data-ttu-id="cf262-102">BC32008: " \<typename> " jest typem delegata</span><span class="sxs-lookup"><span data-stu-id="cf262-102">BC32008: '\<typename>' is a delegate type</span></span>

<span data-ttu-id="cf262-103">\<typename>Typ "" jest typem delegowanym.</span><span class="sxs-lookup"><span data-stu-id="cf262-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="cf262-104">Konstrukcja delegata zezwala tylko na pojedyncze wyrażenie AddressOf jako listę argumentów.</span><span class="sxs-lookup"><span data-stu-id="cf262-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="cf262-105">Często wyrażenie AddressOf może być używane zamiast konstrukcji delegata.</span><span class="sxs-lookup"><span data-stu-id="cf262-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>

 <span data-ttu-id="cf262-106">`New`Klauzula tworząca wystąpienie klasy delegata dostarcza do konstruktora delegata nieprawidłową listę argumentów.</span><span class="sxs-lookup"><span data-stu-id="cf262-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>

 <span data-ttu-id="cf262-107">`AddressOf`Podczas tworzenia nowego wystąpienia delegata można podać tylko jedno wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="cf262-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>

 <span data-ttu-id="cf262-108">Ten błąd może wystąpić, jeśli nie przekażesz żadnych argumentów do konstruktora delegata, Jeśli przekażesz więcej niż jeden argument lub przekażesz pojedynczy argument, który nie jest prawidłowym `AddressOf` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="cf262-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>

 <span data-ttu-id="cf262-109">**Identyfikator błędu:** BC32008</span><span class="sxs-lookup"><span data-stu-id="cf262-109">**Error ID:** BC32008</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="cf262-110">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="cf262-110">To correct this error</span></span>

- <span data-ttu-id="cf262-111">Użyj jednego `AddressOf` wyrażenia na liście argumentów dla klasy delegata w `New` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="cf262-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf262-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cf262-112">See also</span></span>

- [<span data-ttu-id="cf262-113">Operator new</span><span class="sxs-lookup"><span data-stu-id="cf262-113">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="cf262-114">AddressOf, operator</span><span class="sxs-lookup"><span data-stu-id="cf262-114">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="cf262-115">Delegaci</span><span class="sxs-lookup"><span data-stu-id="cf262-115">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="cf262-116">Instrukcje: wywoływanie metody delegata</span><span class="sxs-lookup"><span data-stu-id="cf262-116">How to: Invoke a Delegate Method</span></span>](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
