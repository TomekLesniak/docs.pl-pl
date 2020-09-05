---
ms.openlocfilehash: f61e5670334f4d3674fd0b008d1a476b14c7ba4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496780"
---
### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a><span data-ttu-id="7fda2-101">Wywołanie atrybutu. GetCustomAttributes — na właściwości indeksatora nie zgłasza już AmbiguousMatchException —, jeśli niejednoznaczność może zostać rozpoznana przez typ indeksu</span><span class="sxs-lookup"><span data-stu-id="7fda2-101">Calling Attribute.GetCustomAttributes on an indexer property no longer throws AmbiguousMatchException if the ambiguity can be resolved by index's type</span></span>

#### <a name="details"></a><span data-ttu-id="7fda2-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7fda2-102">Details</span></span>

<span data-ttu-id="7fda2-103">Przed .NET Framework 4,6 wywoływanie <code>GetCustomAttribute(s)</code> Właściwości indeksatora, która różni się od innej właściwości tylko typem indeksu, spowoduje powstanie <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="7fda2-103">Prior to the .NET Framework 4.6, calling <code>GetCustomAttribute(s)</code> on an indexer property which differed from another property only by the type of the index would result in an <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>.</span></span> <span data-ttu-id="7fda2-104">Począwszy od .NET Framework 4,6, atrybuty właściwości zostaną poprawnie zwrócone.</span><span class="sxs-lookup"><span data-stu-id="7fda2-104">Beginning in the .NET Framework 4.6, the property's attributes will be correctly returned.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7fda2-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="7fda2-105">Suggestion</span></span>

<span data-ttu-id="7fda2-106">Należy pamiętać, że elementy GetCustomAttribute będą działać częściej teraz.</span><span class="sxs-lookup"><span data-stu-id="7fda2-106">Be aware that GetCustomAttribute(s) will work more frequently now.</span></span> <span data-ttu-id="7fda2-107">Jeśli aplikacja była wcześniej uzależniona od <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName> , odbicie powinno być teraz używane do jawnego wyszukiwania wielu indeksatorów.</span><span class="sxs-lookup"><span data-stu-id="7fda2-107">If an app was previously relying on the <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>, reflection should now be used to explicitly look for multiple indexers, instead.</span></span>

| <span data-ttu-id="7fda2-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="7fda2-108">Name</span></span>    | <span data-ttu-id="7fda2-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="7fda2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7fda2-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="7fda2-110">Scope</span></span>   |<span data-ttu-id="7fda2-111">Edge</span><span class="sxs-lookup"><span data-stu-id="7fda2-111">Edge</span></span>|
|<span data-ttu-id="7fda2-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="7fda2-112">Version</span></span>|<span data-ttu-id="7fda2-113">4,6</span><span class="sxs-lookup"><span data-stu-id="7fda2-113">4.6</span></span>|
|<span data-ttu-id="7fda2-114">Typ</span><span class="sxs-lookup"><span data-stu-id="7fda2-114">Type</span></span>|<span data-ttu-id="7fda2-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="7fda2-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7fda2-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="7fda2-116">Affected APIs</span></span>

- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo,System.Boolean)``
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo,System.Boolean)``

-->
