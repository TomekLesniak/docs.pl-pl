---
title: 219 — ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241944"
---
# <a name="219---serviceexception"></a><span data-ttu-id="61ba8-102">219 — ServiceException</span><span class="sxs-lookup"><span data-stu-id="61ba8-102">219 - ServiceException</span></span>

## <a name="properties"></a><span data-ttu-id="61ba8-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="61ba8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="61ba8-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="61ba8-104">ID</span></span>|<span data-ttu-id="61ba8-105">219</span><span class="sxs-lookup"><span data-stu-id="61ba8-105">219</span></span>|  
|<span data-ttu-id="61ba8-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="61ba8-106">Keywords</span></span>|<span data-ttu-id="61ba8-107">EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="61ba8-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="61ba8-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="61ba8-108">Level</span></span>|<span data-ttu-id="61ba8-109">Błąd</span><span class="sxs-lookup"><span data-stu-id="61ba8-109">Error</span></span>|  
|<span data-ttu-id="61ba8-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="61ba8-110">Channel</span></span>|<span data-ttu-id="61ba8-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="61ba8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="61ba8-112">Opis</span><span class="sxs-lookup"><span data-stu-id="61ba8-112">Description</span></span>  

 <span data-ttu-id="61ba8-113">To zdarzenie jest emitowane, gdy usługa WCF napotka nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="61ba8-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="61ba8-114">Obejmuje to Nieobsłużone wyjątki podczas aktywacji, podczas przetwarzania komunikatów oraz w kodzie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="61ba8-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="61ba8-115">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="61ba8-115">Message</span></span>  

 <span data-ttu-id="61ba8-116">Podczas przetwarzania komunikatu Wystąpił nieobsługiwany wyjątek typu "%2".</span><span class="sxs-lookup"><span data-stu-id="61ba8-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="61ba8-117">Pełny wyjątek ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="61ba8-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="61ba8-118">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="61ba8-118">Details</span></span>  
  
|<span data-ttu-id="61ba8-119">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="61ba8-119">Data Item Name</span></span>|<span data-ttu-id="61ba8-120">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="61ba8-120">Data Item Type</span></span>|<span data-ttu-id="61ba8-121">Opis</span><span class="sxs-lookup"><span data-stu-id="61ba8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="61ba8-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="61ba8-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="61ba8-123">Wynik wywołania `ToString` () w wyjątku CLR.</span><span class="sxs-lookup"><span data-stu-id="61ba8-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="61ba8-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="61ba8-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="61ba8-125">FullName CLR typu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="61ba8-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="61ba8-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="61ba8-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="61ba8-127">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="61ba8-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="61ba8-128">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="61ba8-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="61ba8-129">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="61ba8-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="61ba8-130">Wywołując</span><span class="sxs-lookup"><span data-stu-id="61ba8-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="61ba8-131">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="61ba8-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
