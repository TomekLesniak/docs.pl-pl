---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 76cc619aed4ba2b944a8d11dc454a40368a4068c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269083"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="74238-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="74238-102">OperationBehaviorAttribute</span></span>

<span data-ttu-id="74238-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="74238-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74238-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="74238-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="74238-105">Metody</span><span class="sxs-lookup"><span data-stu-id="74238-105">Methods</span></span>  

 <span data-ttu-id="74238-106">Klasa OperationBehaviorAttribute będący nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="74238-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="74238-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="74238-107">Properties</span></span>  

 <span data-ttu-id="74238-108">Klasa OperationBehaviorAttribute będący ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="74238-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="74238-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="74238-109">AutoDisposeParameters</span></span>  

 <span data-ttu-id="74238-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="74238-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="74238-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="74238-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74238-112">Stan funkcji autodispose dla parametrów.</span><span class="sxs-lookup"><span data-stu-id="74238-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="74238-113">Personifikacja</span><span class="sxs-lookup"><span data-stu-id="74238-113">Impersonation</span></span>  

 <span data-ttu-id="74238-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="74238-114">Data type: string</span></span>  
  
 <span data-ttu-id="74238-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="74238-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74238-116">Wskazuje poziom personifikacji wywołującego obsługiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="74238-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="74238-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="74238-117">ReleaseInstanceMode</span></span>  

 <span data-ttu-id="74238-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="74238-118">Data type: string</span></span>  
  
 <span data-ttu-id="74238-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="74238-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74238-120">Wskazuje, kiedy w trakcie wywołania operacji w celu odtworzenia obiektu.</span><span class="sxs-lookup"><span data-stu-id="74238-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="74238-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="74238-121">TransactionAutoComplete</span></span>  

 <span data-ttu-id="74238-122">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="74238-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="74238-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="74238-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74238-124">Wskazuje, czy bieżąca transakcja ma być automatycznie przekazywana, jeśli nie wystąpią żadne Nieobsłużone wyjątki.</span><span class="sxs-lookup"><span data-stu-id="74238-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="74238-125">Ustawione</span><span class="sxs-lookup"><span data-stu-id="74238-125">TransactionScopeRequired</span></span>  

 <span data-ttu-id="74238-126">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="74238-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="74238-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="74238-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74238-128">Wskazuje, czy operacja wymaga transakcji.</span><span class="sxs-lookup"><span data-stu-id="74238-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74238-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="74238-129">Requirements</span></span>  
  
|<span data-ttu-id="74238-130">PLIK</span><span class="sxs-lookup"><span data-stu-id="74238-130">MOF</span></span>|<span data-ttu-id="74238-131">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="74238-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="74238-132">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="74238-132">Namespace</span></span>|<span data-ttu-id="74238-133">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="74238-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74238-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="74238-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
