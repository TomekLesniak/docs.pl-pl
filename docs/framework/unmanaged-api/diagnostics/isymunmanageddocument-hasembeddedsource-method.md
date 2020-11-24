---
title: ISymUnmanagedDocument::HasEmbeddedSource — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 09bc0f87cd35f12a15566fb525c2ce42990ac69b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688201"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a>ISymUnmanagedDocument::HasEmbeddedSource — Metoda

Zwraca `true` czy dokument ma osadzone źródło w symbolach debugowania; w przeciwnym razie zwraca `false` .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a>Parametry  

 `pRetVal`  
 określoną Wskaźnik do zmiennej, która wskazuje, czy dokument ma osadzone źródło w symbolach debugowania.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedDocument — Interfejs](isymunmanageddocument-interface.md)
