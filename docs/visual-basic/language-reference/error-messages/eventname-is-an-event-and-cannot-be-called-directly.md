---
title: Element „<eventname>” jest zdarzeniem i nie można go wywołać bezpośrednio
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 246cb92daa2c838c95f695542f33cf02af42764d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161988"
---
# <a name="bc32022-eventname-is-an-event-and-cannot-be-called-directly"></a>BC32022: " \<eventname> " jest zdarzeniem i nie można go wywołać bezpośrednio

"<`eventname`>" jest zdarzeniem i dlatego nie można go wywołać bezpośrednio. Użyj `RaiseEvent` instrukcji, aby zgłosić zdarzenie.

 Wywołanie procedury określa zdarzenie dla nazwy procedury. Procedura obsługi zdarzeń jest procedurą, ale samo zdarzenie jest urządzeniem sygnalizującym, które musi zostać podniesione i obsłużone.

 **Identyfikator błędu:** BC32022

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Użyj `RaiseEvent` instrukcji, aby sygnalizować zdarzenie i wywołać procedury lub procedury, które je obsługują.

## <a name="see-also"></a>Zobacz też

- [RaiseEvent — Instrukcja](../statements/raiseevent-statement.md)
