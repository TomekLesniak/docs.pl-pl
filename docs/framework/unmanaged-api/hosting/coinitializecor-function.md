---
title: CoInitializeCor — Funkcja
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: 9d077d5c5a414568b5643cad0171e101d7bb06f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731712"
---
# <a name="coinitializecor-function"></a>CoInitializeCor — Funkcja

`CoInitializeCor` jest przestarzały.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>Uwagi  

 Aby zainicjować środowisko uruchomieniowe języka wspólnego, użyj opcji [CorBindToRuntimeEx](corbindtoruntimeex-function.md) lub [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** Cor. h  
  
## <a name="see-also"></a>Zobacz także

- [Statyczne funkcje globalne metadanych](../metadata/metadata-global-static-functions.md)
