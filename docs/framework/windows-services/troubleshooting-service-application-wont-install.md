---
title: 'Rozwiązywanie problemów: Aplikacja usług nie instaluje się'
description: Rozwiązywanie problemów, jeśli aplikacja usługi nie zostanie zainstalowana. Upewnij się, że właściwość ServiceName klasy Service została prawidłowo ustawiona.
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
ms.openlocfilehash: 02ac95c22007caa6e30300fb8a98178f11cecd14
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270357"
---
# <a name="troubleshooting-service-application-wont-install"></a>Rozwiązywanie problemów: Aplikacja usług nie instaluje się

Jeśli aplikacja usługi nie zostanie prawidłowo zainstalowana, upewnij się, że <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> Właściwość klasy usługi jest ustawiona na taką samą wartość jak w instalatorze dla tej usługi. Wartość musi być taka sama w obu wystąpieniach, aby można było poprawnie zainstalować usługę.  
  
> [!NOTE]
> Możesz również zapoznać się z dziennikami instalacji, aby uzyskać informacje na temat procesu instalacji.  
  
 Należy również sprawdzić, czy masz już zainstalowaną inną usługę o tej samej nazwie. Aby instalacja powiodła się, nazwy usług muszą być unikatowe.  
  
## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do aplikacji usług systemu Windows](introduction-to-windows-service-applications.md)
