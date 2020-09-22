---
title: Nieprawidłowa konwencja wywoływania biblioteki DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 0481bd5e4dfe7a24dff454d0754b519509fa967f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875737"
---
# <a name="bad-dll-calling-convention"></a>Nieprawidłowa konwencja wywoływania biblioteki DLL

Argumenty przekazane do biblioteki dołączanej dynamicznie (DLL) muszą dokładnie pasować do oczekiwanych przez procedurę. Konwencje wywoływania dotyczą liczby, typu i kolejności argumentów. Program może wywołać procedurę w bibliotece DLL, która jest w trakcie przekazywania nieprawidłowego typu lub liczby argumentów.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że wszystkie typy argumentów zgadzają się z tymi określonymi w deklaracji wywoływanej procedury.  
  
2. Upewnij się, że przekazujesz tę samą liczbę argumentów wskazanych w deklaracji wywoływanej procedury.  
  
3. Jeśli procedura DLL oczekuje argumentów przez wartość, upewnij się, że `ByVal` określono dla tych argumentów w deklaracji procedury.  
  
## <a name="see-also"></a>Zobacz też

- [Typy błędów](../../programming-guide/language-features/error-types.md)
- [Call, instrukcja](../statements/call-statement.md)
- [Declare — Instrukcja](../statements/declare-statement.md)
