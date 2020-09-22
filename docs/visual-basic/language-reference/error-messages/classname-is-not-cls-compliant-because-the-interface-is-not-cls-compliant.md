---
title: Element „<classname>” jest niezgodny ze specyfikacją CLS, ponieważ interfejs „<interfacename>”, który implementuje, jest niezgodny ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: a482d14094a3fa86b56ca84af46c45e6093416c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874631"
---
# <a name="classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a><span data-ttu-id="a17b5-102">Element „\<classname>” jest niezgodny ze specyfikacją CLS, ponieważ interfejs „\<interfacename>”, który implementuje, jest niezgodny ze specyfikacją CLS</span><span class="sxs-lookup"><span data-stu-id="a17b5-102">'\<classname>' is not CLS-compliant because the interface '\<interfacename>' it implements is not CLS-compliant</span></span>

<span data-ttu-id="a17b5-103">Klasa lub interfejs jest oznaczony jako, `<CLSCompliant(True)>` gdy pochodzi z lub implementuje typ, który jest oznaczony jako `<CLSCompliant(False)>` lub nie jest oznaczony.</span><span class="sxs-lookup"><span data-stu-id="a17b5-103">A class or interface is marked as `<CLSCompliant(True)>` when it derives from or implements a type that is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="a17b5-104">Aby Klasa lub interfejs były zgodne z [niezależnością od języka i składnikami niezależnymi od języka](../../../standard/language-independence-and-language-independent-components.md) (CLS), jego cała Hierarchia dziedziczenia musi być zgodna.</span><span class="sxs-lookup"><span data-stu-id="a17b5-104">For a class or interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), its entire inheritance hierarchy must be compliant.</span></span> <span data-ttu-id="a17b5-105">Oznacza to, że każdy typ, z którego dziedziczy, bezpośrednio lub pośrednio, musi być zgodny.</span><span class="sxs-lookup"><span data-stu-id="a17b5-105">That means every type from which it inherits, directly or indirectly, must be compliant.</span></span> <span data-ttu-id="a17b5-106">Podobnie, jeśli klasa implementuje jeden lub więcej interfejsów, muszą one być zgodne w całej hierarchii dziedziczenia.</span><span class="sxs-lookup"><span data-stu-id="a17b5-106">Similarly, if a class implements one or more interfaces, they must all be compliant throughout their inheritance hierarchies.</span></span>  
  
 <span data-ttu-id="a17b5-107">Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub `False` w celu wskazania zgodności lub niezgodności.</span><span class="sxs-lookup"><span data-stu-id="a17b5-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="a17b5-108">Dla tego parametru nie ma wartości domyślnej i należy podać wartość.</span><span class="sxs-lookup"><span data-stu-id="a17b5-108">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="a17b5-109">Jeśli nie zastosujesz <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.</span><span class="sxs-lookup"><span data-stu-id="a17b5-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="a17b5-110">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="a17b5-110">By default, this message is a warning.</span></span> <span data-ttu-id="a17b5-111">Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a17b5-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a17b5-112">**Identyfikator błędu:** BC40029</span><span class="sxs-lookup"><span data-stu-id="a17b5-112">**Error ID:** BC40029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a17b5-113">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="a17b5-113">To correct this error</span></span>  
  
- <span data-ttu-id="a17b5-114">Jeśli wymagana jest zgodność ze specyfikacją CLS, należy zdefiniować ten typ w ramach innej hierarchii dziedziczenia lub schematu implementacji.</span><span class="sxs-lookup"><span data-stu-id="a17b5-114">If you require CLS compliance, define this type within a different inheritance hierarchy or implementation scheme.</span></span>  
  
- <span data-ttu-id="a17b5-115">Jeśli potrzebujesz, aby ten typ pozostał w bieżącej hierarchii dziedziczenia lub schemat implementacji, Usuń <xref:System.CLSCompliantAttribute> z jego definicji lub Oznacz jako `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="a17b5-115">If you require that this type remain within its current inheritance hierarchy or implementation scheme, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
