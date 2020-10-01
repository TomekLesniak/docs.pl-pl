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
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="ea675-103">Instrukcje: Wstrzymywanie usługi systemu Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea675-103">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="ea675-104">Ten przykład używa <xref:System.ServiceProcess.ServiceController> składnika do wstrzymania usługi administratora usług IIS na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="ea675-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea675-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="ea675-105">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="ea675-106">Ten przykład kodu jest również dostępny jako fragment kodu IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ea675-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ea675-107">W selektorze fragmentów kodu znajduje się on w **systemie operacyjnym windows > usług systemu Windows**.</span><span class="sxs-lookup"><span data-stu-id="ea675-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="ea675-108">Aby uzyskać więcej informacji, zobacz [fragmenty kodu](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="ea675-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ea675-109">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="ea675-109">Compiling the Code</span></span>  
 <span data-ttu-id="ea675-110">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="ea675-110">This example requires:</span></span>  
  
- <span data-ttu-id="ea675-111">Odwołanie do projektu do System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="ea675-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="ea675-112">Dostęp do elementów członkowskich <xref:System.ServiceProcess> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="ea675-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="ea675-113">Dodaj `Imports` instrukcję, jeśli nie masz w pełni kwalifikowanej nazwy elementu członkowskiego w kodzie.</span><span class="sxs-lookup"><span data-stu-id="ea675-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="ea675-114">Aby uzyskać więcej informacji, zobacz [Imports — Instrukcja (przestrzeń nazw i typ .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="ea675-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ea675-115">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="ea675-115">Robust Programming</span></span>  
 <span data-ttu-id="ea675-116"><xref:System.ServiceProcess.ServiceController.MachineName%2A>Właściwość <xref:System.ServiceProcess.ServiceController> klasy jest domyślnie komputerem lokalnym.</span><span class="sxs-lookup"><span data-stu-id="ea675-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="ea675-117">Aby odwoływać się do usług systemu Windows na innym komputerze, należy zmienić <xref:System.ServiceProcess.ServiceController.MachineName%2A> Właściwość na nazwę tego komputera.</span><span class="sxs-lookup"><span data-stu-id="ea675-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="ea675-118">Następujące warunki mogą spowodować wyjątek:</span><span class="sxs-lookup"><span data-stu-id="ea675-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ea675-119">Nie można wstrzymać usługi.</span><span class="sxs-lookup"><span data-stu-id="ea675-119">The service cannot be paused.</span></span> <span data-ttu-id="ea675-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="ea675-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="ea675-121">Wystąpił błąd podczas uzyskiwania dostępu do interfejsu API systemu.</span><span class="sxs-lookup"><span data-stu-id="ea675-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="ea675-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="ea675-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ea675-123">Zabezpieczenia.NET Framework</span><span class="sxs-lookup"><span data-stu-id="ea675-123">.NET Framework Security</span></span>  
 <span data-ttu-id="ea675-124">Kontrolowanie usług na komputerze może być ograniczone przy użyciu programu w <xref:System.ServiceProcess.ServiceControllerPermissionAccess> celu ustawienia uprawnień w <xref:System.ServiceProcess.ServiceControllerPermission> .</span><span class="sxs-lookup"><span data-stu-id="ea675-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="ea675-125">Dostęp do informacji o usłudze może być ograniczony przy użyciu <xref:System.Security.Permissions.PermissionState> do ustawiania uprawnień w <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="ea675-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea675-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ea675-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="ea675-127">Instrukcje: Kontynuowanie usługi systemu Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea675-127">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)
