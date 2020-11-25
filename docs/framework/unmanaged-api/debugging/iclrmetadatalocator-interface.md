---
title: ICLRMetadataLocator — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: 69c52c13a4a0aca5094274de969ebed6e09651b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723509"
---
# <a name="iclrmetadatalocator-interface"></a>ICLRMetadataLocator — Interfejs

Używany przez warstwę usług dostępu do danych do lokalizowania metadanych zestawów w procesie docelowym.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetMetadata — Metoda](iclrmetadatalocator-getmetadata-method.md)|Pobiera metadane obrazu z procesu docelowego.|  
  
## <a name="remarks"></a>Uwagi  

 Klient API (tzn. debuger) musi implementować ten interfejs stosownie do określonego procesu docelowego. Na przykład implementacja procesu na żywo byłaby inna niż w przypadku zrzutu pamięci.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData. idl, ClrData. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
