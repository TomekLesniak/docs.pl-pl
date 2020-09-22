---
title: Procedura lub funkcja nie jest zdefiniowana
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 24e290ce1193cd6bc6a0ec8985902576332423f2
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870518"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Procedura lub funkcja nie jest zdefiniowana

A `Sub` lub `Function` musi być zdefiniowana, aby można było ją wywołać. Możliwe przyczyny tego błędu to:  
  
- Błędna pisownia nazwy procedury.  
  
- Próba wywołania procedury z innego projektu bez jawnego dodania odwołania do tego projektu w oknie dialogowym **odwołania** .  
  
- Określanie procedury, która nie jest widoczna dla procedury wywołującej.  
  
- Deklarowanie procedury biblioteki dołączanej dynamicznie (DLL) systemu Windows lub procedury kodu dla systemu Macintosh, która nie znajduje się w określonej bibliotece lub zasobie kodu.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że nazwa procedury jest wpisana poprawnie.  
  
2. Znajdź nazwę projektu zawierającego procedurę, która ma zostać wywołana, w oknie dialogowym **odwołania** . Jeśli nie jest wyświetlany, kliknij przycisk **Przeglądaj** , aby go wyszukać. Zaznacz pole wyboru po lewej stronie nazwy projektu, a następnie kliknij przycisk **OK**.  
  
3. Sprawdź nazwę procedury.  
  
## <a name="see-also"></a>Zobacz też

- [Typy błędów](../../programming-guide/language-features/error-types.md)
- [Zarządzanie odwołaniami w projekcie](/visualstudio/ide/managing-references-in-a-project)
- [Sub, instrukcja](../statements/sub-statement.md)
- [Function, instrukcja](../statements/function-statement.md)
