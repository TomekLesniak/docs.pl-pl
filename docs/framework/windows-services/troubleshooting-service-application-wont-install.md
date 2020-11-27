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
# <a name="troubleshooting-service-application-wont-install"></a><span data-ttu-id="bfd5a-104">Rozwiązywanie problemów: Aplikacja usług nie instaluje się</span><span class="sxs-lookup"><span data-stu-id="bfd5a-104">Troubleshooting: Service Application Won't Install</span></span>

<span data-ttu-id="bfd5a-105">Jeśli aplikacja usługi nie zostanie prawidłowo zainstalowana, upewnij się, że <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> Właściwość klasy usługi jest ustawiona na taką samą wartość jak w instalatorze dla tej usługi.</span><span class="sxs-lookup"><span data-stu-id="bfd5a-105">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="bfd5a-106">Wartość musi być taka sama w obu wystąpieniach, aby można było poprawnie zainstalować usługę.</span><span class="sxs-lookup"><span data-stu-id="bfd5a-106">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bfd5a-107">Możesz również zapoznać się z dziennikami instalacji, aby uzyskać informacje na temat procesu instalacji.</span><span class="sxs-lookup"><span data-stu-id="bfd5a-107">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="bfd5a-108">Należy również sprawdzić, czy masz już zainstalowaną inną usługę o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="bfd5a-108">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="bfd5a-109">Aby instalacja powiodła się, nazwy usług muszą być unikatowe.</span><span class="sxs-lookup"><span data-stu-id="bfd5a-109">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd5a-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bfd5a-110">See also</span></span>

- [<span data-ttu-id="bfd5a-111">Wprowadzenie do aplikacji usług systemu Windows</span><span class="sxs-lookup"><span data-stu-id="bfd5a-111">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
