---
title: 'Instrukcje: Rejestrowanie informacji o usługach'
description: Dowiedz się, jak rejestrować informacje o usługach. Ustaw właściwość AutoLog, jeśli chcesz, aby projekt usługi systemu Windows był współpracujący z dziennikiem zdarzeń aplikacji.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
ms.openlocfilehash: 2e5f1fd8ebbbb218e8d6eba9b2d30d05e7c0e62c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270579"
---
# <a name="how-to-log-information-about-services"></a><span data-ttu-id="4b760-104">Instrukcje: Rejestrowanie informacji o usługach</span><span class="sxs-lookup"><span data-stu-id="4b760-104">How to: Log Information About Services</span></span>

<span data-ttu-id="4b760-105">Domyślnie wszystkie projekty usług systemu Windows mają możliwość korzystania z dziennika zdarzeń aplikacji i zapisywania do niego informacji oraz wyjątków.</span><span class="sxs-lookup"><span data-stu-id="4b760-105">By default, all Windows Service projects have the ability to interact with the Application event log and write information and exceptions to it.</span></span> <span data-ttu-id="4b760-106">Użyj właściwości, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> Aby określić, czy chcesz, aby ta funkcja w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4b760-106">You use the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to indicate whether you want this functionality in your application.</span></span> <span data-ttu-id="4b760-107">Domyślnie rejestrowanie jest włączone dla każdej usługi utworzonej przy użyciu szablonu projektu usługi systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="4b760-107">By default, logging is turned on for any service you create with the Windows Service project template.</span></span> <span data-ttu-id="4b760-108">Możesz użyć statycznej formy <xref:System.Diagnostics.EventLog> klasy do zapisywania informacji o usłudze w dzienniku bez konieczności tworzenia wystąpienia <xref:System.Diagnostics.EventLog> składnika lub ręcznego rejestrowania źródła.</span><span class="sxs-lookup"><span data-stu-id="4b760-108">You can use a static form of the <xref:System.Diagnostics.EventLog> class to write service information to a log without having to create an instance of an <xref:System.Diagnostics.EventLog> component or manually register a source.</span></span>  
  
 <span data-ttu-id="4b760-109">Instalator usługi automatycznie rejestruje każdą usługę w projekcie jako prawidłowe źródło zdarzeń w dzienniku aplikacji na komputerze, na którym zainstalowano usługę, gdy rejestrowanie jest włączone.</span><span class="sxs-lookup"><span data-stu-id="4b760-109">The installer for your service automatically registers each service in your project as a valid source of events with the Application log on the computer where the service is installed, when logging is turned on.</span></span> <span data-ttu-id="4b760-110">Usługa rejestruje informacje za każdym razem, gdy usługa jest uruchomiona, zatrzymana, wstrzymana, wznowiona, zainstalowana lub odinstalowana.</span><span class="sxs-lookup"><span data-stu-id="4b760-110">The service logs information each time the service is started, stopped, paused, resumed, installed, or uninstalled.</span></span> <span data-ttu-id="4b760-111">Rejestruje także wszystkie błędy, które wystąpiły.</span><span class="sxs-lookup"><span data-stu-id="4b760-111">It also logs any failures that occur.</span></span> <span data-ttu-id="4b760-112">Nie trzeba pisać żadnego kodu w celu zapisania wpisów w dzienniku, gdy jest używane zachowanie domyślne; usługa obsługuje to automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4b760-112">You do not need to write any code to write entries to the log when using the default behavior; the service handles this for you automatically.</span></span>  
  
 <span data-ttu-id="4b760-113">Jeśli chcesz zapisać w dzienniku zdarzeń innym niż dziennik aplikacji, musisz ustawić <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> Właściwość na `false` , utworzyć własny dziennik zdarzeń w kodzie usług i zarejestrować usługę jako prawidłowe Źródło wpisów dla tego dziennika.</span><span class="sxs-lookup"><span data-stu-id="4b760-113">If you want to write to an event log other than the Application log, you must set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`, create your own custom event log within your services code, and register your service as a valid source of entries for that log.</span></span> <span data-ttu-id="4b760-114">Następnie należy napisać kod, aby zarejestrować wpisy w dzienniku za każdym razem, gdy akcja jest zainteresowana.</span><span class="sxs-lookup"><span data-stu-id="4b760-114">You must then write code to record entries to the log whenever an action you're interested in occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b760-115">Jeśli używasz niestandardowego dziennika zdarzeń i skonfigurujesz aplikację usługi do zapisu w niej, nie musisz próbować uzyskać dostępu do dziennika zdarzeń przed ustawieniem <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> właściwości usługi w kodzie.</span><span class="sxs-lookup"><span data-stu-id="4b760-115">If you use a custom event log and configure your service application to write to it, you must not attempt to access the event log before setting the service's <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property in your code.</span></span> <span data-ttu-id="4b760-116">Dziennik zdarzeń wymaga wartości tej właściwości, aby zarejestrować usługę jako prawidłowe źródło zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="4b760-116">The event log needs this property's value to register your service as a valid source of events.</span></span>  
  
### <a name="to-enable-default-event-logging-for-your-service"></a><span data-ttu-id="4b760-117">Aby włączyć domyślne rejestrowanie zdarzeń dla usługi</span><span class="sxs-lookup"><span data-stu-id="4b760-117">To enable default event logging for your service</span></span>  
  
- <span data-ttu-id="4b760-118">Ustaw <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> Właściwość dla składnika na `true` .</span><span class="sxs-lookup"><span data-stu-id="4b760-118">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `true`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4b760-119">Domyślnie wartość tej właściwości to `true`.</span><span class="sxs-lookup"><span data-stu-id="4b760-119">By default, this property is set to `true`.</span></span> <span data-ttu-id="4b760-120">Nie musisz jawnie ustawiać tego ustawienia, chyba że tworzysz bardziej skomplikowane przetwarzanie, takie jak szacowanie warunku, a następnie Ustawianie <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> właściwości na podstawie wyniku tego warunku.</span><span class="sxs-lookup"><span data-stu-id="4b760-120">You do not need to set this explicitly unless you are building more complex processing, such as evaluating a condition and then setting the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property based on the result of that condition.</span></span>  
  
### <a name="to-disable-event-logging-for-your-service"></a><span data-ttu-id="4b760-121">Aby wyłączyć rejestrowanie zdarzeń dla usługi</span><span class="sxs-lookup"><span data-stu-id="4b760-121">To disable event logging for your service</span></span>  
  
- <span data-ttu-id="4b760-122">Ustaw <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> Właściwość dla składnika na `false` .</span><span class="sxs-lookup"><span data-stu-id="4b760-122">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `false`.</span></span>  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a><span data-ttu-id="4b760-123">Aby skonfigurować rejestrowanie do dziennika niestandardowego</span><span class="sxs-lookup"><span data-stu-id="4b760-123">To set up logging to a custom log</span></span>  
  
1. <span data-ttu-id="4b760-124">Ustaw <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> Właściwość na wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="4b760-124">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4b760-125">Aby można było <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> użyć dziennika niestandardowego, należy ustawić wartość false.</span><span class="sxs-lookup"><span data-stu-id="4b760-125">You must set <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> to false in order to use a custom log.</span></span>  
  
2. <span data-ttu-id="4b760-126">Skonfiguruj wystąpienie <xref:System.Diagnostics.EventLog> składnika w aplikacji usługi systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="4b760-126">Set up an instance of an <xref:System.Diagnostics.EventLog> component in your Windows Service application.</span></span>  
  
3. <span data-ttu-id="4b760-127">Utwórz dziennik niestandardowy, wywołując <xref:System.Diagnostics.EventLog.CreateEventSource%2A> metodę i określając ciąg źródłowy i nazwę pliku dziennika, który chcesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="4b760-127">Create a custom log by calling the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method and specifying the source string and the name of the log file you want to create.</span></span>  
  
4. <span data-ttu-id="4b760-128">Ustaw <xref:System.Diagnostics.EventLog.Source%2A> Właściwość w <xref:System.Diagnostics.EventLog> wystąpieniu składnika na ciąg źródłowy, który został utworzony w kroku 3.</span><span class="sxs-lookup"><span data-stu-id="4b760-128">Set the <xref:System.Diagnostics.EventLog.Source%2A> property on the <xref:System.Diagnostics.EventLog> component instance to the source string you created in step 3.</span></span>  
  
5. <span data-ttu-id="4b760-129">Zapisz swoje wpisy, uzyskując dostęp do <xref:System.Diagnostics.EventLog.WriteEntry%2A> metody w <xref:System.Diagnostics.EventLog> wystąpieniu składnika.</span><span class="sxs-lookup"><span data-stu-id="4b760-129">Write your entries by accessing the <xref:System.Diagnostics.EventLog.WriteEntry%2A> method on the <xref:System.Diagnostics.EventLog> component instance.</span></span>  
  
     <span data-ttu-id="4b760-130">Poniższy kod pokazuje, jak skonfigurować rejestrowanie w dzienniku niestandardowym.</span><span class="sxs-lookup"><span data-stu-id="4b760-130">The following code shows how to set up logging to a custom log.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4b760-131">W tym przykładzie kodu wystąpienie <xref:System.Diagnostics.EventLog> składnika nosi nazwę `eventLog1` ( `EventLog1` w Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4b760-131">In this code example, an instance of an <xref:System.Diagnostics.EventLog> component is named `eventLog1` (`EventLog1` in Visual Basic).</span></span> <span data-ttu-id="4b760-132">Jeśli utworzono wystąpienie z inną nazwą w kroku 2, Zmień kod odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="4b760-132">If you created an instance with another name in step 2, change the code accordingly.</span></span>  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="4b760-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4b760-133">See also</span></span>

- [<span data-ttu-id="4b760-134">Wprowadzenie do aplikacji usług systemu Windows</span><span class="sxs-lookup"><span data-stu-id="4b760-134">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
