---
title: CoUninitializeCor — Funkcja
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: 7d39c6fda6f159bfc937f62dc45d0d7ce37657f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687884"
---
# <a name="couninitializecor-function"></a>CoUninitializeCor — Funkcja

`CoUninitializeCor` jest przestarzały.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a>Uwagi  

 Nie można zwolnić środowiska uruchomieniowego języka wspólnego z procesu. Aby całkowicie usunąć środowisko uruchomieniowe z działającego procesu, należy zamknąć ten proces.  
  
## <a name="see-also"></a>Zobacz także

- [Statyczne funkcje globalne metadanych](../metadata/metadata-global-static-functions.md)
