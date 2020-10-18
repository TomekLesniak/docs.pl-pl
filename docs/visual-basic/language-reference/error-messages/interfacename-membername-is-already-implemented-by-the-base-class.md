---
title: Klasa „<interfacename><membername>” jest już zaimplementowana przez klasę podstawową „<baseclassname>”. Przyjęto ponowną implementację elementu „<type>”
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 8137f6b1712b6a0752a991f5a3d598b5f958252c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162820"
---
# <a name="bc42015-interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a>BC42015: " \<interfacename> . \<membername> " jest już zaimplementowany przez klasę bazową " \<baseclassname> ". Przyjęto ponowną implementację elementu „\<type>”

Właściwość, procedura lub zdarzenie w klasie pochodnej używa `Implements` klauzuli określającej element członkowski interfejsu, który jest już zaimplementowany w klasie bazowej.

 Klasa pochodna może zmienić implementację elementu członkowskiego interfejsu, który jest implementowany przez jego klasę bazową. Ta wartość nie jest taka sama jak zastępowanie implementacji klasy podstawowej. Aby uzyskać więcej informacji, zobacz [Implements](../statements/implements-clause.md).

 Domyślnie ten komunikat jest ostrzeżeniem. Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identyfikator błędu:** BC42015

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli zamierzasz ponownie zaimplementować element członkowski interfejsu, nie musisz podejmować żadnych działań. Kod w klasie pochodnej uzyskuje dostęp do zaimplementowanego elementu członkowskiego, chyba że użyjesz `MyBase` słowa kluczowego, aby uzyskać dostęp do implementacji klasy bazowej.

- Jeśli nie zamierzasz przeprowadzić ponownej implementacji elementu członkowskiego interfejsu, Usuń `Implements` klauzulę z właściwości, procedury lub deklaracji zdarzenia.

## <a name="see-also"></a>Zobacz też

- [Interfejsy](../../programming-guide/language-features/interfaces/index.md)
