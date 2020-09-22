---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867927"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="3e2b8-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e2b8-102">Narrowing (Visual Basic)</span></span>

<span data-ttu-id="3e2b8-103">Wskazuje, że Operator konwersji ( `CType` ) konwertuje klasę lub strukturę do typu, który może nie być w stanie przechowywać niektórych możliwych wartości oryginalnej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="3e2b8-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="3e2b8-104">Konwertowanie za pomocą słowa kluczowego Narrowing</span><span class="sxs-lookup"><span data-stu-id="3e2b8-104">Converting with the Narrowing Keyword</span></span>  

 <span data-ttu-id="3e2b8-105">Procedura konwersji musi być określona `Public Shared` poza `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="3e2b8-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="3e2b8-106">Konwersje wąskie nie zawsze kończą się powodzeniem w czasie wykonywania i mogą kończyć się niepowodzeniem lub spowodować utratę danych.</span><span class="sxs-lookup"><span data-stu-id="3e2b8-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="3e2b8-107">Przykłady to `Long` `Integer` , `String` do `Date` i typ podstawowy dla typu pochodnego.</span><span class="sxs-lookup"><span data-stu-id="3e2b8-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="3e2b8-108">Ta ostatnia konwersja jest zawężana, ponieważ typ podstawowy może nie zawierać wszystkich elementów członkowskich typu pochodnego, w związku z czym nie jest wystąpieniem typu pochodnego.</span><span class="sxs-lookup"><span data-stu-id="3e2b8-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="3e2b8-109">Jeśli `Option Strict` jest `On` , kod zużywający musi używać `CType` dla wszystkich konwersji zawężających.</span><span class="sxs-lookup"><span data-stu-id="3e2b8-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="3e2b8-110">`Narrowing`Słowo kluczowe może być używane w tym kontekście:</span><span class="sxs-lookup"><span data-stu-id="3e2b8-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="3e2b8-111">Operator — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3e2b8-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3e2b8-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3e2b8-112">See also</span></span>

- [<span data-ttu-id="3e2b8-113">Operator — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3e2b8-113">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="3e2b8-114">Widening</span><span class="sxs-lookup"><span data-stu-id="3e2b8-114">Widening</span></span>](widening.md)
- [<span data-ttu-id="3e2b8-115">Rozszerzanie i zwężanie konwersji</span><span class="sxs-lookup"><span data-stu-id="3e2b8-115">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="3e2b8-116">Instrukcje: definiowanie operatora</span><span class="sxs-lookup"><span data-stu-id="3e2b8-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="3e2b8-117">CType — Funkcja</span><span class="sxs-lookup"><span data-stu-id="3e2b8-117">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="3e2b8-118">Option Strict — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="3e2b8-118">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
