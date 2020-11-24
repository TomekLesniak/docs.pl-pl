---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 40b944f6a1204bfe506ed64408be30f68adf3170
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675259"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags — Metoda

Ustawia flagi, które muszą być osadzone we wstępnie skompilowanym obrazie, aby środowisko uruchomieniowe ładowało ten obraz do bieżącego procesu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pdwFlags`  
 podczas Wartość wyliczenia [CorDebugJITCompilerFlags —](cordebugjitcompilerflags-enumeration.md) , która określa flagi kompilatora używane do wybierania poprawnego prekompilowanego obrazu.  
  
## <a name="remarks"></a>Uwagi  

 `SetDesiredNGENCompilerFlags`Metoda określa flagi, które muszą być osadzone we wstępnie skompilowanym obrazie, aby środowisko uruchomieniowe załadowało ten obraz do tego procesu. Flagi ustawione za pomocą tej metody są używane tylko do wybierania poprawnego prekompilowanego obrazu. Jeśli taki obraz nie istnieje, środowisko uruchomieniowe załaduje obraz języka pośredniego firmy Microsoft (MSIL) oraz kompilator just-in-Time (JIT). W takim przypadku debuger musi nadal używać metody [ICorDebugModule2:: SetJITCompilerFlags —](icordebugmodule2-setjitcompilerflags-method.md) , aby ustawić flagi zgodnie z potrzebami kompilacji JIT.  
  
 Jeśli obraz jest ładowany, ale niektóre kompilacje JIT muszą mieć miejsce dla tego obrazu (w przypadku, gdy obraz zawiera ogólne) flagi kompilatora określone przez `SetDesiredNGENCompilerFlags` metodę zostaną zastosowane do kompilacji dodatkowej JIT.  
  
 `SetDesiredNGENCompilerFlags`Metoda musi być wywoływana podczas wywołania zwrotnego [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . Próby wywołania `SetDesiredNGENCompilerFlags` metody później zakończą się niepowodzeniem. Ponadto program próbuje ustawić flagi, które nie są zdefiniowane w `CorDebugJITCompilerFlags` wyliczeniu lub które nie są dozwolone dla danego procesu, zakończą się niepowodzeniem.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebug — Interfejs](icordebug-interface.md)
- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
