---
title: IAssemblyName::IsEqual — Metoda
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
ms.openlocfilehash: 0fabf8159c2626d4e1716e3be60baaf1ec834032
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712992"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual — Metoda

Określa, czy określony obiekt [IAssemblyName](iassemblyname-interface.md) jest równy temu `IAssemblyName` , na podstawie określonych flag porównania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pName`  
 podczas `IAssemblyName` Obiekt, do którego ma zostać wykonane porównanie `IAssemblyName` .  
  
 `dwCmpFlags`  
 podczas Bitowa kombinacja [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) wartości, które mają wpływ na porównanie.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **Wersje programu .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IAssemblyName — Interfejs](iassemblyname-interface.md)
- [Wyliczenia łączenia](fusion-enumerations.md)
