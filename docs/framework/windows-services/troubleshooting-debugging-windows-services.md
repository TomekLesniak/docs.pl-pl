---
title: 'Rozwiązywanie problemów: debugowanie usług systemu Windows'
description: Wprowadzenie do debugowania usług systemu Windows. Gdy debugujesz aplikację usługi systemu Windows, usługa i Service Manager systemu Windows współpracują.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
ms.openlocfilehash: 2c1180ef8e3e44c50f10a263d86dcae830d9cd0e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270396"
---
# <a name="troubleshooting-debugging-windows-services"></a>Rozwiązywanie problemów: debugowanie usług systemu Windows

Gdy debugujesz aplikację usługi systemu Windows, usługa i **Service Manager systemu Windows** współpracują. **Service Manager** uruchamia usługę <xref:System.ServiceProcess.ServiceBase.OnStart%2A> , wywołując metodę, a następnie czeka 30 sekund na <xref:System.ServiceProcess.ServiceBase.OnStart%2A> zwrócenie metody. Jeśli metoda nie zwróci tego czasu, Menedżer pokazuje błąd, że nie można uruchomić usługi.  
  
 Podczas debugowania <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metody zgodnie z opisem w [instrukcje: debugowanie aplikacji usługi systemu Windows](how-to-debug-windows-service-applications.md), musisz mieć świadomość tego 30-sekundowego okresu. Jeśli umieścisz punkt przerwania w <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodzie i nie ustawisz go w ciągu 30 sekund, Menedżer nie uruchomi usługi.  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Debugowanie aplikacji usług systemu Windows](how-to-debug-windows-service-applications.md)
- [Wprowadzenie do aplikacji usług systemu Windows](introduction-to-windows-service-applications.md)
