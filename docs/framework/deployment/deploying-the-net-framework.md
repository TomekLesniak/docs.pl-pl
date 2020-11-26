---
title: Wdrażanie programu .NET Framework
description: Dowiedz się, jak wdrożyć platformę .NET dla deweloperów, którzy chcą zainstalować program .NET z aplikacjami oraz dla administratorów, którzy chcą wdrożyć platformę .NET w sieci.
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, deploying
- deployment [.NET Framework]
ms.assetid: 19df26c5-4008-461d-a7d7-18f4506312d2
ms.openlocfilehash: b42646b60fab91fe761a8fdef59d67be6ffa884b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242048"
---
# <a name="deploying-the-net-framework"></a><span data-ttu-id="2501e-103">Wdrażanie programu .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2501e-103">Deploying the .NET Framework</span></span>

<span data-ttu-id="2501e-104">Ta sekcja dokumentacji .NET Framework zawiera informacje dla deweloperów, którzy chcą zainstalować .NET Framework z aplikacjami, a także administratorów, którzy chcą wdrożyć .NET Framework w sieci.</span><span class="sxs-lookup"><span data-stu-id="2501e-104">This section of the .NET Framework documentation provides information for developers who want to install the .NET Framework with their applications, and administrators who want to deploy the .NET Framework across a network.</span></span> <span data-ttu-id="2501e-105">Omówiono w nim również problemy dotyczące aktywacji i ponownego uruchomienia związane z wdrożeniem oraz sposób monitorowania postępu instalacji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2501e-105">It also discusses activation and restart issues associated with deployment, and how to monitor the progress of your .NET Framework installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2501e-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="2501e-106">In This Section</span></span>  

 [<span data-ttu-id="2501e-107">Przewodnik wdrażania dla deweloperów</span><span class="sxs-lookup"><span data-stu-id="2501e-107">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)  
 <span data-ttu-id="2501e-108">Wyjaśnia, w jaki sposób deweloperzy mogą instalować .NET Framework na komputerach użytkowników przy użyciu ich aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2501e-108">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>  
  
 [<span data-ttu-id="2501e-109">Przewodnik wdrażania dla administratorów</span><span class="sxs-lookup"><span data-stu-id="2501e-109">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)  
 <span data-ttu-id="2501e-110">Wyjaśnia, w jaki sposób administrator systemu może wdrożyć .NET Framework i zależności systemu w sieci za pomocą usługi Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2501e-110">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span>  
  
 [<span data-ttu-id="2501e-111">Zmniejszenie liczby ponownych uruchomień systemu podczas instalowania programu .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="2501e-111">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)  
 <span data-ttu-id="2501e-112">Opisuje Menedżera ponownego uruchamiania, który uniemożliwia ponowne uruchomienie w miarę możliwości, i wyjaśnia, jak aplikacje instalujące .NET Framework mogą korzystać z tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="2501e-112">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>  
  
 [<span data-ttu-id="2501e-113">Instrukcje: pobieranie danych o postępie z Instalatora .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="2501e-113">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)  
 <span data-ttu-id="2501e-114">Opisuje sposób dyskretnego uruchamiania i śledzenia procesu instalacji .NET Framework podczas wyświetlania własnego widoku postępu instalacji.</span><span class="sxs-lookup"><span data-stu-id="2501e-114">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>  
  
 [<span data-ttu-id="2501e-115">Błędy inicjowania programu .NET Framework: Zarządzanie środowiskiem użytkownika</span><span class="sxs-lookup"><span data-stu-id="2501e-115">.NET Framework Initialization Errors: Managing the User Experience</span></span>](initialization-errors-managing-the-user-experience.md)  
 <span data-ttu-id="2501e-116">Wyjaśnia, co się stanie, gdy aplikacja .NET Framework wymaga wersji środowiska CLR, która jest nieprawidłowa lub niezainstalowana na komputerze użytkownika, jak rozwiązać te błędy i jak kontrolować komunikat o błędzie wyświetlany użytkownikowi.</span><span class="sxs-lookup"><span data-stu-id="2501e-116">Explains what happens when a .NET Framework application requires a CLR version that's invalid or not installed on the user's computer, how to resolve these errors, and how to control the error message displayed to the user.</span></span>  
  
 [<span data-ttu-id="2501e-117">Instrukcje: debugowanie problemów aktywacji środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="2501e-117">How to: Debug CLR Activation Issues</span></span>](how-to-debug-clr-activation-issues.md)  
 <span data-ttu-id="2501e-118">Wyjaśnia, jak można wyświetlać i debugować dzienniki aktywacji środowiska CLR w celu rozwiązywania problemów, które mogą wystąpić podczas uruchamiania aplikacji z poprawną wersją środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="2501e-118">Explains how you can view and debug CLR activation logs to resolve issues you may encounter in getting your application to run with the correct version of the CLR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2501e-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2501e-119">See also</span></span>

- [<span data-ttu-id="2501e-120">Przewodnik programowania</span><span class="sxs-lookup"><span data-stu-id="2501e-120">Development Guide</span></span>](../development-guide.md)
