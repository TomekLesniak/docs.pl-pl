---
title: Element „<proceduresignature1>” nie jest zgodny ze specyfikacją CLS, ponieważ przeciąża element „<proceduresignature2>”, który różni się od niego tylko tablicą typów parametrów tablicowych lub rangą typów parametrów tablicowych
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 5376f0513b1180da511a508cf8e0e754e8938384
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159797"
---
# <a name="bc40035-proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="4c072-102">BC40035: \<proceduresignature1> jest niezgodna ze specyfikacją CLS, ponieważ przeciążania \<proceduresignature2> , które różnią się od niego tylko tablicą typów parametrów tablicowych lub według rangi typów parametrów tablicy</span><span class="sxs-lookup"><span data-stu-id="4c072-102">BC40035: \<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>

<span data-ttu-id="4c072-103">Procedura lub właściwość jest oznaczona jako, `<CLSCompliant(True)>` gdy zastępuje inną procedurę lub właściwość i jedyną różnicą między ich listami parametrów jest poziom zagnieżdżenia tablicy nieregularnej lub rangi tablicy.</span><span class="sxs-lookup"><span data-stu-id="4c072-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>

 <span data-ttu-id="4c072-104">W poniższych deklaracjach druga i trzecia deklaracja generują ten błąd:</span><span class="sxs-lookup"><span data-stu-id="4c072-104">In the following declarations, the second and third declarations generate this error:</span></span>

 `Overloads Sub ProcessArray(arrayParam() As Integer)`

 `Overloads Sub ProcessArray(arrayParam()() As Integer)`

 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`

 <span data-ttu-id="4c072-105">Druga Deklaracja powoduje zmianę oryginalnego parametru jednowymiarowego `arrayParam` na tablicę tablic.</span><span class="sxs-lookup"><span data-stu-id="4c072-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="4c072-106">Trzecia deklaracja zmienia `arrayParam` się w tablicę dwuwymiarową (ranga 2).</span><span class="sxs-lookup"><span data-stu-id="4c072-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="4c072-107">Chociaż Visual Basic zezwala na przeciążenia tylko jednej z tych zmian, takie Przeciążenie nie jest zgodne z [niezależną od języka i składnikami Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="4c072-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>

 <span data-ttu-id="4c072-108">Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub `False` w celu wskazania zgodności lub niezgodności.</span><span class="sxs-lookup"><span data-stu-id="4c072-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="4c072-109">Dla tego parametru nie ma wartości domyślnej i należy podać wartość.</span><span class="sxs-lookup"><span data-stu-id="4c072-109">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="4c072-110">Jeśli nie zastosujesz <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.</span><span class="sxs-lookup"><span data-stu-id="4c072-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="4c072-111">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="4c072-111">By default, this message is a warning.</span></span> <span data-ttu-id="4c072-112">Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4c072-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="4c072-113">**Identyfikator błędu:** BC40035</span><span class="sxs-lookup"><span data-stu-id="4c072-113">**Error ID:** BC40035</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4c072-114">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="4c072-114">To correct this error</span></span>

- <span data-ttu-id="4c072-115">Jeśli jest wymagana zgodność ze specyfikacją CLS, zdefiniuj przeciążenia tak, aby różnią się od siebie na więcej sposobów niż zmiany wprowadzone na tej stronie pomocy.</span><span class="sxs-lookup"><span data-stu-id="4c072-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>
- <span data-ttu-id="4c072-116">Jeśli wymagane jest, aby przeciążenia różniły się tylko zmianami wprowadzonymi na tej stronie pomocy, należy usunąć <xref:System.CLSCompliantAttribute> z ich definicji lub oznaczyć je jako `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="4c072-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c072-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4c072-117">See also</span></span>

- [<span data-ttu-id="4c072-118">Przeciążanie procedury</span><span class="sxs-lookup"><span data-stu-id="4c072-118">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="4c072-119">Przeciążenia</span><span class="sxs-lookup"><span data-stu-id="4c072-119">Overloads</span></span>](../modifiers/overloads.md)
