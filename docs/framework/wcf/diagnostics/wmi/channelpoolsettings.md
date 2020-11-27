---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 3dcc1f3b27d93d5641a4bb2d8082aa3fa88882dc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274221"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="6f2b2-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="6f2b2-102">ChannelPoolSettings</span></span>

<span data-ttu-id="6f2b2-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="6f2b2-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f2b2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6f2b2-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6f2b2-105">Metody</span><span class="sxs-lookup"><span data-stu-id="6f2b2-105">Methods</span></span>  

 <span data-ttu-id="6f2b2-106">Klasa ChannelPoolSettings nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="6f2b2-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6f2b2-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="6f2b2-107">Properties</span></span>  

 <span data-ttu-id="6f2b2-108">Klasa ChannelPoolSettings ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="6f2b2-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="6f2b2-109">Czynności</span><span class="sxs-lookup"><span data-stu-id="6f2b2-109">IdleTimeout</span></span>  

 <span data-ttu-id="6f2b2-110">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="6f2b2-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="6f2b2-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6f2b2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f2b2-112">Maksymalny czas bezczynności połączenia przed jego rozłączeniem.</span><span class="sxs-lookup"><span data-stu-id="6f2b2-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="6f2b2-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="6f2b2-113">LeaseTimeout</span></span>  

 <span data-ttu-id="6f2b2-114">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="6f2b2-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="6f2b2-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6f2b2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f2b2-116">Limit czasu oczekiwania na zakończenie operacji dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6f2b2-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="6f2b2-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="6f2b2-117">MaxOutboundChannelsPerEndpoint</span></span>  

 <span data-ttu-id="6f2b2-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="6f2b2-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="6f2b2-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6f2b2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f2b2-120">Maksymalna liczba kanałów wychodzących dla każdego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="6f2b2-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f2b2-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6f2b2-121">Requirements</span></span>  
  
|<span data-ttu-id="6f2b2-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="6f2b2-122">MOF</span></span>|<span data-ttu-id="6f2b2-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="6f2b2-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6f2b2-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="6f2b2-124">Namespace</span></span>|<span data-ttu-id="6f2b2-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6f2b2-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f2b2-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6f2b2-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
