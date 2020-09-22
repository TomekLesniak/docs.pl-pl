---
title: Wznowienie bez błędu
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 6dd6805151de52a5e0cf51c520485c0e8558e0a7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870836"
---
# <a name="resume-without-error"></a>Wznowienie bez błędu

`Resume`Instrukcja pojawiła się poza kodem obsługi błędu lub kod przeskoczy do procedury obsługi błędów, chociaż nie wystąpił błąd.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Przenieś `Resume` instrukcję do procedury obsługi błędów lub usuń ją.  
  
2. Przeskocz do etykiet nie mogą występować w różnych procedurach, więc Wyszukaj w tej procedurze etykietę identyfikującą procedurę obsługi błędów. Jeśli zostanie znaleziona zduplikowana etykieta określona jako obiekt docelowy `GoTo` instrukcji, która nie jest `On Error GoTo` instrukcją, Zmień etykietę wiersza, aby zgadzać się z zamierzonym celem.  
  
## <a name="see-also"></a>Zobacz też

- [Resume — Instrukcja](../statements/resume-statement.md)
- [On Error, instrukcja](../statements/on-error-statement.md)
