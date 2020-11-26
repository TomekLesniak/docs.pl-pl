---
title: 206 — ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 99415733624752217d32f6f026a419b2b32bfa7b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244616"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="9e252-102">206 — ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="9e252-102">206 - ErrorHandlerInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="9e252-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="9e252-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e252-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="9e252-104">ID</span></span>|<span data-ttu-id="9e252-105">206</span><span class="sxs-lookup"><span data-stu-id="9e252-105">206</span></span>|  
|<span data-ttu-id="9e252-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="9e252-106">Keywords</span></span>|<span data-ttu-id="9e252-107">Rozwiązywanie problemów, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9e252-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9e252-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="9e252-108">Level</span></span>|<span data-ttu-id="9e252-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="9e252-109">Information</span></span>|  
|<span data-ttu-id="9e252-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="9e252-110">Channel</span></span>|<span data-ttu-id="9e252-111">Microsoft-Windows-Application Server-Applications/Analytics</span><span class="sxs-lookup"><span data-stu-id="9e252-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9e252-112">Opis</span><span class="sxs-lookup"><span data-stu-id="9e252-112">Description</span></span>  

 <span data-ttu-id="9e252-113">To zdarzenie jest emitowane, gdy `ErrorHandler` miało możliwość obsługi wyjątku, który wystąpił w operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="9e252-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9e252-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="9e252-114">Message</span></span>  

 <span data-ttu-id="9e252-115">Dyspozytor wywołał ErrorHandler typu ' %1 ' z wyjątkiem typu ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="9e252-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="9e252-116">ErrorHandled = = ' %2 '.</span><span class="sxs-lookup"><span data-stu-id="9e252-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9e252-117">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="9e252-117">Details</span></span>  
  
|<span data-ttu-id="9e252-118">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="9e252-118">Data Item Name</span></span>|<span data-ttu-id="9e252-119">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="9e252-119">Data Item Type</span></span>|<span data-ttu-id="9e252-120">Opis</span><span class="sxs-lookup"><span data-stu-id="9e252-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9e252-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="9e252-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="9e252-122">FullName CLR typu wywoływanego `ErrorHandler` .</span><span class="sxs-lookup"><span data-stu-id="9e252-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="9e252-123">Obsłużone</span><span class="sxs-lookup"><span data-stu-id="9e252-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="9e252-124">`true` Jeśli program obsługi błędów obsłużył błąd, w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="9e252-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="9e252-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="9e252-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="9e252-126">FullName CLR wyjątku, który był obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="9e252-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="9e252-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="9e252-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="9e252-128">W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web.</span><span class="sxs-lookup"><span data-stu-id="9e252-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9e252-129">Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="9e252-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9e252-130">Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="9e252-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9e252-131">Wywołując</span><span class="sxs-lookup"><span data-stu-id="9e252-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9e252-132">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9e252-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
