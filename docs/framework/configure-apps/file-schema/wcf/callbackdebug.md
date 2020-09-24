---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 02632cc3f668bb9e4cc6f8c9726d7bcb3cab2c5d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183822"
---
# \<callbackDebug>

<span data-ttu-id="eb69c-101">Określa debugowanie usługi dla obiektu wywołania zwrotnego Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eb69c-101">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**  
  
## <a name="syntax"></a><span data-ttu-id="eb69c-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="eb69c-102">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="eb69c-103">Typ</span><span class="sxs-lookup"><span data-stu-id="eb69c-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb69c-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="eb69c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="eb69c-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="eb69c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb69c-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="eb69c-106">Attributes</span></span>  
  
|<span data-ttu-id="eb69c-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="eb69c-107">Attribute</span></span>|<span data-ttu-id="eb69c-108">Opis</span><span class="sxs-lookup"><span data-stu-id="eb69c-108">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="eb69c-109">Wartość określająca, czy obiekty wywołania zwrotnego klienta zwracają informacje o zarządzanym wyjątku w błędach protokołu SOAP z powrotem do usługi.</span><span class="sxs-lookup"><span data-stu-id="eb69c-109">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="eb69c-110">Jeśli ten atrybut zostanie ustawiony na `true` programowo, można włączyć przepływ informacji o zarządzanym wyjątku w obiekcie wywołania zwrotnego klienta z powrotem do usługi na potrzeby debugowania.</span><span class="sxs-lookup"><span data-stu-id="eb69c-110">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="eb69c-111">**Przestroga:**  Zwrócenie informacji o wyjątku zarządzanym do klientów może stanowić zagrożenie bezpieczeństwa.</span><span class="sxs-lookup"><span data-stu-id="eb69c-111">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="eb69c-112">Wynika to z faktu, że szczegóły wyjątku ujawniają informacje o implementacji wewnętrznej usługi, która może być używana przez nieautoryzowanych klientów.</span><span class="sxs-lookup"><span data-stu-id="eb69c-112">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb69c-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="eb69c-113">Child Elements</span></span>  

 <span data-ttu-id="eb69c-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="eb69c-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb69c-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="eb69c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="eb69c-116">Element</span><span class="sxs-lookup"><span data-stu-id="eb69c-116">Element</span></span>|<span data-ttu-id="eb69c-117">Opis</span><span class="sxs-lookup"><span data-stu-id="eb69c-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="eb69c-118">Określa zachowanie punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="eb69c-118">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb69c-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eb69c-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
