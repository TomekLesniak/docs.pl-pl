---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 45bfcd069391156bc85cc4c26f2b172770197a9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234846"
---
# <a name="transportbindingelement"></a><span data-ttu-id="ec780-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec780-102">TransportBindingElement</span></span>

<span data-ttu-id="ec780-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ec780-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec780-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ec780-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ec780-105">Metody</span><span class="sxs-lookup"><span data-stu-id="ec780-105">Methods</span></span>  

 <span data-ttu-id="ec780-106">Klasa TransportBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="ec780-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ec780-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ec780-107">Properties</span></span>  

 <span data-ttu-id="ec780-108">Klasa TransportBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="ec780-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="ec780-109">Opcję ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="ec780-109">ManualAddressing</span></span>  

 <span data-ttu-id="ec780-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="ec780-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ec780-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ec780-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec780-112">Wartość logiczna określająca, czy użytkownik chce przejąć kontrolę nad adresowaniem komunikatów.</span><span class="sxs-lookup"><span data-stu-id="ec780-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="ec780-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ec780-113">MaxBufferPoolSize</span></span>  

 <span data-ttu-id="ec780-114">Typ danych: sint64</span><span class="sxs-lookup"><span data-stu-id="ec780-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="ec780-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ec780-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec780-116">Maksymalny rozmiar puli buforów dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="ec780-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="ec780-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ec780-117">MaxReceivedMessageSize</span></span>  

 <span data-ttu-id="ec780-118">Typ danych: sint64</span><span class="sxs-lookup"><span data-stu-id="ec780-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="ec780-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ec780-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec780-120">Maksymalny rozmiar wiadomości przetwarzanej przez to powiązanie.</span><span class="sxs-lookup"><span data-stu-id="ec780-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="ec780-121">Schemat</span><span class="sxs-lookup"><span data-stu-id="ec780-121">Scheme</span></span>  

 <span data-ttu-id="ec780-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="ec780-122">Data type: string</span></span>  
  
 <span data-ttu-id="ec780-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="ec780-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ec780-124">Schemat identyfikatora URI dla transportu.</span><span class="sxs-lookup"><span data-stu-id="ec780-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec780-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ec780-125">Requirements</span></span>  
  
|<span data-ttu-id="ec780-126">PLIK</span><span class="sxs-lookup"><span data-stu-id="ec780-126">MOF</span></span>|<span data-ttu-id="ec780-127">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="ec780-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ec780-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="ec780-128">Namespace</span></span>|<span data-ttu-id="ec780-129">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ec780-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec780-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ec780-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
