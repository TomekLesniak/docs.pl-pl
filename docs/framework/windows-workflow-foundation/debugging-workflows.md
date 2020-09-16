---
title: Debugowanie przepływów pracy
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 31c688f5f45b41f337176108486ec2074e1915a7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543839"
---
# <a name="debugging-workflows"></a>Debugowanie przepływów pracy

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] oferuje kilka opcji debugowania uruchomionych przepływów pracy w środowisku deweloperskim. Przepływy pracy mogą być debugowane w projektancie, w języku XAML i w kodzie.

## <a name="debugging-in-the-workflow-designer"></a>Debugowanie w Projektant przepływu pracy

Punkty przerwania można ustawić dla działań w Projektancie przepływu pracy przez wyróżnienie działania i naciśnięcie klawisza <kbd>F9</kbd> lub menu kontekstowego działania. Wykonywanie przepływu pracy jest przerywane, gdy host przepływu pracy jest uruchamiany w trybie debugowania. Na poniższym zrzucie ekranu wykonywanie przepływu pracy jest wstrzymywane w punkcie przerwania. Aby uzyskać więcej informacji, zobacz [debugowanie przepływów pracy za pomocą Projektant przepływu pracy](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).

## <a name="debugging-in-xaml"></a>Debugowanie w języku XAML

Jeśli przepływ pracy został wstrzymany w punkcie przerwania w projektancie, można go również debugować w języku XAML. Aby wyświetlić punkt wykonywania w języku XAML, wybierz opcję **Widok XAML** w Projektancie przepływów pracy, gdy wykonywanie przepływu pracy jest wstrzymane. Debugowanie można przełączyć z powrotem do projektanta, otwierając ponownie przepływ pracy w Projektancie z Eksploratora rozwiązań. Aby uzyskać więcej informacji, zobacz [How to: Debug XAML with Projektant przepływu pracy](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).

## <a name="debugging-in-code"></a>Debugowanie w kodzie

Aby ustawić punkt przerwania, kliknij lewy margines okienka kod lub naciśnij klawisz <kbd>F9</kbd> z kursorem w wierszu, w którym chcesz go ustawić.

## <a name="attaching-to-a-workflow-process"></a>Dołączanie do procesu przepływu pracy

Debugowanie przepływu pracy obsługuje również korzystanie z infrastruktury programu Visual Studio w celu dołączenia do procesu. Umożliwia to autorowi przepływu pracy debugowanie przepływu pracy działającego w innym środowisku hosta, takim jak Internet Information Services (IIS) 7,0.

## <a name="remote-debugging"></a>Debugowanie zdalne

Debugowanie zdalne Windows Workflow Foundation (WF) działa tak samo jak debugowanie zdalne dla innych składników programu Visual Studio. Aby uzyskać informacje na temat korzystania z debugowania zdalnego, zobacz [How to: Enable Remote Debug](/previous-versions/visualstudio/visual-studio-2010/febz73k0(v=vs.100)).

> [!NOTE]
> Jeśli aplikacja przepływu pracy jest ukierunkowana na architekturę x86 i jest hostowana na komputerze z uruchomionym 64-bitowym systemem operacyjnym, debugowanie zdalne nie będzie działać, jeśli program Visual Studio nie jest zainstalowany na komputerze zdalnym lub obiekt docelowy dla aplikacji przepływu pracy zostanie zmieniony na **dowolny procesor CPU**.

## <a name="extending-the-workflow-debugging-service"></a>Rozszerzanie usługi debugowania przepływu pracy

Usługa debuggera przepływu pracy jest teraz publiczna i może służyć do tworzenia niestandardowych aplikacji, takich jak monitorowanie, Symulacja i debugowanie w środowisku, w którym jest ponownie hostowany. Aby uzyskać więcej informacji, zobacz <xref:System.Activities.Presentation.Debug.DebuggerService> artykuł.
