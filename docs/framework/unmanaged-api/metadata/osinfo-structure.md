---
title: OSINFO — Struktura
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: 49e29cc0367d5162dffcd641b163fd7b9a56ffd0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672893"
---
# <a name="osinfo-structure"></a><span data-ttu-id="22236-102">OSINFO — Struktura</span><span class="sxs-lookup"><span data-stu-id="22236-102">OSINFO Structure</span></span>

<span data-ttu-id="22236-103">Zawiera szczegółowe informacje o systemie operacyjnym dla zestawu lub modułu.</span><span class="sxs-lookup"><span data-stu-id="22236-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22236-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="22236-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="22236-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="22236-105">Members</span></span>  
  
|<span data-ttu-id="22236-106">Członek</span><span class="sxs-lookup"><span data-stu-id="22236-106">Member</span></span>|<span data-ttu-id="22236-107">Opis</span><span class="sxs-lookup"><span data-stu-id="22236-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="22236-108">Jedna z wartości identyfikatora zdefiniowanych przez funkcję platformy Microsoft Windows `GetVersionEx` .</span><span class="sxs-lookup"><span data-stu-id="22236-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="22236-109">Obsługiwane są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="22236-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="22236-110">-VER_PLATFORM_WIN32s lub 0x0000, aby określić system Microsoft Windows 3,1.</span><span class="sxs-lookup"><span data-stu-id="22236-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="22236-111">-VER_PLATFORM_WIN32_WINDOWS lub 0x0001, aby określić z nich systemy Windows 95, Windows 98 lub systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="22236-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="22236-112">-VER_PLATFORM_WIN32_NT lub 0x0002, aby określić system Windows NT lub systemy operacyjne, które są od niego podrzędne.</span><span class="sxs-lookup"><span data-stu-id="22236-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="22236-113">Wersja główna systemu operacyjnego lub wartość zerowa wskazująca dowolną wersję.</span><span class="sxs-lookup"><span data-stu-id="22236-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="22236-114">Wersja pomocnicza systemu operacyjnego lub wartość zerowa wskazująca dowolną wersję.</span><span class="sxs-lookup"><span data-stu-id="22236-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22236-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="22236-115">Remarks</span></span>  

 <span data-ttu-id="22236-116">`OSINFO` jest oparty na `OSVERSIONINFOEX` strukturze, która jest używana w wywołaniach funkcji platformy Microsoft Windows `GetVersionEx` .</span><span class="sxs-lookup"><span data-stu-id="22236-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="22236-117">Ta struktura jest używana przez strukturę ASSEMBLYMETADATA, aby wskazać jej obsługę systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="22236-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22236-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="22236-118">Requirements</span></span>  

 <span data-ttu-id="22236-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22236-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22236-120">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="22236-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22236-121">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22236-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22236-122">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22236-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22236-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="22236-123">See also</span></span>

- [<span data-ttu-id="22236-124">Metadane — Struktury</span><span class="sxs-lookup"><span data-stu-id="22236-124">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="22236-125">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="22236-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
