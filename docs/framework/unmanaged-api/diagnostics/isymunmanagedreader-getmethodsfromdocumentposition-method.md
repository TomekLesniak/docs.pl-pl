---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: 5298dd0f53693d96b748f6c839660838fdfad4ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689553"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a>ISymUnmanagedReader::GetMethodsFromDocumentPosition — Metoda

Zwraca tablicę metod, z których każdy zawiera punkt przerwania w podanym miejscu w dokumencie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>Parametry  

 `document`  
 podczas Określony dokument.  
  
 `line`  
 podczas Wiersz określonego dokumentu.  
  
 `column`  
 podczas Kolumna określonego dokumentu.  
  
 `cMethod`  
 podczas Rozmiar `pRetVal` tablicy.  
  
 `pcMethod`  
 określoną Wskaźnik do zmiennej, która otrzymuje liczbę elementów zwracanych w `pRetVal` tablicy.  
  
 `pRetVal`  
 określoną Tablica wskaźników, z których każdy wskazuje obiekt [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) , który reprezentuje metodę zawierającą punkt przerwania.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedReader — Interfejs](isymunmanagedreader-interface.md)
