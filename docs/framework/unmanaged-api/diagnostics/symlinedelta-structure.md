---
title: SYMLINEDELTA — Struktura
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690944"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA — Struktura

Zawiera informacje do obsługi symboli dotyczące metod, które zostały przeniesione w wyniku edycji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`mdMethod`|Token metadanych metody.|  
|`delta`|Liczba wierszy, które zostały przeniesione przez metodę.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** CorSym. idl  
  
## <a name="see-also"></a>Zobacz także

- [Struktury magazynu symboli diagnostycznych](diagnostics-symbol-store-structures.md)
