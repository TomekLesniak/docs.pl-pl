---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6af85d62fffada95537494692b8694f42d7a2932
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290091"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="abdd5-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="abdd5-102">TcpTransportBindingElement</span></span>

<span data-ttu-id="abdd5-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="abdd5-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abdd5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="abdd5-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="abdd5-105">Metody</span><span class="sxs-lookup"><span data-stu-id="abdd5-105">Methods</span></span>  

 <span data-ttu-id="abdd5-106">Klasa TcpTransportBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="abdd5-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="abdd5-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="abdd5-107">Properties</span></span>  

 <span data-ttu-id="abdd5-108">Klasa TcpTransportBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="abdd5-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="abdd5-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="abdd5-109">ConnectionPoolSettings</span></span>  

 <span data-ttu-id="abdd5-110">Typ danych: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="abdd5-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="abdd5-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="abdd5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="abdd5-112">Ustawienia puli połączeń.</span><span class="sxs-lookup"><span data-stu-id="abdd5-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="abdd5-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="abdd5-113">ListenBacklog</span></span>  

 <span data-ttu-id="abdd5-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="abdd5-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="abdd5-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="abdd5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="abdd5-116">Maksymalna liczba oczekujących żądań połączeń z kolejki.</span><span class="sxs-lookup"><span data-stu-id="abdd5-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="abdd5-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="abdd5-117">PortSharingEnabled</span></span>  

 <span data-ttu-id="abdd5-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="abdd5-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="abdd5-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="abdd5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="abdd5-120">Wartość logiczna określająca, czy włączone jest Udostępnianie portów TCP dla tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="abdd5-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="abdd5-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="abdd5-121">TeredoEnabled</span></span>  

 <span data-ttu-id="abdd5-122">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="abdd5-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="abdd5-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="abdd5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="abdd5-124">Wartość logiczna określająca, czy jest włączona funkcja Teredo (technologia do adresowania klientów znajdujących się za zaporą).</span><span class="sxs-lookup"><span data-stu-id="abdd5-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abdd5-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="abdd5-125">Requirements</span></span>  
  
|<span data-ttu-id="abdd5-126">PLIK</span><span class="sxs-lookup"><span data-stu-id="abdd5-126">MOF</span></span>|<span data-ttu-id="abdd5-127">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="abdd5-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="abdd5-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="abdd5-128">Namespace</span></span>|<span data-ttu-id="abdd5-129">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="abdd5-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="abdd5-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="abdd5-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
