---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 6590c5188e4e1758987a75fbd007099703ea6bc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250427"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="4a1ec-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="4a1ec-102">MsmqTransportBindingElement</span></span>

<span data-ttu-id="4a1ec-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="4a1ec-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a1ec-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4a1ec-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4a1ec-105">Metody</span><span class="sxs-lookup"><span data-stu-id="4a1ec-105">Methods</span></span>  

 <span data-ttu-id="4a1ec-106">Klasa MsmqTransportBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4a1ec-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="4a1ec-107">Properties</span></span>  

 <span data-ttu-id="4a1ec-108">Klasa MsmqTransportBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="4a1ec-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="4a1ec-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="4a1ec-109">MaxPoolSize</span></span>  

 <span data-ttu-id="4a1ec-110">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="4a1ec-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="4a1ec-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4a1ec-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a1ec-112">Maksymalny rozmiar puli zawierającej wewnętrzne obiekty wiadomości MSMQ.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="4a1ec-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="4a1ec-113">QueueTransferProtocol</span></span>  

 <span data-ttu-id="4a1ec-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="4a1ec-114">Data type: string</span></span>  
  
 <span data-ttu-id="4a1ec-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4a1ec-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a1ec-116">Wartość wyliczenia wskazująca transport kanału komunikacyjnego znajdującego się w kolejce, który jest wykorzystywany przez to powiązanie.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="4a1ec-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="4a1ec-117">UseActiveDirectory</span></span>  

 <span data-ttu-id="4a1ec-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="4a1ec-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4a1ec-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4a1ec-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a1ec-120">Zwraca wartość logiczną wskazującą, czy adresy kolejek mają być konwertowane przy użyciu Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a1ec-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4a1ec-121">Requirements</span></span>  
  
|<span data-ttu-id="4a1ec-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="4a1ec-122">MOF</span></span>|<span data-ttu-id="4a1ec-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="4a1ec-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4a1ec-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="4a1ec-124">Namespace</span></span>|<span data-ttu-id="4a1ec-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4a1ec-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a1ec-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4a1ec-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
