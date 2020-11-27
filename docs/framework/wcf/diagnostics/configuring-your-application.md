---
title: Konfigurowanie własnej aplikacji
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: e08e474be02ee11a6727df8b908b53ab1403f7f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294832"
---
# <a name="configuring-your-application"></a><span data-ttu-id="66ecd-102">Konfigurowanie własnej aplikacji</span><span class="sxs-lookup"><span data-stu-id="66ecd-102">Configuring Your Application</span></span>

<span data-ttu-id="66ecd-103">Windows Communication Foundation (WCF) korzysta z systemu konfiguracji platformy .NET i umożliwia konfigurowanie usług zarówno w zakresie komputera, jak i aplikacji.</span><span class="sxs-lookup"><span data-stu-id="66ecd-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="66ecd-104">Ustawienia konfiguracji zdefiniowane przez funkcję WCF znajdują się w `<system.serviceModel>` grupie sekcji.</span><span class="sxs-lookup"><span data-stu-id="66ecd-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="66ecd-105">Więcej informacji o sposobie konfigurowania usługi WCF znajduje się w następujących tematach:</span><span class="sxs-lookup"><span data-stu-id="66ecd-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
- [<span data-ttu-id="66ecd-106">Konfigurowanie usług</span><span class="sxs-lookup"><span data-stu-id="66ecd-106">Configuring Services</span></span>](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="66ecd-107">Ustawienia konfiguracji zdefiniowane przez aplikację są zdefiniowane w `<appSettings>` grupie sekcji.</span><span class="sxs-lookup"><span data-stu-id="66ecd-107">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="66ecd-108">Aby uzyskać więcej informacji na temat ustawień aplikacji w plikach konfiguracji platformy .NET, zobacz [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)) .</span><span class="sxs-lookup"><span data-stu-id="66ecd-108">For more information about application settings in .NET configuration files, see [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="66ecd-109">Korzystanie z edytora konfiguracji</span><span class="sxs-lookup"><span data-stu-id="66ecd-109">Using the Configuration Editor</span></span>  

 <span data-ttu-id="66ecd-110">[Narzędzie Edytor konfiguracji WCF (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) umożliwia administratorom i deweloperom tworzenie i modyfikowanie ustawień konfiguracji usług WCF przy użyciu graficznego interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="66ecd-110">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="66ecd-111">Za pomocą tego narzędzia można zarządzać ustawieniami powiązań programu WCF, zachowań, usług i diagnostyki bez bezpośredniego edytowania plików konfiguracji XML.</span><span class="sxs-lookup"><span data-stu-id="66ecd-111">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="66ecd-112">Edytowanie plików konfiguracji w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66ecd-112">Editing Configuration Files in Visual Studio</span></span>  

 <span data-ttu-id="66ecd-113">Aby edytować plik konfiguracji projektu usługi WCF w programie Visual Studio, kliknij prawym przyciskiem myszy w **Eksplorator rozwiązań** i wybierz pozycję **Edytuj kontekst konfiguracji WCF** .</span><span class="sxs-lookup"><span data-stu-id="66ecd-113">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="66ecd-114">Spowoduje to uruchomienie [Narzędzia Edytora konfiguracji (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="66ecd-114">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66ecd-115">Jeśli edytujesz plik konfiguracyjny projektu usługi sieci Web WCF w programie Visual Studio, klikając go prawym przyciskiem myszy w **Eksplorator rozwiązań**, Zauważ, że brakuje elementu menu kontekstowego **konfiguracji WCF** .</span><span class="sxs-lookup"><span data-stu-id="66ecd-115">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="66ecd-116">Aby obejść ten problem, kliknij menu **Narzędzia** , a następnie wybierz pozycję **Edytor konfiguracji usługi WCF**.</span><span class="sxs-lookup"><span data-stu-id="66ecd-116">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="66ecd-117">Następnie możesz kliknąć prawym przyciskiem myszy plik konfiguracyjny i użyć elementu menu kontekstowego **edytowania konfiguracji WCF** .</span><span class="sxs-lookup"><span data-stu-id="66ecd-117">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ecd-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="66ecd-118">See also</span></span>

- [<span data-ttu-id="66ecd-119">Narzędzie edytora konfiguracji (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="66ecd-119">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="66ecd-120">Konfigurowanie usług</span><span class="sxs-lookup"><span data-stu-id="66ecd-120">Configuring Services</span></span>](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
