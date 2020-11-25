---
title: Wskazówki dotyczące migracji
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: b9b90aedc06fb4a4564596d61aa0ac2dc4c6143f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733597"
---
# <a name="migration-guidance"></a>Wskazówki dotyczące migracji

W .NET Framework 4 firma Microsoft udostępnia drugą wersję główną Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] wydano w usłudze WinFX (w tym do typów w przestrzeni nazw System. Workflow. \* Namespaces; teraz określana jako WF3) i ulepszonych w .NET Framework 3,5. WF3 jest również częścią .NET Framework 4, ale istnieje tam, gdzie jest to nowa technologia przepływu pracy (typy w System. Activities. \* Namespaces; określane jako WF4). Biorąc pod uwagę, kiedy należy wdrożyć WF4, ważne jest, aby najpierw rozpoznać, czy należy kontrolować czas.

- WF3 jest w pełni obsługiwaną częścią .NET Framework 4.

- Aplikacje WF3 są uruchamiane na .NET Framework 4 bez modyfikacji i nadal będą w pełni obsługiwane.

- Można tworzyć nowe aplikacje WF3, a istniejące aplikacje można edytować w programie Visual Studio 2012 i są w pełni obsługiwane.

 W związku z tym decyzja o przyjęciu .NET Framework 4 jest oddzielona od decyzji o przejściu do WF4 (System. Activities. \* ) z WF3 (System. Workflow. \* ). Ten temat zawiera linki do wskazówek dotyczących migracji programu WF, które zawierają informacje na temat pracy z WF3 i WF4.

## <a name="wf-migration-white-papers-and-cookbooks"></a>Oficjalne dokumenty dotyczące migracji WF i podręczniki

 Temat [Omówienie migracji WF](/previous-versions/appfabric/ff383417(v=azure.10)) zawiera obszerne Omówienie relacji między WF3 i WF4 i strategiami migracji. Tematy pomocnicze przechodzenie do szczegółów określonych tematów.

 [Omówienie migracji WF](/previous-versions/appfabric/ff383417(v=azure.10)) Opisuje relację między WF3 i WF4 i opcjami, które są dostępne jako użytkownik lub potencjalni użytkownicy technologii przepływu pracy w .NET Framework 4.

 [Migracja WF: najlepsze rozwiązania dotyczące programowania WF3](/previous-versions/appfabric/ff383417(v=azure.10)) W tym artykule omówiono sposób projektowania artefaktów WF3, dzięki czemu można łatwiej migrować je do WF4.

 [Wskazówki dotyczące WF: reguły](/previous-versions/appfabric/ff383417(v=azure.10)) W tym artykule omówiono sposób przenoszenia inwestycji związanych z regułami do .NET Framework 4 rozwiązań.

 [Wskazówki dotyczące WF: automat Stanów](/previous-versions/appfabric/ff383417(v=azure.10)) Omówienie modelowania przepływu sterowania WF4 w przypadku braku działania State-Machine.

 Należy zauważyć, że te wskazówki dotyczą tylko projektów przepływu pracy przeznaczonych dla .NET Framework 4. Przepływy pracy automatu Stanów zostały dodane w .NET Framework 4.0.1 z wydaniem aktualizacji platformy 1 i zostały dołączone jako część .NET Framework 4,5. Aby uzyskać więcej informacji o przepływach pracy automatu stanów w .NET Framework 4.0.1-4.0.3 i .NET Framework 4,5, zobacz temat [Update 4.0.1 for Microsoft .NET Framework 4 Features](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) and [State Machines](state-machine-workflows.md).

 [Cookbook migracji WF: działania niestandardowe](/previous-versions/appfabric/ff383417(v=azure.10)) Zawiera przykłady i instrukcje dotyczące ponownego projektowania działań niestandardowych WF3 na WF4.

 [Cookbook migracji WF: Zaawansowane działania niestandardowe](/previous-versions/appfabric/ff383417(v=azure.10)) Zawiera wskazówki dotyczące ponownego projektowania zaawansowanych działań WF3, które korzystają z kolejek WF3 i planowania działań podrzędnych jako WF4 działań niestandardowych.

 [Cookbook migracji WF: przepływy pracy](/previous-versions/appfabric/ff383417(v=azure.10)) Zawiera przykłady i instrukcje dotyczące przeprojektowania przepływów pracy WF3 na WF4.

 [Cookbook migracji WF: hosting przepływu pracy](/previous-versions/appfabric/ff383417(v=azure.10)) Zawiera wskazówki dotyczące przeprojektowania kodu hostingu WF3 jako WF4 kodu hostingu. Celem jest pokrycie najważniejszych różnic między WF3 i WF4.

 [Cookbook migracji WF: śledzenie przepływu pracy](/previous-versions/appfabric/ff383417(v=azure.10)) Zawiera wskazówki dotyczące przeprojektowania kodu śledzenia WF3 i konfiguracji przy użyciu równoważnego kodu śledzenia WF4 i konfiguracji.

 [Wskazówki dotyczące WF: usługi przepływu pracy](/previous-versions/appfabric/ff383417(v=azure.10)) Zawiera przykładowe instrukcje krok po kroku dotyczące ponownego projektowania przepływów pracy, które implementują usługi sieci Web programu Windows Communication Foundation (WCF), które są tworzone w WF3 do używania WF4, w przypadku typowych scenariuszy dla działań gotowych do użycia.

## <a name="see-also"></a>Zobacz także

- <xref:System.Activities.Statements.Interop>
