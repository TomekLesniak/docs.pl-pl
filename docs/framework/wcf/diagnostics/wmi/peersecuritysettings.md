---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 2de417e4a4f5c6197551c1408da6907e2fa7c635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269005"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="ccfbe-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ccfbe-102">PeerSecuritySettings</span></span>

<span data-ttu-id="ccfbe-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ccfbe-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccfbe-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ccfbe-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ccfbe-105">Metody</span><span class="sxs-lookup"><span data-stu-id="ccfbe-105">Methods</span></span>  

 <span data-ttu-id="ccfbe-106">Klasa PeerSecuritySettings nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ccfbe-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ccfbe-107">Properties</span></span>  

 <span data-ttu-id="ccfbe-108">Klasa PeerSecuritySettings ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="ccfbe-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="ccfbe-109">Tryb</span><span class="sxs-lookup"><span data-stu-id="ccfbe-109">Mode</span></span>  

 <span data-ttu-id="ccfbe-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="ccfbe-110">Data type: string</span></span>  
  
 <span data-ttu-id="ccfbe-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ccfbe-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccfbe-112">Określa, czy zabezpieczenia na poziomie komunikatów i transportu są używane przez punkt końcowy skonfigurowany dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="ccfbe-113">Transport</span><span class="sxs-lookup"><span data-stu-id="ccfbe-113">Transport</span></span>  

 <span data-ttu-id="ccfbe-114">Typ danych: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ccfbe-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="ccfbe-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ccfbe-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ccfbe-116">Ustawienia zabezpieczeń transportu.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccfbe-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ccfbe-117">Requirements</span></span>  
  
|<span data-ttu-id="ccfbe-118">PLIK</span><span class="sxs-lookup"><span data-stu-id="ccfbe-118">MOF</span></span>|<span data-ttu-id="ccfbe-119">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="ccfbe-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ccfbe-120">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="ccfbe-120">Namespace</span></span>|<span data-ttu-id="ccfbe-121">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ccfbe-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccfbe-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ccfbe-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
