---
title: Wizualne śledzenie przepływu pracy
ms.date: 03/30/2017
ms.assetid: 0143448f-2044-40a0-8a3d-941f6d12468b
ms.openlocfilehash: 4c6e0c1bc4bb9d017a3341f165409ff3e427ed01
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267575"
---
# <a name="visual-workflow-tracking"></a>Wizualne śledzenie przepływu pracy

Ten przykład pokazuje, jak napisać aplikację wizualną śledzenia przepływu pracy przy użyciu funkcji debugowania dostępnej za pośrednictwem [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] .

## <a name="sample-details"></a>Przykładowe szczegóły

 Aplikacja wykonuje prosty przepływ pracy Flowchart (zdefiniowany w przepływie pracy. XAML) i ponownie hostuje projektanta przepływu pracy w celu wyświetlenia aktualnie wykonywanego przepływu pracy. Gdy przepływ pracy jest wykonywany, aktualnie wykonywane działanie jest pokazane przy użyciu żółtego konturu i strzałki debugowania. Ponadto rekordy śledzenia wygenerowane przez przepływ pracy są również wyświetlane w oknie aplikacji. Aby uzyskać więcej informacji na temat śledzenia przepływu pracy, zobacz [śledzenie i śledzenie przepływu pracy](../workflow-tracking-and-tracing.md). Aby uzyskać więcej informacji o ponownym udostępnianiu projektanta przepływu pracy, zobacz artykuł ponowne [hostowanie Projektant przepływu pracy](../rehosting-the-workflow-designer.md).

 Symulator przepływu pracy działa przez utrzymywanie dwóch słowników. Jeden z nich zawiera mapowanie między aktualnie wykonywanym obiektem działania a numerem wiersza XAML, w którym jest tworzone wystąpienie działania. Drugi zawiera mapowanie między IDENTYFIKATORem wystąpienia działania a obiektem działania. W przypadku emisji rekordów śledzenia przy użyciu niestandardowego profilu śledzenia aplikacja określa identyfikator wystąpienia aktualnie wykonywanego działania i mapuje go z powrotem do pliku XAML, który go tworzy. Projektant przepływu pracy przekazujący jest następnie wyróżniać działanie na powierzchni projektanta i używać tej samej metody jak debuger przepływu pracy, a w odniesieniu do zaznaczenia żółtego obramowania wokół działania i wyświetlania żółtej strzałki wzdłuż lewej krawędzi projektanta.

#### <a name="to-use-this-sample"></a>Aby użyć tego przykładu

1. Otwórz plik WorkflowSimulator. sln z przykładowego katalogu w programie Visual Studio 2010.

2. Naciśnij kombinację klawiszy CTRL+SHIFT+B w celu skompilowania rozwiązania.

3. Naciśnij klawisze CTRL + F5, aby uruchomić przykład. Spowoduje to wyświetlenie pliku Workflow. XAML w oknie rehostowanie projektanta przepływu pracy.

4. Kliknij menu **plik** i wybierz polecenie **Uruchom przepływ pracy.**...

5. Zauważ, że aktualnie wykonywane działanie zostało wyróżnione zgodnie z opisem wcześniej, a śledzone rekordy są wyświetlane po prawej stronie okna aplikacji.

6. Po zakończeniu przepływu pracy można kliknąć dowolny z rekordów śledzenia, aby sprawdzić, które działanie odnosi się do.

> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\VisualWorkflowTracking`
