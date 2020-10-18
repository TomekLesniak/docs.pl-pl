---
title: Zwracany typ funkcji „<procedurename>” jest niezgodny ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 9a877046a1b30e2e3773a41b8b44573e11ff1c96
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159706"
---
# <a name="bc40027-return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="2d613-102">BC40027: zwracany typ funkcji " \<procedurename> " jest niezgodny ze specyfikacją CLS</span><span class="sxs-lookup"><span data-stu-id="2d613-102">BC40027: Return type of function '\<procedurename>' is not CLS-compliant</span></span>

<span data-ttu-id="2d613-103">`Function`Procedura jest oznaczona jako `<CLSCompliant(True)>` , ale zwraca typ, który jest oznaczony jako `<CLSCompliant(False)>` , nie jest oznaczona lub nie kwalifikuje się, ponieważ jest typem niezgodnym.</span><span class="sxs-lookup"><span data-stu-id="2d613-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>

 <span data-ttu-id="2d613-104">Aby procedura była zgodna z [niezależnością od języka i składnikami Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), musi używać tylko typów zgodnych ze specyfikacją CLS.</span><span class="sxs-lookup"><span data-stu-id="2d613-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="2d613-105">Dotyczy to typów parametrów, typu zwracanego i typów wszystkich zmiennych lokalnych.</span><span class="sxs-lookup"><span data-stu-id="2d613-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>

 <span data-ttu-id="2d613-106">Następujące Visual Basic typy danych nie są zgodne ze specyfikacją CLS:</span><span class="sxs-lookup"><span data-stu-id="2d613-106">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="2d613-107">SByte, typ danych</span><span class="sxs-lookup"><span data-stu-id="2d613-107">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="2d613-108">UInteger, typ danych</span><span class="sxs-lookup"><span data-stu-id="2d613-108">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="2d613-109">ULong, typ danych</span><span class="sxs-lookup"><span data-stu-id="2d613-109">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="2d613-110">UShort, typ danych</span><span class="sxs-lookup"><span data-stu-id="2d613-110">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="2d613-111">Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub `False` w celu wskazania zgodności lub niezgodności.</span><span class="sxs-lookup"><span data-stu-id="2d613-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="2d613-112">Dla tego parametru nie ma wartości domyślnej i należy podać wartość.</span><span class="sxs-lookup"><span data-stu-id="2d613-112">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="2d613-113">Jeśli nie zastosujesz <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.</span><span class="sxs-lookup"><span data-stu-id="2d613-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="2d613-114">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="2d613-114">By default, this message is a warning.</span></span> <span data-ttu-id="2d613-115">Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2d613-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="2d613-116">**Identyfikator błędu:** BC40027</span><span class="sxs-lookup"><span data-stu-id="2d613-116">**Error ID:** BC40027</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2d613-117">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="2d613-117">To correct this error</span></span>

- <span data-ttu-id="2d613-118">Jeśli `Function` procedura musi zwrócić ten konkretny typ, Usuń <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="2d613-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="2d613-119">Procedura nie może być zgodna ze specyfikacją CLS.</span><span class="sxs-lookup"><span data-stu-id="2d613-119">The procedure cannot be CLS-compliant.</span></span>

- <span data-ttu-id="2d613-120">Jeśli `Function` procedura musi być zgodna ze specyfikacją CLS, należy zmienić typ zwracany na najbliższy typ zgodny ze specyfikacją CLS.</span><span class="sxs-lookup"><span data-stu-id="2d613-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="2d613-121">Na przykład, zamiast `UInteger` można użyć, `Integer` Jeśli nie potrzebujesz zakresu wartości powyżej 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="2d613-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="2d613-122">Jeśli potrzebujesz rozszerzonego zakresu, możesz zamienić `UInteger` na `Long` .</span><span class="sxs-lookup"><span data-stu-id="2d613-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="2d613-123">Jeśli masz połączenie z obiektami automatyzacji lub COM, pamiętaj, że niektóre typy mają różne szerokości danych niż w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d613-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="2d613-124">Na przykład `int` często jest 16 bitów w innych środowiskach.</span><span class="sxs-lookup"><span data-stu-id="2d613-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="2d613-125">Jeśli zwracasz 16-bitową liczbę całkowitą do takiego składnika, zadeklaruj ją jako `Short` zamiast `Integer` w kodzie zarządzanym Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2d613-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
