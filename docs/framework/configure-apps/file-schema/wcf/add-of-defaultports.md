---
title: <add> dla <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 2c6b5de51e6508965daf6022a47d12d8d73f2a4d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149130"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="23a43-102">\<add> dla \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="23a43-102">\<add> of \<defaultPorts></span></span>

<span data-ttu-id="23a43-103">Domyślny punkt końcowy komunikacji, do którego nasłuchuje aplikacja kliencka.</span><span class="sxs-lookup"><span data-stu-id="23a43-103">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="23a43-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="23a43-104">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23a43-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="23a43-105">Attributes and Elements</span></span>  

 <span data-ttu-id="23a43-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="23a43-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23a43-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="23a43-107">Attributes</span></span>  
  
|<span data-ttu-id="23a43-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="23a43-108">Attribute</span></span>|<span data-ttu-id="23a43-109">Opis</span><span class="sxs-lookup"><span data-stu-id="23a43-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23a43-110">port</span><span class="sxs-lookup"><span data-stu-id="23a43-110">port</span></span>|<span data-ttu-id="23a43-111">Liczba całkowita, która określa domyślny numer portu komunikacyjnego</span><span class="sxs-lookup"><span data-stu-id="23a43-111">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="23a43-112">schemat</span><span class="sxs-lookup"><span data-stu-id="23a43-112">scheme</span></span>|<span data-ttu-id="23a43-113">Ciąg określający grupę ustawień protokołu skojarzonych z portem komunikacyjnym.</span><span class="sxs-lookup"><span data-stu-id="23a43-113">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23a43-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="23a43-114">Child Elements</span></span>  

 <span data-ttu-id="23a43-115">Brak.</span><span class="sxs-lookup"><span data-stu-id="23a43-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23a43-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="23a43-116">Parent Elements</span></span>  
  
|<span data-ttu-id="23a43-117">Element</span><span class="sxs-lookup"><span data-stu-id="23a43-117">Element</span></span>|<span data-ttu-id="23a43-118">Opis</span><span class="sxs-lookup"><span data-stu-id="23a43-118">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="23a43-119">Kolekcja portów domyślnych wyświetla domyślne punkty końcowe komunikacji, do których nasłuchuje aplikacja kliencka.</span><span class="sxs-lookup"><span data-stu-id="23a43-119">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23a43-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="23a43-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
