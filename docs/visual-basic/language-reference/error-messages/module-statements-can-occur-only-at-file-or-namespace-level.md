---
title: Instrukcje „Module” mogą wystąpić tylko na poziomie pliku lub przestrzeni nazw
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 91e6c81bb64c259411cbef8a36629b8b320ea584
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873751"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a>Instrukcje „Module” mogą wystąpić tylko na poziomie pliku lub przestrzeni nazw

`Module` instrukcje muszą pojawić się w górnej części pliku źródłowego bezpośrednio po `Option` i `Imports` instrukcjach, atrybutach globalnych i deklaracjach przestrzeni nazw, ale przed wszystkimi innymi deklaracjami.  
  
 **Identyfikator błędu:** BC30617  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Przenieś `Module` instrukcję do początku deklaracji przestrzeni nazw lub pliku źródłowego.  
  
## <a name="see-also"></a>Zobacz też

- [Module — Instrukcja](../statements/module-statement.md)
