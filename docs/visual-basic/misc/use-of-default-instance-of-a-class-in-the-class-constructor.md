---
title: Użycie domyślnego wystąpienia klasy w konstruktorze klas może prowadzić do nieskończonego wywołania cyklicznego
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 5d239fdb7dcc5c488bf0341043b810ec7dadc083
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100324"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>Użycie domyślnego wystąpienia klasy w konstruktorze klas może prowadzić do nieskończonego wywołania cyklicznego

W konstruktorze klasy użyto domyślnego wystąpienia klasy. Może to prowadzić do nieskończonego wywołania cyklicznego, nazywanego również pętlą nieskończoną.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Usuń wystąpienie domyślne z konstruktora klasy.  
  
## <a name="see-also"></a>Zobacz także

- [Konstruktory](../programming-guide/concepts/object-oriented-programming.md#constructors)
