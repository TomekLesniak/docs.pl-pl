---
title: <add> dla <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7d055d4933f1ad625d6842f91a140f668c05c64e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204999"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="ee530-102">\<add> dla \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="ee530-102">\<add> of \<namespaceTable></span></span>

<span data-ttu-id="ee530-103">Reprezentuje element konfiguracji, który zawiera przestrzeń nazw do mapowania prefiksów, które mogą być następnie używane w filtrach XPath dla routingu.</span><span class="sxs-lookup"><span data-stu-id="ee530-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ee530-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ee530-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee530-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="ee530-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ee530-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="ee530-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee530-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="ee530-107">Attributes</span></span>  
  
|<span data-ttu-id="ee530-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="ee530-108">Attribute</span></span>|<span data-ttu-id="ee530-109">Opis</span><span class="sxs-lookup"><span data-stu-id="ee530-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee530-110">namespace</span><span class="sxs-lookup"><span data-stu-id="ee530-110">namespace</span></span>|<span data-ttu-id="ee530-111">Ciąg zawierający przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="ee530-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="ee530-112">prefiks</span><span class="sxs-lookup"><span data-stu-id="ee530-112">prefix</span></span>|<span data-ttu-id="ee530-113">Ciąg zawierający prefiks dla tej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="ee530-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee530-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="ee530-114">Child Elements</span></span>  

 <span data-ttu-id="ee530-115">Brak.</span><span class="sxs-lookup"><span data-stu-id="ee530-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee530-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="ee530-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ee530-117">Element</span><span class="sxs-lookup"><span data-stu-id="ee530-117">Element</span></span>|<span data-ttu-id="ee530-118">Opis</span><span class="sxs-lookup"><span data-stu-id="ee530-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="ee530-119">Reprezentuje sekcję konfiguracji definiującą zestaw elementów zawierających przestrzeń nazw do mapowania prefiksów, które mogą być następnie używane w filtrach XPath dla routingu.</span><span class="sxs-lookup"><span data-stu-id="ee530-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee530-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ee530-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
