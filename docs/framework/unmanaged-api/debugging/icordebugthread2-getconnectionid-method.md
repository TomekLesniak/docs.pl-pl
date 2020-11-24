---
title: ICorDebugThread2::GetConnectionID — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
ms.openlocfilehash: 1507715e80761c871dfdb0b8d25dc708a2130678
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678691"
---
# <a name="icordebugthread2getconnectionid-method"></a>ICorDebugThread2::GetConnectionID — Metoda

Pobiera identyfikator połączenia dla tego obiektu ICorDebugThread2.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pdwConnectionId`  
 określoną `CONNID` Reprezentuje identyfikator połączenia.  
  
## <a name="remarks"></a>Uwagi  

 `GetConnectionID`Metoda zwraca zero w `pdwConnectionId` parametrze, jeśli ten wątek nie jest częścią połączenia.  
  
 Jeśli ten wątek jest połączony z wystąpieniem Microsoft SQL Server 2005 Analysis Services (SSAS), `CONNID` mapuje na identyfikator procesu serwera (SPID).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
