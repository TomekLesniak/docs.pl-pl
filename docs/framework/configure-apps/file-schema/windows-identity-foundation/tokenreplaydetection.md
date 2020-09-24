---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: df512960b522f17dc9247bb5959e246c8c1f15b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169807"
---
# \<tokenReplayDetection>

<span data-ttu-id="d660e-101">Włącza wykrywanie powtarzania tokenów i określa czas wygaśnięcia tokenów.</span><span class="sxs-lookup"><span data-stu-id="d660e-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="d660e-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="d660e-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="d660e-103">Typ</span><span class="sxs-lookup"><span data-stu-id="d660e-103">Type</span></span>  

 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d660e-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d660e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d660e-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d660e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d660e-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d660e-106">Attributes</span></span>  
  
|<span data-ttu-id="d660e-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="d660e-107">Attribute</span></span>|<span data-ttu-id="d660e-108">Opis</span><span class="sxs-lookup"><span data-stu-id="d660e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d660e-109">enabled</span><span class="sxs-lookup"><span data-stu-id="d660e-109">enabled</span></span>|<span data-ttu-id="d660e-110">Wartość określająca, czy jest włączone wykrywanie powtarzania tokenów; wartość "true" w celu włączenia wykrywania powtarzania tokenu.</span><span class="sxs-lookup"><span data-stu-id="d660e-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="d660e-111">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="d660e-111">expirationPeriod</span></span>|<span data-ttu-id="d660e-112">A <xref:System.TimeSpan> , która określa maksymalny czas, po upływie którego element zostanie uznany za wygasły i usunięty z pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="d660e-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="d660e-113">Aby uzyskać więcej informacji na temat sposobu określania <xref:System.TimeSpan> wartości, zobacz [wartości TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="d660e-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d660e-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d660e-114">Child Elements</span></span>  

 <span data-ttu-id="d660e-115">Brak</span><span class="sxs-lookup"><span data-stu-id="d660e-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d660e-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d660e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d660e-117">Element</span><span class="sxs-lookup"><span data-stu-id="d660e-117">Element</span></span>|<span data-ttu-id="d660e-118">Opis</span><span class="sxs-lookup"><span data-stu-id="d660e-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="d660e-119">Określa ustawienia tożsamości na poziomie usług.</span><span class="sxs-lookup"><span data-stu-id="d660e-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d660e-120">Zapewnia konfigurację kolekcji programów obsługi tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="d660e-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d660e-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d660e-121">Remarks</span></span>  

 <span data-ttu-id="d660e-122">`<tokenReplayDetection>`Element można określić na poziomie usługi pod `<identityConfiguration>` elementem lub na poziomie kolekcji programu obsługi tokenów zabezpieczających w ramach `<securityTokenHandlerConfiguration>` elementu.</span><span class="sxs-lookup"><span data-stu-id="d660e-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="d660e-123">Ustawienia w kolekcji obsługi tokenów zastępują te określone w usłudze.</span><span class="sxs-lookup"><span data-stu-id="d660e-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="d660e-124">Typ pamięci podręcznej powtarzania tokenów jest określany przez [\<tokenReplayCache>](tokenreplaycache.md) element.</span><span class="sxs-lookup"><span data-stu-id="d660e-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
