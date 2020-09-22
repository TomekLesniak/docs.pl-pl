---
title: Typ wartości opcjonalnej dla parametru opcjonalnego <parametername> jest niezgodny ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: 77d23fff518cb3b0768264ddd07728e3ad6b9f91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872214"
---
# <a name="type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="06ad0-102">Typ wartości opcjonalnej dla parametru opcjonalnego \<parametername> jest niezgodny ze specyfikacją CLS</span><span class="sxs-lookup"><span data-stu-id="06ad0-102">Type of optional value for optional parameter \<parametername> is not CLS-compliant</span></span>

<span data-ttu-id="06ad0-103">Procedura jest oznaczona jako, `<CLSCompliant(True)>` ale deklaruje [opcjonalny](../modifiers/optional.md) parametr z wartością domyślną niezgodnego typu.</span><span class="sxs-lookup"><span data-stu-id="06ad0-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>  
  
 <span data-ttu-id="06ad0-104">Aby procedura była zgodna z [niezależnością od języka i składnikami niezależnymi od języka](../../../standard/language-independence-and-language-independent-components.md) (CLS), musi używać tylko typów zgodnych ze specyfikacją CLS.</span><span class="sxs-lookup"><span data-stu-id="06ad0-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="06ad0-105">Dotyczy to typów parametrów, typu zwracanego i typów wszystkich zmiennych lokalnych.</span><span class="sxs-lookup"><span data-stu-id="06ad0-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="06ad0-106">Ma również zastosowanie do domyślnych wartości parametrów opcjonalnych.</span><span class="sxs-lookup"><span data-stu-id="06ad0-106">It also applies to the default values of optional parameters.</span></span>  
  
 <span data-ttu-id="06ad0-107">Następujące Visual Basic typy danych nie są zgodne ze specyfikacją CLS:</span><span class="sxs-lookup"><span data-stu-id="06ad0-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="06ad0-108">SByte, typ danych</span><span class="sxs-lookup"><span data-stu-id="06ad0-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="06ad0-109">UInteger, typ danych</span><span class="sxs-lookup"><span data-stu-id="06ad0-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="06ad0-110">ULong, typ danych</span><span class="sxs-lookup"><span data-stu-id="06ad0-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="06ad0-111">UShort, typ danych</span><span class="sxs-lookup"><span data-stu-id="06ad0-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="06ad0-112">Po zastosowaniu <xref:System.CLSCompliantAttribute> atrybutu do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub, `False` Aby wskazać zgodność lub niezgodność.</span><span class="sxs-lookup"><span data-stu-id="06ad0-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="06ad0-113">Dla tego parametru nie ma wartości domyślnej i należy podać wartość.</span><span class="sxs-lookup"><span data-stu-id="06ad0-113">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="06ad0-114">Jeśli nie ma zastosowania <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.</span><span class="sxs-lookup"><span data-stu-id="06ad0-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="06ad0-115">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="06ad0-115">By default, this message is a warning.</span></span> <span data-ttu-id="06ad0-116">Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="06ad0-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="06ad0-117">**Identyfikator błędu:** BC40042</span><span class="sxs-lookup"><span data-stu-id="06ad0-117">**Error ID:** BC40042</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="06ad0-118">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="06ad0-118">To correct this error</span></span>  
  
- <span data-ttu-id="06ad0-119">Jeśli opcjonalny parametr musi mieć wartość domyślną tego konkretnego typu, Usuń <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="06ad0-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="06ad0-120">Procedura nie może być zgodna ze specyfikacją CLS.</span><span class="sxs-lookup"><span data-stu-id="06ad0-120">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="06ad0-121">Jeśli procedura musi być zgodna ze specyfikacją CLS, Zmień typ tej wartości domyślnej na najbliższy typ zgodny ze specyfikacją CLS.</span><span class="sxs-lookup"><span data-stu-id="06ad0-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="06ad0-122">Na przykład, zamiast `UInteger` można użyć, `Integer` Jeśli nie potrzebujesz zakresu wartości powyżej 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="06ad0-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="06ad0-123">Jeśli potrzebujesz rozszerzonego zakresu, możesz zamienić `UInteger` na `Long` .</span><span class="sxs-lookup"><span data-stu-id="06ad0-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="06ad0-124">Jeśli masz połączenie z obiektami automatyzacji lub COM, pamiętaj, że niektóre typy mają różne szerokości danych niż w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="06ad0-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="06ad0-125">Na przykład `int` często jest 16 bitów w innych środowiskach.</span><span class="sxs-lookup"><span data-stu-id="06ad0-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="06ad0-126">Jeśli zaakceptujesz 16-bitową liczbę całkowitą z tego składnika, zadeklaruj ją jako `Short` zamiast `Integer` w kodzie zarządzanym Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="06ad0-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
