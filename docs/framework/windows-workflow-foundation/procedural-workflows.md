---
title: Proceduralne przepływy pracy
description: W programie Workflow Foundation przepływy pracy proceduralnej korzystają z metod sterowania przepływem podobnych do tych, które znajdują się w językach proceduralnych.
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 13d1b5e55b84687e2a78db1a94317b8b1e33328c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246033"
---
# <a name="procedural-workflows"></a>Proceduralne przepływy pracy

Proceduralne przepływy pracy używają metod sterowania przepływem podobnych do tych, które znajdują się w językach proceduralnych. Te konstrukcje obejmują `While` i `If` . Te przepływy pracy mogą być swobodnie składane przy użyciu innych działań sterowania przepływem, takich jak <xref:System.Activities.Statements.Flowchart> i <xref:System.Activities.Statements.Sequence> .  
  
## <a name="controlling-execution-flow"></a>Sterowanie przepływem wykonywania  

 Biblioteka działań przepływu pracy ma działania dotyczące modelowania większości metod kontroli przepływu używanych w językach proceduralnych. Są one następujące:  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 Aby korzystać z działań sterowania przepływem, przeciągnij i upuść je z przybornika **działań** do działania złożonego wewnątrz okna projektanta.  
  
> [!NOTE]
> W przypadku używania funkcji hostingu systemu Windows Server AppFabric do hostowania przepływów pracy w kolektywie serwerów, program AppFabric przeniesie wystąpienia między różnymi serwerami programu AppFabric. Wymaga to, aby zasoby mogły być współużytkowane między wszystkimi węzłami.  Żadna z domyślnych działań w ramach przepływu pracy netto 4 nie zawiera żadnych operacji, które uzyskują dostęp do zasobów lokalnych. Ponieważ program AppFabric nie oferuje żadnego mechanizmu, aby oznaczyć przepływ pracy jako nieruchomy, Deweloper nie może tworzyć działań niestandardowych, które kończą się niepowodzeniem podczas przenoszenia przepływu pracy.  
  
## <a name="see-also"></a>Zobacz też

- [Przepływy pracy schematów blokowych](flowchart-workflows.md)
