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
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>BC40007: Właściwość domyślna " \<propertyname1> " powoduje konflikt z właściwością domyślną " \<propertyname2> " w elemencie " \<classname> " i dlatego powinna być zadeklarowana jako "Shadows"

Właściwość jest zadeklarowana z taką samą nazwą jak Właściwość zdefiniowana w klasie bazowej. W tej sytuacji właściwość w tej klasie powinna zasłaniać właściwość klasy bazowej.

 Ten komunikat jest ostrzeżeniem. `Shadows` jest domyślnie przyjmowana. Aby uzyskać więcej informacji na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędów, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identyfikator błędu:** BC40007

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Dodaj `Shadows` słowo kluczowe do deklaracji lub Zmień nazwę zadeklarowanej właściwości.

## <a name="see-also"></a>Zobacz też

- [Shadows](../modifiers/shadows.md)
- [Przesłanianie w Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
