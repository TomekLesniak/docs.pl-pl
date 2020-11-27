---
title: Tworzenie działań przepływu pracy przy użyciu klasy Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 21f1c8b1249d41029fa7a19360e96ad866c823a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293848"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Tworzenie działań przepływu pracy przy użyciu klasy Activity

Najbardziej podstawowym sposobem utworzenia działania przy użyciu Windows Workflow Foundation (WF) w programie [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] jest utworzenie klasy, która dziedziczy po <xref:System.Activities.Activity> utworzeniu funkcji przez złożenie niestandardowych działań lub działań z [wbudowanej biblioteki działań](net-framework-4-5-built-in-activity-library.md). W tym temacie pokazano, jak utworzyć działanie, które zapisuje dwa komunikaty w konsoli programu.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Aby utworzyć działanie niestandardowe przy użyciu projektanta działań

1. Otwórz program Visual Studio 2012.

2. Wybierz plik, nowy, projekt. Wybierz pozycję **Workflow 4,0** w obszarze **Visual C#** w oknie **typy projektów** , a następnie wybierz węzeł **V2010** . Wybierz pozycję **Biblioteka działań** w oknie **Szablony** . Nadaj nazwę nowej powitaniu projektu.

3. Otwórz nowe działanie.  Przeciągnij <xref:System.Activities.Statements.Sequence> działanie z przybornika na powierzchnię projektanta.

4. Przeciągnij <xref:System.Activities.Statements.WriteLine> działanie do <xref:System.Activities.Statements.Sequence> działania. Wprowadź `"Hello World"` (z cudzysłowami) w polu **tekstowym** .

5. Przeciągnij drugie <xref:System.Activities.Statements.WriteLine> działanie do <xref:System.Activities.Statements.Sequence> działania poniżej pierwszego. Wprowadź `"Goodbye"` (z cudzysłowami) w polu **tekstowym** .
