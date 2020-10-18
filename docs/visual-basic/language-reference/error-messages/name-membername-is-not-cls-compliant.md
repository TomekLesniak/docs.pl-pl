---
title: Nazwa <membername> jest niezgodna ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 43fff3f12295f3837148b0a349887e8405126819
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160239"
---
# <a name="bc40031-name-membername-is-not-cls-compliant"></a><span data-ttu-id="59a60-102">BC40031: nazwa \<membername> jest niezgodna ze specyfikacją CLS</span><span class="sxs-lookup"><span data-stu-id="59a60-102">BC40031: Name \<membername> is not CLS-compliant</span></span>

<span data-ttu-id="59a60-103">Zestaw jest oznaczony jako, `<CLSCompliant(True)>` ale uwidacznia element członkowski o nazwie rozpoczynającej się od znaku podkreślenia ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="59a60-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>

 <span data-ttu-id="59a60-104">Element programowania może zawierać jeden lub więcej podkreśleń, ale w celu uzyskania zgodności z [niezależnymi od języka i składnikami Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS) nie może zaczynać się od znaku podkreślenia.</span><span class="sxs-lookup"><span data-stu-id="59a60-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="59a60-105">Zobacz [zadeklarowane nazwy elementów](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="59a60-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

 <span data-ttu-id="59a60-106">Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub `False` w celu wskazania zgodności lub niezgodności.</span><span class="sxs-lookup"><span data-stu-id="59a60-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="59a60-107">Dla tego parametru nie ma wartości domyślnej i należy podać wartość.</span><span class="sxs-lookup"><span data-stu-id="59a60-107">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="59a60-108">Jeśli nie zastosujesz <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.</span><span class="sxs-lookup"><span data-stu-id="59a60-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="59a60-109">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="59a60-109">By default, this message is a warning.</span></span> <span data-ttu-id="59a60-110">Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="59a60-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="59a60-111">**Identyfikator błędu:** BC40031</span><span class="sxs-lookup"><span data-stu-id="59a60-111">**Error ID:** BC40031</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="59a60-112">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="59a60-112">To correct this error</span></span>

- <span data-ttu-id="59a60-113">Jeśli masz kontrolę nad kodem źródłowym, Zmień nazwę elementu członkowskiego tak, aby nie zaczynała się od znaku podkreślenia.</span><span class="sxs-lookup"><span data-stu-id="59a60-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>

- <span data-ttu-id="59a60-114">Jeśli wymagasz, aby nazwa elementu członkowskiego pozostała niezmieniona, Usuń <xref:System.CLSCompliantAttribute> z jej definicji lub oznacz ją jako `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="59a60-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="59a60-115">Można nadal oznaczyć zestaw jako `<CLSCompliant(True)>` .</span><span class="sxs-lookup"><span data-stu-id="59a60-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="59a60-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="59a60-116">See also</span></span>

- [<span data-ttu-id="59a60-117">Nazwy zadeklarowanych elementów</span><span class="sxs-lookup"><span data-stu-id="59a60-117">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="59a60-118">Visual Basic — Konwencje nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="59a60-118">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
