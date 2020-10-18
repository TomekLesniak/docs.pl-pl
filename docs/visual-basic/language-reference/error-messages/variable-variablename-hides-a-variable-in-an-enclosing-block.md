---
title: Zmienna „<variablename>” ukrywa zmienną w otaczającym bloku
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 408acaafd5e266266b5191313611b94b72a5c270
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161351"
---
# <a name="bc30616-variable-variablename-hides-a-variable-in-an-enclosing-block"></a>BC30616: zmienna " \<variablename> " ukrywa zmienną w otaczającym bloku

Zmienna ujęta w bloku ma taką samą nazwę jak inna zmienna lokalna.

 **Identyfikator błędu:** BC30616

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zmień nazwę zmiennej w załączonym bloku, tak aby nie była taka sama jak jakakolwiek inna zmienna lokalna. Na przykład:

    ```vb
    Dim a, b, x As Integer
    If a = b Then
       Dim y As Integer = 20 ' Uniquely named block variable.
    End If
    ```

- Typową przyczyną tego błędu jest użycie `Catch e As Exception` wewnątrz procedury obsługi zdarzeń. W takim przypadku należy nazwać `Catch` zmienną bloku `ex` zamiast `e` .

- Innym wspólnym źródłem tego błędu jest próba uzyskania dostępu do zmiennej lokalnej zadeklarowanej w `Try` bloku w oddzielnym `Catch` bloku. Aby to poprawić, zadeklaruj zmienną poza `Try...Catch...Finally` strukturą.

## <a name="see-also"></a>Zobacz też

- [Try...Catch...Finally, instrukcja](../statements/try-catch-finally-statement.md)
- [Deklaracja zmiennej](../../programming-guide/language-features/variables/variable-declaration.md)
