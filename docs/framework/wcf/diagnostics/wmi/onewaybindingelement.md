---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 806066a8845068413d2a52c78878f76b5f5fa34f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250375"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="d10d4-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="d10d4-102">OneWayBindingElement</span></span>

<span data-ttu-id="d10d4-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="d10d4-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d10d4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d10d4-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d10d4-105">Metody</span><span class="sxs-lookup"><span data-stu-id="d10d4-105">Methods</span></span>  

 <span data-ttu-id="d10d4-106">Klasa OneWayBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="d10d4-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d10d4-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="d10d4-107">Properties</span></span>  

 <span data-ttu-id="d10d4-108">Klasa OneWayBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="d10d4-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="d10d4-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d10d4-109">ChannelPoolSettings</span></span>  

 <span data-ttu-id="d10d4-110">Typ danych: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d10d4-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="d10d4-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d10d4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d10d4-112">Ustawienia puli kanałów.</span><span class="sxs-lookup"><span data-stu-id="d10d4-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="d10d4-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="d10d4-113">MaxAcceptedChannels</span></span>  

 <span data-ttu-id="d10d4-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="d10d4-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="d10d4-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d10d4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d10d4-116">Maksymalna liczba zaakceptowanych kanałów.</span><span class="sxs-lookup"><span data-stu-id="d10d4-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="d10d4-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="d10d4-117">PacketRoutable</span></span>  

 <span data-ttu-id="d10d4-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="d10d4-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="d10d4-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="d10d4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d10d4-120">Wartość wskazująca, czy pakiet jest w trakcie routingu.</span><span class="sxs-lookup"><span data-stu-id="d10d4-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d10d4-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d10d4-121">Requirements</span></span>  
  
|<span data-ttu-id="d10d4-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="d10d4-122">MOF</span></span>|<span data-ttu-id="d10d4-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="d10d4-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d10d4-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="d10d4-124">Namespace</span></span>|<span data-ttu-id="d10d4-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d10d4-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d10d4-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d10d4-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
