---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8422e1adf9a8914b631431eba5c9c0ed058cd0f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258026"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="99a4b-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="99a4b-102">NamedPipeConnectionPoolSettings</span></span>

<span data-ttu-id="99a4b-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="99a4b-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99a4b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="99a4b-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="99a4b-105">Metody</span><span class="sxs-lookup"><span data-stu-id="99a4b-105">Methods</span></span>  

 <span data-ttu-id="99a4b-106">Klasa NamedPipeConnectionPoolSettings nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="99a4b-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="99a4b-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="99a4b-107">Properties</span></span>  

 <span data-ttu-id="99a4b-108">Klasa NamedPipeConnectionPoolSettings ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="99a4b-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="99a4b-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="99a4b-109">GroupName</span></span>  

 <span data-ttu-id="99a4b-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="99a4b-110">Data type: string</span></span>  
  
 <span data-ttu-id="99a4b-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="99a4b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99a4b-112">Nazwa grupy puli połączeń używanej przez element powiązania.</span><span class="sxs-lookup"><span data-stu-id="99a4b-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="99a4b-113">Czynności</span><span class="sxs-lookup"><span data-stu-id="99a4b-113">IdleTimeout</span></span>  

 <span data-ttu-id="99a4b-114">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="99a4b-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="99a4b-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="99a4b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99a4b-116">Maksymalny czas bezczynności połączenia przed jego rozłączeniem.</span><span class="sxs-lookup"><span data-stu-id="99a4b-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="99a4b-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="99a4b-117">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="99a4b-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="99a4b-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="99a4b-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="99a4b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99a4b-120">Maksymalna liczba połączeń wychodzących dla każdego punktu końcowego na komputerze klienckim.</span><span class="sxs-lookup"><span data-stu-id="99a4b-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99a4b-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="99a4b-121">Requirements</span></span>  
  
|<span data-ttu-id="99a4b-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="99a4b-122">MOF</span></span>|<span data-ttu-id="99a4b-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="99a4b-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="99a4b-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="99a4b-124">Namespace</span></span>|<span data-ttu-id="99a4b-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="99a4b-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99a4b-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="99a4b-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
