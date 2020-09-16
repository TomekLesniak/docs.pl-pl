---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606616"
---
### <a name="workflow-30-types-are-obsolete"></a>Typy przepływów pracy w wersji 3.0 są przestarzałe

#### <a name="details"></a>Szczegóły

Interfejsy API programu Windows Workflow Foundation (WWF) 3.0 (te z przestrzeni nazw System.Workflow) są obecnie przestarzałe.

#### <a name="suggestion"></a>Sugestia

Zamiast nich należy używać nowych interfejsów API programu WWF 4.0 (w System.Activities). Przykład korzystania z nowych interfejsów API można znaleźć [tutaj](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), a dalsze wskazówki są dostępne [tutaj](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5). Ponieważ interfejsy API WWF 3.0 są nadal obsługiwane, alternatywnym rozwiązaniem może być używanie ich i pominięcie ostrzeżenia podczas kompilacji lub użycie starszego kompilatora.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Duży       |
| Wersja | 4.5         |
| Typ    | Przekierowanie |
