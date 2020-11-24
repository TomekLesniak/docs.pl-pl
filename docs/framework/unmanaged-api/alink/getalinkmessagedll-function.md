---
title: GetALinkMessageDll — Funkcja
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 554bd32ae965b21a88a09577749bbd7975f5ec7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684749"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll — Funkcja

Umożliwia znalezienie i załadowanie biblioteki DLL komunikatów. Zwraca wartość 0, jeśli nie można odnaleźć lub załadować biblioteki DLL komunikatu. Biblioteka DLL komunikatów powinna znajdować się w podkatalogu, którego nazwa jest IDENTYFIKATORem języka lub w bieżącym katalogu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** Alink. h  
  
 **Biblioteka**: alink.dll  
  
## <a name="see-also"></a>Zobacz także

- [Al.exe (Konsolidator zestawu)](../../tools/al-exe-assembly-linker.md)
