---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: de00cac851e4c6d0fd6df16f3a01b65bb5f43415
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294680"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="6e65b-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="6e65b-102">TcpConnectionPoolSettings</span></span>

<span data-ttu-id="6e65b-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="6e65b-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e65b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6e65b-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6e65b-105">Metody</span><span class="sxs-lookup"><span data-stu-id="6e65b-105">Methods</span></span>  

 <span data-ttu-id="6e65b-106">Klasa TcpConnectionPoolSettings nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="6e65b-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6e65b-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="6e65b-107">Properties</span></span>  

 <span data-ttu-id="6e65b-108">Klasa TcpConnectionPoolSettings ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="6e65b-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="6e65b-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="6e65b-109">GroupName</span></span>  

 <span data-ttu-id="6e65b-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="6e65b-110">Data type: string</span></span>  
  
 <span data-ttu-id="6e65b-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6e65b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e65b-112">Nazwa grupy puli połączeń używanej przez element powiązania.</span><span class="sxs-lookup"><span data-stu-id="6e65b-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="6e65b-113">Czynności</span><span class="sxs-lookup"><span data-stu-id="6e65b-113">IdleTimeout</span></span>  

 <span data-ttu-id="6e65b-114">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="6e65b-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="6e65b-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6e65b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e65b-116">Maksymalny czas bezczynności połączenia przed jego rozłączeniem.</span><span class="sxs-lookup"><span data-stu-id="6e65b-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="6e65b-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="6e65b-117">LeaseTimeout</span></span>  

 <span data-ttu-id="6e65b-118">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="6e65b-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="6e65b-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6e65b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e65b-120">Limit czasu oczekiwania na zakończenie operacji dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="6e65b-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="6e65b-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="6e65b-121">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="6e65b-122">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="6e65b-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="6e65b-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="6e65b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e65b-124">Maksymalna liczba połączeń wychodzących dla każdego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="6e65b-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e65b-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6e65b-125">Requirements</span></span>  
  
|<span data-ttu-id="6e65b-126">PLIK</span><span class="sxs-lookup"><span data-stu-id="6e65b-126">MOF</span></span>|<span data-ttu-id="6e65b-127">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="6e65b-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6e65b-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="6e65b-128">Namespace</span></span>|<span data-ttu-id="6e65b-129">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6e65b-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e65b-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6e65b-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
