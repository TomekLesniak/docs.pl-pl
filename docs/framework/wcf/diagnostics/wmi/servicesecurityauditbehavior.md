---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 9da8f77ee8ea5dc8b22ac5c0cb5113e906c5dc78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262271"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="85c0c-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="85c0c-102">ServiceSecurityAuditBehavior</span></span>

<span data-ttu-id="85c0c-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="85c0c-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c0c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="85c0c-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="85c0c-105">Metody</span><span class="sxs-lookup"><span data-stu-id="85c0c-105">Methods</span></span>  

 <span data-ttu-id="85c0c-106">Klasa ServiceSecurityAuditBehavior nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="85c0c-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="85c0c-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="85c0c-107">Properties</span></span>  

 <span data-ttu-id="85c0c-108">Klasa ServiceSecurityAuditBehavior ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="85c0c-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="85c0c-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="85c0c-109">AuditLogLocation</span></span>  

 <span data-ttu-id="85c0c-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="85c0c-110">Data type: string</span></span>  
  
 <span data-ttu-id="85c0c-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="85c0c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="85c0c-112">Lokalizacja dziennika inspekcji.</span><span class="sxs-lookup"><span data-stu-id="85c0c-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="85c0c-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="85c0c-113">MessageAuthenticationAuditLevel</span></span>  

 <span data-ttu-id="85c0c-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="85c0c-114">Data type: string</span></span>  
  
 <span data-ttu-id="85c0c-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="85c0c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="85c0c-116">Typ poziomu uwierzytelniania wiadomości, który jest używany do rejestrowania zdarzeń inspekcji.</span><span class="sxs-lookup"><span data-stu-id="85c0c-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="85c0c-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="85c0c-117">ServiceAuthorizationAuditLevel</span></span>  

 <span data-ttu-id="85c0c-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="85c0c-118">Data type: string</span></span>  
  
 <span data-ttu-id="85c0c-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="85c0c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="85c0c-120">Typy zdarzeń autoryzacji, które są rejestrowane w dzienniku inspekcji.</span><span class="sxs-lookup"><span data-stu-id="85c0c-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="85c0c-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="85c0c-121">SuppressAuditFailure</span></span>  

 <span data-ttu-id="85c0c-122">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="85c0c-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="85c0c-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="85c0c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="85c0c-124">Wartość logiczna określająca zachowanie w przypadku pomijania błędów zapisu do dziennika inspekcji.</span><span class="sxs-lookup"><span data-stu-id="85c0c-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c0c-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="85c0c-125">Requirements</span></span>  
  
|<span data-ttu-id="85c0c-126">PLIK</span><span class="sxs-lookup"><span data-stu-id="85c0c-126">MOF</span></span>|<span data-ttu-id="85c0c-127">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="85c0c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="85c0c-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="85c0c-128">Namespace</span></span>|<span data-ttu-id="85c0c-129">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="85c0c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85c0c-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="85c0c-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
