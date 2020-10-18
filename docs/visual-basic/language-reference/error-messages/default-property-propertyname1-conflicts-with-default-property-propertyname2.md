---
title: Właściwość domyślna „<propertyname1>" powoduje konflikt z właściwością domyślną „<propertyname2>” w „<classname>" i dlatego należy ją zadeklarować jako „Shadows”
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 290971a3173c59f08fbd279b6fffe3bcb618cb72
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160610"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="f1a5e-102">BC40007: Właściwość domyślna " \<propertyname1> " powoduje konflikt z właściwością domyślną " \<propertyname2> " w elemencie " \<classname> " i dlatego powinna być zadeklarowana jako "Shadows"</span><span class="sxs-lookup"><span data-stu-id="f1a5e-102">BC40007: Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>

<span data-ttu-id="f1a5e-103">Właściwość jest zadeklarowana z taką samą nazwą jak Właściwość zdefiniowana w klasie bazowej.</span><span class="sxs-lookup"><span data-stu-id="f1a5e-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="f1a5e-104">W tej sytuacji właściwość w tej klasie powinna zasłaniać właściwość klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="f1a5e-104">In this situation, the property in this class should shadow the base class property.</span></span>

 <span data-ttu-id="f1a5e-105">Ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="f1a5e-105">This message is a warning.</span></span> <span data-ttu-id="f1a5e-106">`Shadows` jest domyślnie przyjmowana.</span><span class="sxs-lookup"><span data-stu-id="f1a5e-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="f1a5e-107">Aby uzyskać więcej informacji na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędów, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f1a5e-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="f1a5e-108">**Identyfikator błędu:** BC40007</span><span class="sxs-lookup"><span data-stu-id="f1a5e-108">**Error ID:** BC40007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f1a5e-109">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="f1a5e-109">To correct this error</span></span>

- <span data-ttu-id="f1a5e-110">Dodaj `Shadows` słowo kluczowe do deklaracji lub Zmień nazwę zadeklarowanej właściwości.</span><span class="sxs-lookup"><span data-stu-id="f1a5e-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1a5e-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f1a5e-111">See also</span></span>

- [<span data-ttu-id="f1a5e-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="f1a5e-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="f1a5e-113">Przesłanianie w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1a5e-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
