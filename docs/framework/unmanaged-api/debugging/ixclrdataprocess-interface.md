---
title: IXCLRDataProcess, interfejs
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 376ec2b840bc17c79ed1f27c17a8ddd22c37a0f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245357"
---
# <a name="ixclrdataprocess-interface"></a>IXCLRDataProcess, interfejs

Dostarcza metody do wykonywania zapytań dotyczących informacji o procesie.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Metody

| Metoda                                                                                                                                               | Opis                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetRuntimeNameByAddress](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | Pobiera nazwę dla danego adresu.                                                               |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Pobiera `AppDomain` w procesie według jego unikatowego identyfikatora.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Udostępnia dojście do wyliczenia modułów procesu.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Wylicza moduły tego procesu.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Zwalnia zasoby używane przez Iteratory wewnętrzne używane podczas wyliczania modułu.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Udostępnia dojście do wyliczenia wystąpień metod, `AppDomain` Zaczynając od danego adresu. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Wylicza wystąpienia metody tego procesu, rozpoczynając od przesunięcia adresu.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Zwalnia zasoby używane przez Iteratory wewnętrzne używane podczas wyliczania wystąpień.             |

## <a name="remarks"></a>Uwagi

Ten interfejs jest wewnątrz środowiska uruchomieniowego i nie jest udostępniany przez żadne nagłówki lub pliki bibliotek. Jest to jednak interfejs COM pochodzący z `IUnknown` identyfikatora GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , który można uzyskać za pomocą zwykłych mechanizmów com.

## <a name="requirements"></a>Wymagania

**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).
**Nagłówek:** Dawaj  
**Biblioteka:** Dawaj  
**.NET Framework wersje:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Zobacz też

- [Debugowanie](index.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
