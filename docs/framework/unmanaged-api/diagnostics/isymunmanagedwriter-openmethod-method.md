---
title: ISymUnmanagedWriter::OpenMethod — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: deb3a28ffb73754b4c03496a6a72325418f1a4fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722911"
---
# <a name="isymunmanagedwriteropenmethod-method"></a>ISymUnmanagedWriter::OpenMethod — Metoda

Otwiera metodę, do której są emitowane informacje o symbolach. Dana metoda jest bieżącą metodą dla wywołań definiujących punkty sekwencji, parametry i zakresy leksykalne. Istnieje niejawny zakres leksykalny wokół całej metody. Ponowne otwarcie wcześniej zamkniętej metody powoduje wymazanie wszystkich wcześniej zdefiniowanych symboli dla tej metody. W danym momencie może istnieć tylko jedna metoda Open.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a>Parametry  

 `method`  
 podczas Token metadanych dla metody, która ma zostać otwarta.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Zobacz także

- [ISymUnmanagedWriter — Interfejs](isymunmanagedwriter-interface.md)
- [CloseMethod, metoda](isymunmanagedwriter-closemethod-method.md)
- [OpenMethod2, metoda](isymunmanagedwriter3-openmethod2-method.md)
