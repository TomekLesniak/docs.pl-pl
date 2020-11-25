---
title: GUID_ManagedName — Atrybut
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
ms.openlocfilehash: 0127b6894f1095521f1b24fc8c0424dc7db824b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721052"
---
# <a name="guid_managedname-attribute"></a><span data-ttu-id="df1c2-102">GUID_ManagedName — Atrybut</span><span class="sxs-lookup"><span data-stu-id="df1c2-102">GUID_ManagedName Attribute</span></span>

<span data-ttu-id="df1c2-103">Definiuje niestandardowy atrybut interfejsu, który określa nazwę zarządzanej przestrzeni nazw dla biblioteki modelu obiektów składnika (COM).</span><span class="sxs-lookup"><span data-stu-id="df1c2-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df1c2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="df1c2-104">Syntax</span></span>  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="df1c2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="df1c2-105">Parameters</span></span>  

 `value`  
 <span data-ttu-id="df1c2-106">Nazwa zarządzanej przestrzeni nazw dla biblioteki.</span><span class="sxs-lookup"><span data-stu-id="df1c2-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="df1c2-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="df1c2-107">Definition</span></span>  

 <span data-ttu-id="df1c2-108">`GUID_ManagedName` jest zdefiniowany w cor. h w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="df1c2-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="df1c2-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="df1c2-109">Remarks</span></span>  

 <span data-ttu-id="df1c2-110">Niestandardowy atrybut interfejsu definiuje metadane dla obiektu w bibliotece typów.</span><span class="sxs-lookup"><span data-stu-id="df1c2-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="df1c2-111">Użyj <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> lub, <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> Aby pobrać nazwę zarządzaną z atrybutu.</span><span class="sxs-lookup"><span data-stu-id="df1c2-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="df1c2-112">Aby uzyskać więcej informacji, zobacz [atrybuty interfejsu](/cpp/windows/attributes/interface-attributes) w dokumentacji referencyjnej Visual C++.</span><span class="sxs-lookup"><span data-stu-id="df1c2-112">For more information, see [Interface Attributes](/cpp/windows/attributes/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df1c2-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="df1c2-113">Example</span></span>  

 <span data-ttu-id="df1c2-114">Poniższy przykład przedstawia definicję biblioteki przy użyciu `GUID_ManagedName` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="df1c2-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
```idl
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="df1c2-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="df1c2-115">Requirements</span></span>  

 <span data-ttu-id="df1c2-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="df1c2-116">**Header:** Cor.h</span></span>
