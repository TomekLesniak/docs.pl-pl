---
title: IAssemblyCacheItem — Interfejs
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719947"
---
# <a name="iassemblycacheitem-interface"></a>IAssemblyCacheItem — Interfejs

Reprezentuje pojedynczy zestaw w globalnej pamięci podręcznej zestawów.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[AbortItem, metoda](iassemblycacheitem-abortitem-method.md)|Zezwala na zestaw w globalnej pamięci podręcznej zestawów na wykonywanie operacji czyszczenia przed jego wydaniem.|  
|[Commit — metoda](iassemblycacheitem-commit-method.md)|Zatwierdza odwołanie do pamięci podręcznej.|  
|[CreateStream, metoda](iassemblycacheitem-createstream-method.md)|Tworzy strumień o określonej nazwie i formacie.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy łączenia](fusion-interfaces.md)
- [Global Assembly Cache](../../app-domains/gac.md)
- [IAssemblyCache — Interfejs](iassemblycache-interface.md)
