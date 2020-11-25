---
title: ISymUnmanagedWriter::Initialize — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: c702aa32e8c8d6d5c137f7968d1578715102180f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726864"
---
# <a name="isymunmanagedwriterinitialize-method"></a>ISymUnmanagedWriter::Initialize — Metoda

Ustawia interfejs emitujący metadane, z którym jest skojarzony ten składnik zapisywania i ustawia nazwę pliku wyjściowego, do którego będą zapisywane symbole debugowania.  
  
 Tę metodę można wywołać tylko raz i musi ona zostać wywołana przed innymi metodami zapisywania. Niektóre moduły zapisujące mogą wymagać nazwy pliku. Można jednak zawsze przekazać nazwę pliku do tej metody bez żadnego negatywnego wpływu na moduły zapisujące, które nie używają nazwy pliku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a>Parametry  

 `emitter`  
 podczas Wskaźnik do interfejsu emitującego metadane.  
  
 `filename`  
 podczas Nazwa pliku, do którego są zapisywane symbole debugowania. Jeśli nazwa pliku jest określona dla składnika zapisywania, który nie używa nazw plików, ten parametr jest ignorowany.  
  
 `pIStream`  
 podczas Jeśli ta wartość jest określona, moduł zapisujący symboli będzie emituje symbole do danego, <xref:System.Runtime.InteropServices.ComTypes.IStream> a nie do pliku określonego w `filename` parametrze. `pIStream`Parametr jest opcjonalny.  
  
 `fFullBuild`  
 [w] `true` Jeśli jest to pełna ponowna kompilacja; `false` Jeśli jest to kompilacja przyrostowa.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedWriter — Interfejs](isymunmanagedwriter-interface.md)
- [Initialize2, metoda](isymunmanagedwriter-initialize2-method.md)
