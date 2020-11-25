---
title: ISymUnmanagedDocument::GetURL — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
ms.openlocfilehash: c862b6d3bfa415b622b68898db1ff30c6759e8f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726941"
---
# <a name="isymunmanageddocumentgeturl-method"></a>ISymUnmanagedDocument::GetURL — Metoda

Zwraca adres URL (Uniform Resource Locator) dla tego dokumentu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a>Parametry  

 `cchUrl`  
 podczas Rozmiar (w znakach) `szURL` buforu.  
  
 `pcchUrl`  
 określoną Wskaźnik do zmiennej, która otrzymuje rozmiar adresu URL, łącznie z zakończeniem o wartości null.  
  
 `szUrl`  
 określoną Bufor zawierający adres URL.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie kod błędu.  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedDocument — Interfejs](isymunmanageddocument-interface.md)
