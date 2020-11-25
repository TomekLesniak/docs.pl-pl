---
title: IsFrameworkAssembly — Funkcja
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: 828c7660d6c006e700302d119ce4caf7d76e5d84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728566"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="6c83f-102">IsFrameworkAssembly — Funkcja</span><span class="sxs-lookup"><span data-stu-id="6c83f-102">IsFrameworkAssembly Function</span></span>

<span data-ttu-id="6c83f-103">Pobiera wartość wskazującą, czy określony zestaw jest zarządzany.</span><span class="sxs-lookup"><span data-stu-id="6c83f-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c83f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6c83f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c83f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6c83f-105">Parameters</span></span>  

 `pwzAssemblyReference`  
 <span data-ttu-id="6c83f-106">podczas Nazwa zestawu do sprawdzenia.</span><span class="sxs-lookup"><span data-stu-id="6c83f-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="6c83f-107">określoną Wartość logiczna wskazująca, czy zestaw jest zarządzany.</span><span class="sxs-lookup"><span data-stu-id="6c83f-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="6c83f-108">podczas Niekanoniczny ciąg, który zawiera unikatową tożsamość zestawu.</span><span class="sxs-lookup"><span data-stu-id="6c83f-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="6c83f-109">podczas Rozmiar `pwzFrameworkAssemblyIdentity` .</span><span class="sxs-lookup"><span data-stu-id="6c83f-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c83f-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6c83f-110">Remarks</span></span>  

 <span data-ttu-id="6c83f-111">`pwzAssemblyReference`Parametr jest wskaźnikiem do ciągu znaków, który zawiera nazwę zestawu.</span><span class="sxs-lookup"><span data-stu-id="6c83f-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="6c83f-112">Jeśli ten zestaw jest częścią .NET Framework, `pbIsFrameworkAssembly` parametr będzie zawierać wartość logiczną `true` .</span><span class="sxs-lookup"><span data-stu-id="6c83f-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="6c83f-113">Jeśli nazwany zestaw nie jest częścią .NET Framework lub jeśli `pwzAssemblyReference` parametr nie ma nazwy zestawu, `pbIsFrameworkAssembly` będzie zawierać wartość logiczną `false` .</span><span class="sxs-lookup"><span data-stu-id="6c83f-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c83f-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6c83f-114">Requirements</span></span>  

 <span data-ttu-id="6c83f-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c83f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c83f-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6c83f-116">See also</span></span>

- [<span data-ttu-id="6c83f-117">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="6c83f-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
