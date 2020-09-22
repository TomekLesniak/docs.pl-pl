---
title: Szacowanie funkcji zostało wyłączone, ponieważ poprzednie szacowanie przekroczyło limit czasu
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 9bdc12e3dc57b440ed9f304201b8ec401db37871
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874070"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Szacowanie funkcji zostało wyłączone, ponieważ poprzednie szacowanie przekroczyło limit czasu

Obliczanie funkcji jest wyłączone, ponieważ Przekroczono limit czasu obliczania poprzedniej funkcji. Aby ponownie włączyć szacowanie funkcji, ponownie wykonaj krok lub ponownie uruchom debugowanie.  
  
 W debugerze programu Visual Studio wyrażenie określa wywołanie procedury, ale inna Ocena przekroczyła limit czasu.  
  
 Możliwe przyczyny wywołania procedury przekroczenia limitu czasu obejmują nieskończoną pętlę lub *nieskończoną pętlę*. Aby uzyskać więcej informacji, zobacz [dla... Next — instrukcja](../statements/for-next-statement.md).  
  
 Szczególnym przypadkiem nieskończoności pętli jest *rekursja*. Aby uzyskać więcej informacji, zobacz [procedury cykliczne](../../programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Identyfikator błędu:** BC30957  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Jeśli to możliwe, ustal, jakie poprzednie funkcje oceny były i co spowodowało przekroczenie limitu czasu. W przeciwnym razie ten błąd może się pojawić ponownie.  
  
2. Ponownie wykonaj debuger lub Przerwij i ponownie uruchom debugowanie.  
  
## <a name="see-also"></a>Zobacz też

- [Debugowanie w Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Nawigowanie po kodzie za pomocą debugera](/visualstudio/debugger/navigating-through-code-with-the-debugger)
