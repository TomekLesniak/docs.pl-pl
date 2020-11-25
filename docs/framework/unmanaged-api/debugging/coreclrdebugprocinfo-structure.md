---
title: CoreClrDebugProcInfo — Struktura
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 5996393fd1a0504f9c3d3f9f07aa0e3d886a0787
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719700"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="aa2f4-102">CoreClrDebugProcInfo — Struktura</span><span class="sxs-lookup"><span data-stu-id="aa2f4-102">CoreClrDebugProcInfo Structure</span></span>

<span data-ttu-id="aa2f4-103">Reprezentuje proces, który jest uruchomiony na komputerze zdalnym.</span><span class="sxs-lookup"><span data-stu-id="aa2f4-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa2f4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="aa2f4-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="aa2f4-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="aa2f4-105">Members</span></span>  
  
|<span data-ttu-id="aa2f4-106">Członek</span><span class="sxs-lookup"><span data-stu-id="aa2f4-106">Member</span></span>|<span data-ttu-id="aa2f4-107">Opis</span><span class="sxs-lookup"><span data-stu-id="aa2f4-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="aa2f4-108">Identyfikator procesu przypisany do systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="aa2f4-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="aa2f4-109">Identyfikator procesu, który jest przypisywany przez zdalny serwer proxy na komputerze docelowym.</span><span class="sxs-lookup"><span data-stu-id="aa2f4-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="aa2f4-110">Ten identyfikator jest odtwarzany rzadziej niż identyfikator systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="aa2f4-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="aa2f4-111">Wiersz polecenia procesu.</span><span class="sxs-lookup"><span data-stu-id="aa2f4-111">Command-line of the process.</span></span> <span data-ttu-id="aa2f4-112">Ten element członkowski może zostać obcięty.</span><span class="sxs-lookup"><span data-stu-id="aa2f4-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa2f4-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="aa2f4-113">Requirements</span></span>  

 <span data-ttu-id="aa2f4-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa2f4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa2f4-115">**Nagłówek:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="aa2f4-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="aa2f4-116">**Biblioteka:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="aa2f4-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="aa2f4-117">**.NET Framework wersje:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="aa2f4-117">**.NET Framework Versions:** 3.5 SP1</span></span>
