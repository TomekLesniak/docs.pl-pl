---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ae6a3448896cb206bce8867daf7104c3e484ecc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269018"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="e221e-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e221e-102">PeerTransportBindingElement</span></span>

<span data-ttu-id="e221e-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e221e-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e221e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e221e-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e221e-105">Metody</span><span class="sxs-lookup"><span data-stu-id="e221e-105">Methods</span></span>  

 <span data-ttu-id="e221e-106">Klasa PeerTransportBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="e221e-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e221e-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e221e-107">Properties</span></span>  

 <span data-ttu-id="e221e-108">Klasa PeerTransportBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="e221e-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="e221e-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="e221e-109">ListenIPAddress</span></span>  

 <span data-ttu-id="e221e-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="e221e-110">Data type: string</span></span>  
  
 <span data-ttu-id="e221e-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e221e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e221e-112">Adres IP, na którym węzeł równorzędny nasłuchuje komunikatów.</span><span class="sxs-lookup"><span data-stu-id="e221e-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="e221e-113">Port</span><span class="sxs-lookup"><span data-stu-id="e221e-113">Port</span></span>  

 <span data-ttu-id="e221e-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="e221e-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="e221e-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e221e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e221e-116">Port interfejsu sieciowego, na którym to powiązanie przetwarza wiadomości kanału równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="e221e-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="e221e-117">Zabezpieczenia</span><span class="sxs-lookup"><span data-stu-id="e221e-117">Security</span></span>  

 <span data-ttu-id="e221e-118">Typ danych: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="e221e-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="e221e-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e221e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e221e-120">Ustawienia zabezpieczeń transportu elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="e221e-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e221e-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e221e-121">Requirements</span></span>  
  
|<span data-ttu-id="e221e-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="e221e-122">MOF</span></span>|<span data-ttu-id="e221e-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="e221e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e221e-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="e221e-124">Namespace</span></span>|<span data-ttu-id="e221e-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e221e-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e221e-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e221e-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
