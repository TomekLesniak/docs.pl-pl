---
title: <Parameter> — Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: 7e812ab60eb0a89eb868346733a8ea74e2f76d3e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287868"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="4e346-102">\<Parameter> — Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="4e346-102">\<Parameter> Element (.NET Native)</span></span>

<span data-ttu-id="4e346-103">Stosuje zasady odbicia do typu argumentu przesłanego do metody.</span><span class="sxs-lookup"><span data-stu-id="4e346-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e346-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4e346-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e346-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="4e346-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4e346-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="4e346-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e346-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="4e346-107">Attributes</span></span>  
  
|<span data-ttu-id="4e346-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="4e346-108">Attribute</span></span>|<span data-ttu-id="4e346-109">Typ atrybutu</span><span class="sxs-lookup"><span data-stu-id="4e346-109">Attribute type</span></span>|<span data-ttu-id="4e346-110">Opis</span><span class="sxs-lookup"><span data-stu-id="4e346-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="4e346-111">Ogólne</span><span class="sxs-lookup"><span data-stu-id="4e346-111">General</span></span>|<span data-ttu-id="4e346-112">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="4e346-112">Required attribute.</span></span> <span data-ttu-id="4e346-113">Nazwa parametru.</span><span class="sxs-lookup"><span data-stu-id="4e346-113">The parameter name.</span></span> <span data-ttu-id="4e346-114">Na przykład dla sygnatury metody `String.CompareTo(Object value)` wartość `Name` atrybutu to "value".</span><span class="sxs-lookup"><span data-stu-id="4e346-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="4e346-115">Odbicie</span><span class="sxs-lookup"><span data-stu-id="4e346-115">Reflection</span></span>|<span data-ttu-id="4e346-116">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-116">Optional attribute.</span></span> <span data-ttu-id="4e346-117">Kontroluje dostęp środowiska uruchomieniowego do konstruktorów, aby umożliwić aktywację wystąpień.</span><span class="sxs-lookup"><span data-stu-id="4e346-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="4e346-118">Odbicie</span><span class="sxs-lookup"><span data-stu-id="4e346-118">Reflection</span></span>|<span data-ttu-id="4e346-119">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-119">Optional attribute.</span></span> <span data-ttu-id="4e346-120">Steruje wykonywaniem zapytań dotyczących informacji o elementach programu, ale nie umożliwia dostępu do środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="4e346-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="4e346-121">Odbicie</span><span class="sxs-lookup"><span data-stu-id="4e346-121">Reflection</span></span>|<span data-ttu-id="4e346-122">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-122">Optional attribute.</span></span> <span data-ttu-id="4e346-123">Kontroluje dostęp środowiska uruchomieniowego do wszystkich elementów członkowskich typu, takich jak konstruktory, metody, pola, właściwości i zdarzenia, aby umożliwić programowanie dynamiczne.</span><span class="sxs-lookup"><span data-stu-id="4e346-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="4e346-124">Serializacja</span><span class="sxs-lookup"><span data-stu-id="4e346-124">Serialization</span></span>|<span data-ttu-id="4e346-125">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-125">Optional attribute.</span></span> <span data-ttu-id="4e346-126">Kontroluje dostęp środowiska uruchomieniowego do konstruktorów, pól i właściwości, aby umożliwić Serializowanie i deserializacja wystąpień typów przez biblioteki, takie jak serializator JSON Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="4e346-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="4e346-127">Serializacja</span><span class="sxs-lookup"><span data-stu-id="4e346-127">Serialization</span></span>|<span data-ttu-id="4e346-128">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-128">Optional attribute.</span></span> <span data-ttu-id="4e346-129">Kontroluje zasady dla serializacji, która używa <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="4e346-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="4e346-130">Serializacja</span><span class="sxs-lookup"><span data-stu-id="4e346-130">Serialization</span></span>|<span data-ttu-id="4e346-131">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-131">Optional attribute.</span></span> <span data-ttu-id="4e346-132">Kontroluje zasady dla serializacji JSON używającej <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="4e346-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="4e346-133">Serializacja</span><span class="sxs-lookup"><span data-stu-id="4e346-133">Serialization</span></span>|<span data-ttu-id="4e346-134">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-134">Optional attribute.</span></span> <span data-ttu-id="4e346-135">Kontroluje zasady dla serializacji XML, która używa <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="4e346-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="4e346-136">Interop</span><span class="sxs-lookup"><span data-stu-id="4e346-136">Interop</span></span>|<span data-ttu-id="4e346-137">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-137">Optional attribute.</span></span> <span data-ttu-id="4e346-138">Kontroluje zasady dotyczące organizowania typów odwołań do WinRT i COM.</span><span class="sxs-lookup"><span data-stu-id="4e346-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="4e346-139">Interop</span><span class="sxs-lookup"><span data-stu-id="4e346-139">Interop</span></span>|<span data-ttu-id="4e346-140">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-140">Optional attribute.</span></span> <span data-ttu-id="4e346-141">Steruje zasadami organizowania typów delegatów jako wskaźników funkcji do kodu natywnego.</span><span class="sxs-lookup"><span data-stu-id="4e346-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="4e346-142">Interop</span><span class="sxs-lookup"><span data-stu-id="4e346-142">Interop</span></span>|<span data-ttu-id="4e346-143">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="4e346-143">Optional attribute.</span></span> <span data-ttu-id="4e346-144">Steruje zasadami dotyczącymi organizowania typów wartości na kod natywny.</span><span class="sxs-lookup"><span data-stu-id="4e346-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="4e346-145">Atrybut nazwy</span><span class="sxs-lookup"><span data-stu-id="4e346-145">Name attribute</span></span>  
  
|<span data-ttu-id="4e346-146">Wartość</span><span class="sxs-lookup"><span data-stu-id="4e346-146">Value</span></span>|<span data-ttu-id="4e346-147">Opis</span><span class="sxs-lookup"><span data-stu-id="4e346-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e346-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="4e346-148">*parameter_name*</span></span>|<span data-ttu-id="4e346-149">Nazwa parametru metody, do którego zastosowano zasady.</span><span class="sxs-lookup"><span data-stu-id="4e346-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="4e346-150">Na przykład dla sygnatury metody `String.CompareTo(Object value)` wartość `Name` atrybutu to "value".</span><span class="sxs-lookup"><span data-stu-id="4e346-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="4e346-151">Wszystkie inne atrybuty</span><span class="sxs-lookup"><span data-stu-id="4e346-151">All other attributes</span></span>  
  
|<span data-ttu-id="4e346-152">Wartość</span><span class="sxs-lookup"><span data-stu-id="4e346-152">Value</span></span>|<span data-ttu-id="4e346-153">Opis</span><span class="sxs-lookup"><span data-stu-id="4e346-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e346-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="4e346-154">*policy_setting*</span></span>|<span data-ttu-id="4e346-155">Ustawienie, które ma zostać zastosowane do tego typu zasad.</span><span class="sxs-lookup"><span data-stu-id="4e346-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="4e346-156">Możliwe wartości to `All` , `Public` , `PublicAndInternal` , `Required Public` , `Required PublicAndInternal` i `Required All` .</span><span class="sxs-lookup"><span data-stu-id="4e346-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="4e346-157">Aby uzyskać więcej informacji, zobacz [Ustawienia zasad dyrektywy środowiska uruchomieniowego](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4e346-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e346-158">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="4e346-158">Child Elements</span></span>  

 <span data-ttu-id="4e346-159">Brak.</span><span class="sxs-lookup"><span data-stu-id="4e346-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e346-160">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="4e346-160">Parent Elements</span></span>  
  
|<span data-ttu-id="4e346-161">Element</span><span class="sxs-lookup"><span data-stu-id="4e346-161">Element</span></span>|<span data-ttu-id="4e346-162">Opis</span><span class="sxs-lookup"><span data-stu-id="4e346-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="4e346-163">Stosuje zasady odbicia środowiska uruchomieniowego do konstruktora lub metody.</span><span class="sxs-lookup"><span data-stu-id="4e346-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e346-164">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4e346-164">Remarks</span></span>  

 <span data-ttu-id="4e346-165">`<Parameter>`Element jest elementem podrzędnym [\<Method>](method-element-net-native.md) elementu i służy do stosowania zasad do określonego parametru metody.</span><span class="sxs-lookup"><span data-stu-id="4e346-165">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="4e346-166">Konkretny parametr metody jest określony według nazwy, a nie według typu.</span><span class="sxs-lookup"><span data-stu-id="4e346-166">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="4e346-167">Co najmniej jeden atrybut reprezentujący typ zasad, taki jak `Activate` lub `Dynamic` , musi być obecny.</span><span class="sxs-lookup"><span data-stu-id="4e346-167">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e346-168">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4e346-168">See also</span></span>

- [<span data-ttu-id="4e346-169">\<Method> Postaci</span><span class="sxs-lookup"><span data-stu-id="4e346-169">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="4e346-170">Dokumentacja pliku konfiguracji dyrektyw środowiska uruchomieniowego (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="4e346-170">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="4e346-171">Ustawienia zasad dyrektyw środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="4e346-171">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="4e346-172">Elementy dyrektyw środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="4e346-172">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
