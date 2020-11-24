---
title: ISymUnmanagedReader::UpdateSymbolStore — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: 6670d985eed4c55550b23d3f4110ee20f3b75661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675831"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>ISymUnmanagedReader::UpdateSymbolStore — Metoda

Aktualizuje istniejący magazyn symboli przy użyciu magazynu symboli różnicowych. Ta metoda jest używana w scenariuszach Edytuj i Kontynuuj, aby zaktualizować magazyn symboli tak, aby pasował do różnic w oryginalnym przenośnym pliku wykonywalnym (PE).  
  
> [!NOTE]
> Należy określić tylko jeden z `filename` `pIStream` parametrów lub, ale nie oba. Jeśli `filename` jest określony, magazyn symboli zostanie zaktualizowany przy użyciu symboli w tym pliku. Jeśli `pIStream` jest określony, magazyn zostanie zaktualizowany o dane z <xref:System.Runtime.InteropServices.ComTypes.IStream> .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parametry  

 `filename`  
 podczas Nazwa pliku, który zawiera magazyn symboli.  
  
 `pIStream`  
 podczas Strumień pliku używany jako alternatywa dla `filename` parametru.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedReader — Interfejs](isymunmanagedreader-interface.md)
