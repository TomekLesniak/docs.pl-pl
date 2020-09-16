---
title: Śledzenie przepływu pracy
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: fc27be295cbf0a83b65ff03e36f2aeffeda12db9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557505"
---
# <a name="workflow-tracing"></a><span data-ttu-id="cf460-102">Śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="cf460-102">Workflow Tracing</span></span>
<span data-ttu-id="cf460-103">Śledzenie przepływu pracy umożliwia przechwytywanie informacji diagnostycznych przy użyciu detektorów śledzenia .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf460-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="cf460-104">Śledzenie można włączyć, jeśli problem zostanie wykryty w aplikacji, a następnie ponownie wyłączony po rozwiązaniu problemu.</span><span class="sxs-lookup"><span data-stu-id="cf460-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="cf460-105">Istnieją dwa sposoby włączania śledzenia debugowania dla przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="cf460-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="cf460-106">Można go skonfigurować przy użyciu podglądu śledzenia zdarzeń lub użyć <xref:System.Diagnostics> do wysyłania zdarzeń śledzenia do pliku.</span><span class="sxs-lookup"><span data-stu-id="cf460-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="cf460-107">Włączanie śledzenia debugowania w ETW</span><span class="sxs-lookup"><span data-stu-id="cf460-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="cf460-108">Aby włączyć śledzenie przy użyciu funkcji ETW, Włącz kanał debugowania w Podgląd zdarzeń:</span><span class="sxs-lookup"><span data-stu-id="cf460-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1. <span data-ttu-id="cf460-109">Przejdź do węzła dzienniki analityczne i debugowania w Podgląd zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="cf460-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2. <span data-ttu-id="cf460-110">W widoku drzewa w Podgląd zdarzeń przejdź do **Podgląd zdarzeń >aplikacje i usługi Dzienniki — >Microsoft->Windows->aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="cf460-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="cf460-111">Kliknij prawym przyciskiem myszy pozycję **serwer aplikacji — aplikacje** i wybierz polecenie **Widok->Pokaż dzienniki analityczne i debugowania**.</span><span class="sxs-lookup"><span data-stu-id="cf460-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="cf460-112">Kliknij prawym przyciskiem myszy pozycję **Debuguj** i wybierz pozycję **Włącz dziennik**.</span><span class="sxs-lookup"><span data-stu-id="cf460-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3. <span data-ttu-id="cf460-113">Gdy przepływ pracy uruchamia debugowanie i ślady są emitowane do kanału debugowania ETW, można je wyświetlić w Podgląd zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="cf460-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="cf460-114">Przejdź do **Podgląd zdarzeń->Dzienniki aplikacji i usług->Microsoft->Windows->aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="cf460-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="cf460-115">Kliknij prawym przyciskiem myszy pozycję **Debuguj** i wybierz polecenie **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="cf460-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4. <span data-ttu-id="cf460-116">Domyślny rozmiar buforu śledzenia analitycznego to tylko 4 kilobajty (KB); zaleca się zwiększenie rozmiaru do 32 KB.</span><span class="sxs-lookup"><span data-stu-id="cf460-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="cf460-117">Aby to zrobić, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="cf460-117">To do this, perform the following steps.</span></span>  
  
    1. <span data-ttu-id="cf460-118">Wykonaj następujące polecenie w bieżącym katalogu struktury (na przykład C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="cf460-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2. <span data-ttu-id="cf460-119">Zmień \<bufferSize> wartość w pliku Windows. ApplicationServer. Applications. Man na 32.</span><span class="sxs-lookup"><span data-stu-id="cf460-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. <span data-ttu-id="cf460-120">Wykonaj następujące polecenie w bieżącym katalogu struktury (na przykład C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="cf460-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf460-121">Jeśli używasz profilu klienta .NET Framework 4, musisz najpierw zarejestrować manifest ETW, uruchamiając następujące polecenie w katalogu .NET Framework 4: `ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="cf460-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="cf460-122">Włączanie śledzenia debugowania przy użyciu System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="cf460-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="cf460-123">Te odbiorniki można skonfigurować w pliku App.config aplikacji przepływu pracy lub Web.config dla usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="cf460-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="cf460-124">W tym przykładzie <xref:System.Diagnostics.TextWriterTraceListener> jest skonfigurowany do zapisywania informacji o śledzeniu do pliku MyTraceLog.txt w bieżącym katalogu.</span><span class="sxs-lookup"><span data-stu-id="cf460-124">In this example, a <xref:System.Diagnostics.TextWriterTraceListener> is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf460-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cf460-125">See also</span></span>

- <span data-ttu-id="cf460-126">[Monitorowanie aplikacji sieci szkieletowej systemu Windows Server](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="cf460-126">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="cf460-127">[Monitorowanie aplikacji przy użyciu sieci szkieletowej aplikacji](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="cf460-127">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
