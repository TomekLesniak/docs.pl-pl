---
title: Właściwość domyślna „<propertyname1>" powoduje konflikt z właściwością domyślną „<propertyname2>” w „<classname>" i dlatego należy ją zadeklarować jako „Shadows”
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b857a9ae7875a156179602cbe77558333d07b7b9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874513"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>Właściwość domyślna „\<propertyname1>" powoduje konflikt z właściwością domyślną „\<propertyname2>” w „\<classname>" i dlatego należy ją zadeklarować jako „Shadows”

Właściwość jest zadeklarowana z taką samą nazwą jak Właściwość zdefiniowana w klasie bazowej. W tej sytuacji właściwość w tej klasie powinna zasłaniać właściwość klasy bazowej.  
  
 Ten komunikat jest ostrzeżeniem. `Shadows` jest domyślnie przyjmowana. Aby uzyskać więcej informacji na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędów, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identyfikator błędu:** BC40007  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Dodaj `Shadows` słowo kluczowe do deklaracji lub Zmień nazwę zadeklarowanej właściwości.  
  
## <a name="see-also"></a>Zobacz też

- [Shadows](../modifiers/shadows.md)
- [Przesłanianie w Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
