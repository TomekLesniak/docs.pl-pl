---
title: CorOpenFlags — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
ms.openlocfilehash: e474cac6437413565a1ebddfa88c3e228fe59d41
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556352"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="00d26-102">CorOpenFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="00d26-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="00d26-103">Zawiera wartości flag kontrolujące zachowanie metadanych podczas otwierania plików manifestu.</span><span class="sxs-lookup"><span data-stu-id="00d26-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d26-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="00d26-104">Syntax</span></span>  
  
```cpp  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="00d26-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="00d26-105">Members</span></span>  
  
|<span data-ttu-id="00d26-106">Członek</span><span class="sxs-lookup"><span data-stu-id="00d26-106">Member</span></span>|<span data-ttu-id="00d26-107">Opis</span><span class="sxs-lookup"><span data-stu-id="00d26-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="00d26-108">Wskazuje, że plik powinien być otwarty tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="00d26-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="00d26-109">Wskazuje, że plik powinien być otwarty do zapisu.</span><span class="sxs-lookup"><span data-stu-id="00d26-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="00d26-110">Jeśli używasz `ofWrite` flagi podczas otwierania pliku winmd, należy również przekazać `ofNoTransform` flagę.</span><span class="sxs-lookup"><span data-stu-id="00d26-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="00d26-111">Maska do odczytu i zapisu.</span><span class="sxs-lookup"><span data-stu-id="00d26-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="00d26-112">Wskazuje, że plik powinien być odczytywany do pamięci.</span><span class="sxs-lookup"><span data-stu-id="00d26-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="00d26-113">Metadane powinny zachować własną kopię.</span><span class="sxs-lookup"><span data-stu-id="00d26-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="00d26-114">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="00d26-114">Obsolete.</span></span> <span data-ttu-id="00d26-115">Ta flaga jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="00d26-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="00d26-116">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="00d26-116">Obsolete.</span></span> <span data-ttu-id="00d26-117">Ta flaga jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="00d26-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="00d26-118">Wskazuje, że plik powinien być otwarty do odczytu i że wywołanie `QueryInterface` dla elementu [IMetaDataEmit](imetadataemit-interface.md) nie może zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="00d26-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="00d26-119">Wskazuje, że pamięć została przypisana przy użyciu wywołania do [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) i zostanie zwolniona z metadanych.</span><span class="sxs-lookup"><span data-stu-id="00d26-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="00d26-120">Nieaktualne.</span><span class="sxs-lookup"><span data-stu-id="00d26-120">Obsolete.</span></span> <span data-ttu-id="00d26-121">Ta flaga jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="00d26-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="00d26-122">Wskazuje, że należy wyłączyć automatyczne transformacje plików WinMD.</span><span class="sxs-lookup"><span data-stu-id="00d26-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="00d26-123">Innymi słowy, projekcja typu środowisko wykonawcze systemu Windows do typu .NET Framework powinna być wyłączona.</span><span class="sxs-lookup"><span data-stu-id="00d26-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="00d26-124">Aby uzyskać więcej informacji, zobacz [środowisko wykonawcze systemu Windows i środowisko CLR poniżej wystawcy z platformą .NET i środowisko wykonawcze systemu Windows](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span><span class="sxs-lookup"><span data-stu-id="00d26-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span></span>|  
|`ofReserved1`|<span data-ttu-id="00d26-125">Zarezerwowane do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="00d26-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="00d26-126">Zarezerwowane do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="00d26-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="00d26-127">Zarezerwowane do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="00d26-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00d26-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="00d26-128">Requirements</span></span>  
 <span data-ttu-id="00d26-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00d26-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00d26-130">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="00d26-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="00d26-131">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00d26-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d26-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="00d26-132">See also</span></span>

- [<span data-ttu-id="00d26-133">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="00d26-133">Metadata Enumerations</span></span>](metadata-enumerations.md)
