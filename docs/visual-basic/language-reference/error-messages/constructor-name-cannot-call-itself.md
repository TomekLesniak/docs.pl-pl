---
title: Konstruktor „<name>” nie może wywołać sam siebie
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: f40319cde8388b17e27cfaec2117ebd519ebd4ff
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160948"
---
# <a name="bc30298-constructor-name-cannot-call-itself"></a>BC30298: Konstruktor " \<name> " nie może wywoływać samego siebie

`Sub New`Procedura w klasie lub strukturze wywołuje sam siebie.

 Celem konstruktora jest zainicjowanie wystąpienia klasy lub struktury, gdy jest ona najpierw tworzona. Klasa lub struktura może mieć kilka konstruktorów, pod warunkiem, że wszystkie mają różne listy parametrów. Konstruktor jest uprawniony do wywołania innego konstruktora, aby wykonywał jego funkcję oprócz własnych. Jednak nie ma to znaczenia dla konstruktora, który wywołuje siebie, i w rzeczywistości spowoduje nieskończoną rekursję, jeśli jest to dozwolone.

 **Identyfikator błędu:** BC30298

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Sprawdź listę parametrów wywoływanego konstruktora. Powinien być różny od konstruktora wywołującego wywołanie.

2. Jeśli nie zamierzasz wywołać innego konstruktora, Usuń `Sub New` wywołanie całkowicie.

## <a name="see-also"></a>Zobacz też

- [Okres istnienia obiektów: w jaki sposób obiekty są tworzone i niszczone](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
