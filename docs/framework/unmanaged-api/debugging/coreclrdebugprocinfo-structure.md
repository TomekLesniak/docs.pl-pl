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
# <a name="coreclrdebugprocinfo-structure"></a>CoreClrDebugProcInfo — Struktura

Reprezentuje proces, który jest uruchomiony na komputerze zdalnym.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`m_dwPID`|Identyfikator procesu przypisany do systemu operacyjnego.|  
|`m_dwInternalID`|Identyfikator procesu, który jest przypisywany przez zdalny serwer proxy na komputerze docelowym. Ten identyfikator jest odtwarzany rzadziej niż identyfikator systemu operacyjnego.|  
|`m_wszName`|Wiersz polecenia procesu. Ten element członkowski może zostać obcięty.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteka:** mscordbi_macx86.dll  
  
 **.NET Framework wersje:** 3,5 SP1
