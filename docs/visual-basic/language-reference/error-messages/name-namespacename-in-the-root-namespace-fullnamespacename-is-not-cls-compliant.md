---
title: Nazwa <namespacename> w głównej przestrzeni nazw <fullnamespacename> jest niezgodna ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 4e29a27841021b0cf68af01f4535e60eeb38b9a8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871520"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="48e09-102">Nazwa \<namespacename> w głównej przestrzeni nazw \<fullnamespacename> jest niezgodna ze specyfikacją CLS</span><span class="sxs-lookup"><span data-stu-id="48e09-102">Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>

<span data-ttu-id="48e09-103">Zestaw jest oznaczony jako `<CLSCompliant(True)>` , ale element nazwy głównej przestrzeni nazw zaczyna się od znaku podkreślenia ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="48e09-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="48e09-104">Element programowania może zawierać jeden lub więcej podkreśleń, ale w celu uzyskania zgodności z [niezależnymi od języka i składnikami niezależnymi od języka](../../../standard/language-independence-and-language-independent-components.md) (CLS) nie może zaczynać się od znaku podkreślenia.</span><span class="sxs-lookup"><span data-stu-id="48e09-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="48e09-105">Zobacz [zadeklarowane nazwy elementów](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="48e09-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="48e09-106">Po zastosowaniu <xref:System.CLSCompliantAttribute> do elementu programistycznego, należy ustawić `isCompliant` parametr atrybutu na wartość `True` lub `False` w celu wskazania zgodności lub niezgodności.</span><span class="sxs-lookup"><span data-stu-id="48e09-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="48e09-107">Dla tego parametru nie ma wartości domyślnej i należy podać wartość.</span><span class="sxs-lookup"><span data-stu-id="48e09-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="48e09-108">Jeśli nie zastosujesz <xref:System.CLSCompliantAttribute> do elementu, jest on uznawany za niezgodny.</span><span class="sxs-lookup"><span data-stu-id="48e09-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="48e09-109">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="48e09-109">By default, this message is a warning.</span></span> <span data-ttu-id="48e09-110">Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="48e09-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="48e09-111">**Identyfikator błędu:** BC40039</span><span class="sxs-lookup"><span data-stu-id="48e09-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="48e09-112">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="48e09-112">To correct this error</span></span>  
  
- <span data-ttu-id="48e09-113">Jeśli jest wymagana zgodność ze specyfikacją CLS, Zmień nazwę głównej przestrzeni nazw, tak aby żaden z jej elementów nie zaczynał się od znaku podkreślenia.</span><span class="sxs-lookup"><span data-stu-id="48e09-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
- <span data-ttu-id="48e09-114">Jeśli potrzebujesz, aby nazwa przestrzeni nazw pozostała niezmieniona, Usuń <xref:System.CLSCompliantAttribute> z zestawu lub oznacz ją jako `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="48e09-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e09-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="48e09-115">See also</span></span>

- [<span data-ttu-id="48e09-116">Namespace — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="48e09-116">Namespace Statement</span></span>](../statements/namespace-statement.md)
- [<span data-ttu-id="48e09-117">Przestrzenie nazw w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48e09-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="48e09-118">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="48e09-118">-rootnamespace</span></span>](../../reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="48e09-119">Strona aplikacji, Projektant projektu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48e09-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="48e09-120">Nazwy zadeklarowanych elementów</span><span class="sxs-lookup"><span data-stu-id="48e09-120">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="48e09-121">Visual Basic — Konwencje nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="48e09-121">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
