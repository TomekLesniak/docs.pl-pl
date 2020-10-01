---
title: 'Instrukcje: Wstrzymywanie usługi systemu Windows (Visual Basic)'
description: Przeczytaj, jak używać składnika ServiceController do wstrzymania usługi systemu Windows (na przykład usługi administratora usług IIS) na komputerze lokalnym z Visual Basic.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
ms.openlocfilehash: 19919a8b0a289f0e88eb136d8c010a036e84cbec
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608507"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a>Instrukcje: Wstrzymywanie usługi systemu Windows (Visual Basic)
Ten przykład używa <xref:System.ServiceProcess.ServiceController> składnika do wstrzymania usługi administratora usług IIS na komputerze lokalnym.  
  
## <a name="example"></a>Przykład  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Ten przykład kodu jest również dostępny jako fragment kodu IntelliSense. W selektorze fragmentów kodu znajduje się on w **systemie operacyjnym windows > usług systemu Windows**. Aby uzyskać więcej informacji, zobacz [fragmenty kodu](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
- Odwołanie do projektu do System.serviceprocess.dll.  
  
- Dostęp do elementów członkowskich <xref:System.ServiceProcess> przestrzeni nazw. Dodaj `Imports` instrukcję, jeśli nie masz w pełni kwalifikowanej nazwy elementu członkowskiego w kodzie. Aby uzyskać więcej informacji, zobacz [Imports — Instrukcja (przestrzeń nazw i typ .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 <xref:System.ServiceProcess.ServiceController.MachineName%2A>Właściwość <xref:System.ServiceProcess.ServiceController> klasy jest domyślnie komputerem lokalnym. Aby odwoływać się do usług systemu Windows na innym komputerze, należy zmienić <xref:System.ServiceProcess.ServiceController.MachineName%2A> Właściwość na nazwę tego komputera.  
  
 Następujące warunki mogą spowodować wyjątek:  
  
- Nie można wstrzymać usługi. (<xref:System.InvalidOperationException>)  
  
- Wystąpił błąd podczas uzyskiwania dostępu do interfejsu API systemu. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  
 Kontrolowanie usług na komputerze może być ograniczone przy użyciu programu w <xref:System.ServiceProcess.ServiceControllerPermissionAccess> celu ustawienia uprawnień w <xref:System.ServiceProcess.ServiceControllerPermission> .  
  
 Dostęp do informacji o usłudze może być ograniczony przy użyciu <xref:System.Security.Permissions.PermissionState> do ustawiania uprawnień w <xref:System.Security.Permissions.SecurityPermission> .  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [Instrukcje: Kontynuowanie usługi systemu Windows (Visual Basic)](how-to-continue-a-windows-service-visual-basic.md)
