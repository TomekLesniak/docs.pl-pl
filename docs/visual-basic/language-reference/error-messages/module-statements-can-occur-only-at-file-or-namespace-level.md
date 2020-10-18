---
title: Instrukcje „Module” mogą wystąpić tylko na poziomie pliku lub przestrzeni nazw
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: b946a527d3de3a030ac03691c77afcf440f518ee
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160317"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a>BC30617: instrukcje "module" mogą wystąpić tylko na poziomie pliku lub przestrzeni nazw

`Module` instrukcje muszą pojawić się w górnej części pliku źródłowego bezpośrednio po `Option` i `Imports` instrukcjach, atrybutach globalnych i deklaracjach przestrzeni nazw, ale przed wszystkimi innymi deklaracjami.

 **Identyfikator błędu:** BC30617

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Przenieś `Module` instrukcję do początku deklaracji przestrzeni nazw lub pliku źródłowego.

## <a name="see-also"></a>Zobacz też

- [Module — Instrukcja](../statements/module-statement.md)
