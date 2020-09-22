---
title: Stałe muszą być typu wewnętrznego lub wyliczeniowego, a nie typu klasy, struktury, parametru typu lub tablicy
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: a9bbf27615233f4282e481710a0234b2fa589f63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874559"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="0ab12-102">Stałe muszą być typu wewnętrznego lub wyliczeniowego, a nie typu klasy, struktury, parametru typu lub tablicy</span><span class="sxs-lookup"><span data-stu-id="0ab12-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>

<span data-ttu-id="0ab12-103">Próbowano zadeklarować stałą jako klasę, strukturę lub typ tablicy albo jako parametr typu zdefiniowany przez zawierający typ ogólny.</span><span class="sxs-lookup"><span data-stu-id="0ab12-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="0ab12-104">Stałe muszą być typu wewnętrznego (,,,,,,,,,, `Boolean` `Byte` ,,,, `Date` `Decimal` `Double` `Integer` `Long` `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` lub `UShort` ) lub `Enum` typu na podstawie jednego z typów całkowitych.</span><span class="sxs-lookup"><span data-stu-id="0ab12-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="0ab12-105">**Identyfikator błędu:** BC30424</span><span class="sxs-lookup"><span data-stu-id="0ab12-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0ab12-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="0ab12-106">To correct this error</span></span>  
  
1. <span data-ttu-id="0ab12-107">Zadeklaruj stałą jako wewnętrzną lub `Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="0ab12-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2. <span data-ttu-id="0ab12-108">Stała może być również specjalną wartością, taką jak `True` , `False` , lub `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="0ab12-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="0ab12-109">Kompilator uważa, że te wstępnie zdefiniowane wartości mają być odpowiednim typem wewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="0ab12-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab12-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0ab12-110">See also</span></span>

- [<span data-ttu-id="0ab12-111">Stałe i wyliczenia</span><span class="sxs-lookup"><span data-stu-id="0ab12-111">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
- [<span data-ttu-id="0ab12-112">Typy danych</span><span class="sxs-lookup"><span data-stu-id="0ab12-112">Data Types</span></span>](../../programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="0ab12-113">Typy danych</span><span class="sxs-lookup"><span data-stu-id="0ab12-113">Data Types</span></span>](../data-types/index.md)
