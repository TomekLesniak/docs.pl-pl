---
title: Śledzenie
ms.date: 03/30/2017
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
ms.openlocfilehash: 10b9be028710cdda378aeef0ca235a00aa451e08
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243914"
---
# <a name="tracing"></a><span data-ttu-id="d1547-102">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="d1547-102">Tracing</span></span>

<span data-ttu-id="d1547-103">Windows Communication Foundation (WCF) udostępnia instrumentację aplikacji i dane diagnostyczne na potrzeby monitorowania i analizy błędów.</span><span class="sxs-lookup"><span data-stu-id="d1547-103">Windows Communication Foundation (WCF) provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="d1547-104">Możesz użyć śledzenia zamiast debugera, aby zrozumieć, jak działa aplikacja, lub przyczynę błędu.</span><span class="sxs-lookup"><span data-stu-id="d1547-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="d1547-105">Możesz również skorelować błędy i przetwarzanie między składnikami, aby zapewnić kompleksowe środowisko pracy.</span><span class="sxs-lookup"><span data-stu-id="d1547-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 <span data-ttu-id="d1547-106">Usługa WCF wyprowadza następujące dane do śledzenia diagnostycznego:</span><span class="sxs-lookup"><span data-stu-id="d1547-106">WCF outputs the following data for diagnostic tracing:</span></span>  
  
- <span data-ttu-id="d1547-107">Ślady dla punktów kontrolnych procesu we wszystkich składnikach aplikacji, takich jak wywołania operacji, wyjątki kodu, ostrzeżenia i inne istotne zdarzenia przetwarzania ".</span><span class="sxs-lookup"><span data-stu-id="d1547-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
- <span data-ttu-id="d1547-108">Zdarzenia błędów systemu Windows, gdy funkcja śledzenia działa nieprawidłowo.</span><span class="sxs-lookup"><span data-stu-id="d1547-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1547-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="d1547-109">In This Section</span></span>  

 [<span data-ttu-id="d1547-110">Konfigurowanie śledzenia</span><span class="sxs-lookup"><span data-stu-id="d1547-110">Configuring Tracing</span></span>](configuring-tracing.md)  
  
 <span data-ttu-id="d1547-111">W tym temacie opisano, jak można skonfigurować śledzenie na różnych poziomach zgodnie z konkretną potrzebami.</span><span class="sxs-lookup"><span data-stu-id="d1547-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="d1547-112">Kompleksowe śledzenie</span><span class="sxs-lookup"><span data-stu-id="d1547-112">End-to-End Tracing</span></span>](end-to-end-tracing.md)  
  
 <span data-ttu-id="d1547-113">W tej sekcji opisano, jak można użyć funkcji Śledzenie aktywności i Propagacja na potrzeby kompleksowej korelacji, aby pomóc w debugowaniu.</span><span class="sxs-lookup"><span data-stu-id="d1547-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="d1547-114">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="d1547-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="d1547-115">W tej sekcji opisano, jak można użyć śledzenia do debugowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d1547-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="d1547-116">Problemy dotyczące zabezpieczeń i przydatne porady na temat śledzenia</span><span class="sxs-lookup"><span data-stu-id="d1547-116">Security Concerns and Useful Tips for Tracing</span></span>](security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="d1547-117">W tym temacie opisano, jak można chronić poufne informacje przed ujawnieniem, a także przydatne porady dotyczące korzystania z programu WebHost.</span><span class="sxs-lookup"><span data-stu-id="d1547-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="d1547-118">Informacje o śladach</span><span class="sxs-lookup"><span data-stu-id="d1547-118">Traces Reference</span></span>](traces-reference.md)  
  
 <span data-ttu-id="d1547-119">W tym temacie wymieniono wszystkie ślady wygenerowane przez program WCF.</span><span class="sxs-lookup"><span data-stu-id="d1547-119">This topic lists all the traces generated by WCF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1547-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d1547-120">See also</span></span>

- [<span data-ttu-id="d1547-121">Narzędzie do przeglądania danych śledzenia usług (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="d1547-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
