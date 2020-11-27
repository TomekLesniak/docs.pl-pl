---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262219"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="3bb86-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="3bb86-102">WSAT_TraceRecord</span></span>

<span data-ttu-id="3bb86-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="3bb86-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb86-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3bb86-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3bb86-105">Metody</span><span class="sxs-lookup"><span data-stu-id="3bb86-105">Methods</span></span>  

 <span data-ttu-id="3bb86-106">Klasa WSAT_TraceRecord nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="3bb86-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3bb86-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="3bb86-107">Properties</span></span>  

 <span data-ttu-id="3bb86-108">Klasa WSAT_TraceRecord ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="3bb86-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="3bb86-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="3bb86-109">ActivityID</span></span>  

 <span data-ttu-id="3bb86-110">Typ danych: obiekt</span><span class="sxs-lookup"><span data-stu-id="3bb86-110">Data type: object</span></span>  
<span data-ttu-id="3bb86-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="3bb86-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3bb86-112">Identyfikator działania rekordu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="3bb86-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="3bb86-113">Identyfikator zdarzenia</span><span class="sxs-lookup"><span data-stu-id="3bb86-113">EventID</span></span>  

 <span data-ttu-id="3bb86-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="3bb86-114">Data type: sint32</span></span>  
<span data-ttu-id="3bb86-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="3bb86-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3bb86-116">Identyfikator zdarzenia rekordu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="3bb86-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="3bb86-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="3bb86-117">TraceRecord</span></span>  

 <span data-ttu-id="3bb86-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="3bb86-118">Data type: string</span></span>  
<span data-ttu-id="3bb86-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="3bb86-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3bb86-120">Rekord śledzenia</span><span class="sxs-lookup"><span data-stu-id="3bb86-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bb86-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3bb86-121">Requirements</span></span>  
  
|<span data-ttu-id="3bb86-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="3bb86-122">MOF</span></span>|<span data-ttu-id="3bb86-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="3bb86-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3bb86-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="3bb86-124">Namespace</span></span>|<span data-ttu-id="3bb86-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3bb86-125">Defined in root\ServiceModel</span></span>|
