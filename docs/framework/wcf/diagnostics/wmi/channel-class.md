---
title: Klasa kanału
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: a920636e7df9609b12834366b1488c80122f9fca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274234"
---
# <a name="channel-class"></a><span data-ttu-id="64b92-102">Klasa kanału</span><span class="sxs-lookup"><span data-stu-id="64b92-102">Channel class</span></span>

<span data-ttu-id="64b92-103">Kanał</span><span class="sxs-lookup"><span data-stu-id="64b92-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64b92-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="64b92-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="64b92-105">Metody</span><span class="sxs-lookup"><span data-stu-id="64b92-105">Methods</span></span>  

 <span data-ttu-id="64b92-106">Klasa kanału nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="64b92-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="64b92-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="64b92-107">Properties</span></span>  

 <span data-ttu-id="64b92-108">Klasa kanału ma następujące właściwości.</span><span class="sxs-lookup"><span data-stu-id="64b92-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="64b92-109">Localaddress wynosi</span><span class="sxs-lookup"><span data-stu-id="64b92-109">LocalAddress</span></span>  

 <span data-ttu-id="64b92-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="64b92-110">Data type: string</span></span>  
  
 <span data-ttu-id="64b92-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="64b92-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64b92-112">Lokalny punkt końcowy kanału.</span><span class="sxs-lookup"><span data-stu-id="64b92-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="64b92-113">ref</span><span class="sxs-lookup"><span data-stu-id="64b92-113">ref</span></span>  

 <span data-ttu-id="64b92-114">Typ danych: punkt końcowy</span><span class="sxs-lookup"><span data-stu-id="64b92-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="64b92-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="64b92-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64b92-116">Odwołanie do punktu końcowego, z którym łączy się kanał.</span><span class="sxs-lookup"><span data-stu-id="64b92-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="64b92-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="64b92-117">RemoteAddress</span></span>  

 <span data-ttu-id="64b92-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="64b92-118">Data type: string</span></span>  
  
 <span data-ttu-id="64b92-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="64b92-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64b92-120">Adres zdalny skojarzony z kanałem.</span><span class="sxs-lookup"><span data-stu-id="64b92-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="64b92-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="64b92-121">SessionId</span></span>  

 <span data-ttu-id="64b92-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="64b92-122">Data type: string</span></span>  
  
 <span data-ttu-id="64b92-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="64b92-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64b92-124">Identyfikator bieżącej sesji (jeśli istnieje).</span><span class="sxs-lookup"><span data-stu-id="64b92-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="64b92-125">Typ</span><span class="sxs-lookup"><span data-stu-id="64b92-125">Type</span></span>  

 <span data-ttu-id="64b92-126">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="64b92-126">Data type: string</span></span>  
  
 <span data-ttu-id="64b92-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="64b92-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64b92-128">Typ kanału.</span><span class="sxs-lookup"><span data-stu-id="64b92-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64b92-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="64b92-129">Requirements</span></span>  
  
|<span data-ttu-id="64b92-130">PLIK</span><span class="sxs-lookup"><span data-stu-id="64b92-130">MOF</span></span>|<span data-ttu-id="64b92-131">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="64b92-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="64b92-132">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="64b92-132">Namespace</span></span>|<span data-ttu-id="64b92-133">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="64b92-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64b92-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="64b92-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
