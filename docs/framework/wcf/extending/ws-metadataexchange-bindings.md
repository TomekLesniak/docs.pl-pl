---
title: Powiązania elementu WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293991"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="75cc5-102">Powiązania elementu WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="75cc5-102">WS-MetadataExchange Bindings</span></span>

<span data-ttu-id="75cc5-103">W tym temacie opisano, jak domyślne powiązania wymiany metadanych są konstruowane dla różnych transportów.</span><span class="sxs-lookup"><span data-stu-id="75cc5-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="75cc5-104">Domyślne powiązania</span><span class="sxs-lookup"><span data-stu-id="75cc5-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="75cc5-105">Domyślna nazwa powiązania</span><span class="sxs-lookup"><span data-stu-id="75cc5-105">Default Binding Name</span></span>|<span data-ttu-id="75cc5-106">Sposób konstruowania powiązania</span><span class="sxs-lookup"><span data-stu-id="75cc5-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="75cc5-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="75cc5-107">mexHttpBinding</span></span>|<span data-ttu-id="75cc5-108"><xref:System.ServiceModel.WSHttpBinding>Z wyłączonym zabezpieczeniami na poziomie transportu.</span><span class="sxs-lookup"><span data-stu-id="75cc5-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="75cc5-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="75cc5-109">mexHttpsBinding</span></span>|<span data-ttu-id="75cc5-110">A <xref:System.ServiceModel.WSHttpBinding> który obsługuje zabezpieczenia na poziomie transportu.</span><span class="sxs-lookup"><span data-stu-id="75cc5-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="75cc5-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="75cc5-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="75cc5-112">A przy  <xref:System.ServiceModel.Channels.CustomBinding> <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> użyciu wartości domyślnych.</span><span class="sxs-lookup"><span data-stu-id="75cc5-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="75cc5-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="75cc5-113">mexTcpBinding</span></span>|<span data-ttu-id="75cc5-114">A <xref:System.ServiceModel.Channels.CustomBinding> z <xref:System.ServiceModel.Channels.TcpTransportBindingElement> wartościami domyślnymi.</span><span class="sxs-lookup"><span data-stu-id="75cc5-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
