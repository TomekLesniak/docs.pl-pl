---
title: Nie można wywnioskować argumentów typu na podstawie obiektu delegowanego
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: f7937a34ab425da684f892250884d21e020e4c57
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161247"
---
# <a name="bc36564-type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="56e8f-102">BC36564: nie można wywnioskować argumentów typu na podstawie delegata</span><span class="sxs-lookup"><span data-stu-id="56e8f-102">BC36564: Type arguments could not be inferred from the delegate</span></span>

<span data-ttu-id="56e8f-103">Instrukcja przypisania używa `AddressOf` do przypisywania adresu procedury ogólnej do delegata, ale nie dostarcza żadnych argumentów typu do procedury ogólnej.</span><span class="sxs-lookup"><span data-stu-id="56e8f-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>

 <span data-ttu-id="56e8f-104">Zwykle podczas wywoływania typu ogólnego należy podać argument typu dla każdego parametru typu, który definiuje typ ogólny.</span><span class="sxs-lookup"><span data-stu-id="56e8f-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="56e8f-105">Jeśli nie podasz żadnych argumentów typu, kompilator próbuje wywnioskować typy do przekazania do parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="56e8f-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="56e8f-106">Jeśli kontekst nie zapewnia wystarczającej ilości informacji do wywnioskowania typów przez kompilator, generowany jest błąd.</span><span class="sxs-lookup"><span data-stu-id="56e8f-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>

 <span data-ttu-id="56e8f-107">**Identyfikator błędu:** BC36564</span><span class="sxs-lookup"><span data-stu-id="56e8f-107">**Error ID:** BC36564</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="56e8f-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="56e8f-108">To correct this error</span></span>

- <span data-ttu-id="56e8f-109">Określ argumenty typu dla procedury ogólnej w `AddressOf` wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="56e8f-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>

## <a name="see-also"></a><span data-ttu-id="56e8f-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="56e8f-110">See also</span></span>

- [<span data-ttu-id="56e8f-111">Typy ogólne w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56e8f-111">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="56e8f-112">AddressOf, operator</span><span class="sxs-lookup"><span data-stu-id="56e8f-112">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="56e8f-113">Procedury ogólne w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56e8f-113">Generic Procedures in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="56e8f-114">Lista typów</span><span class="sxs-lookup"><span data-stu-id="56e8f-114">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="56e8f-115">Metody rozszerzające</span><span class="sxs-lookup"><span data-stu-id="56e8f-115">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
