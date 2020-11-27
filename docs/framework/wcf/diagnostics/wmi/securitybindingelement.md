---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 61eae75de04f75b6ad6e78d16569595732b3d28f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273311"
---
# <a name="securitybindingelement"></a><span data-ttu-id="4287a-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4287a-102">SecurityBindingElement</span></span>

<span data-ttu-id="4287a-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4287a-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4287a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4287a-104">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4287a-105">Metody</span><span class="sxs-lookup"><span data-stu-id="4287a-105">Methods</span></span>  

 <span data-ttu-id="4287a-106">Klasa elementu SecurityBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="4287a-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4287a-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="4287a-107">Properties</span></span>  

 <span data-ttu-id="4287a-108">Klasa elementu SecurityBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="4287a-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="4287a-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="4287a-109">DefaultAlgorithmSuite</span></span>  

 <span data-ttu-id="4287a-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="4287a-110">Data type: string</span></span>  
  
 <span data-ttu-id="4287a-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4287a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4287a-112">Określa algorytmy, które mają być używane z powiązaniem.</span><span class="sxs-lookup"><span data-stu-id="4287a-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="4287a-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="4287a-113">IncludeTimestamp</span></span>  

 <span data-ttu-id="4287a-114">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="4287a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4287a-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4287a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4287a-116">Wartość logiczna określająca, czy każdy komunikat zawiera sygnaturę czasową.</span><span class="sxs-lookup"><span data-stu-id="4287a-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="4287a-117">Entropia</span><span class="sxs-lookup"><span data-stu-id="4287a-117">KeyEntropyMode</span></span>  

 <span data-ttu-id="4287a-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="4287a-118">Data type: string</span></span>  
  
 <span data-ttu-id="4287a-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4287a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4287a-120">Źródło entropii używanej do tworzenia kluczy.</span><span class="sxs-lookup"><span data-stu-id="4287a-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="4287a-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4287a-121">LocalServiceSecuritySettings</span></span>  

 <span data-ttu-id="4287a-122">Typ danych: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4287a-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="4287a-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4287a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4287a-124">Specyficzne dla powiązania właściwości zabezpieczeń dla usługi lokalnej.</span><span class="sxs-lookup"><span data-stu-id="4287a-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="4287a-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="4287a-125">MessageSecurityVersion</span></span>  

 <span data-ttu-id="4287a-126">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="4287a-126">Data type: string</span></span>  
  
 <span data-ttu-id="4287a-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4287a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4287a-128">Wersja używana do zabezpieczenia komunikatów.</span><span class="sxs-lookup"><span data-stu-id="4287a-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="4287a-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="4287a-129">SecurityHeaderLayout</span></span>  

 <span data-ttu-id="4287a-130">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="4287a-130">Data type: string</span></span>  
  
 <span data-ttu-id="4287a-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="4287a-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4287a-132">Kolejność elementów w nagłówku zabezpieczeń dla tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="4287a-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4287a-133">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4287a-133">Requirements</span></span>  
  
|<span data-ttu-id="4287a-134">PLIK</span><span class="sxs-lookup"><span data-stu-id="4287a-134">MOF</span></span>|<span data-ttu-id="4287a-135">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="4287a-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4287a-136">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="4287a-136">Namespace</span></span>|<span data-ttu-id="4287a-137">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4287a-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4287a-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4287a-138">See also</span></span>

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
