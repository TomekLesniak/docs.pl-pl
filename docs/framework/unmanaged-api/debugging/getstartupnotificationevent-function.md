---
title: GetStartupNotificationEvent — Funkcja
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: 1c6ad35cd42760a4d88cf78bb084a25cf58a1064
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676091"
---
# <a name="getstartupnotificationevent-function"></a>GetStartupNotificationEvent — Funkcja

Tworzy lub otwiera dojście zdarzenia, które będzie sygnalizowane przez środowisko uruchomieniowe języka wspólnego (CLR) ładowane w określonym procesie docelowym.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a>Parametry  

 `debuggeePID`  
 podczas Identyfikator procesu docelowego, z którego mają zostać odebrane powiadomienia uruchomieniowe środowiska CLR.  
  
 `phStartupEvent`  
 określoną Wskaźnik do dojścia, który zostanie zasygnalizowani przez CLR podczas uruchamiania.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK  
 Pomyślnie uzyskano dojście do zdarzenia powiadomienia uruchomienia.  
  
 E_INVALIDARG  
 `phStartupEvent` ma wartość null lub `debuggeePID` nie odwołuje się do procesu, który jest obecnie uruchomiony.  
  
 E_FAIL (lub inne kody powrotne E_)  
 Nie można uzyskać dojścia do zdarzenia powiadomienia uruchomienia.  
  
## <a name="remarks"></a>Uwagi  

 W systemie operacyjnym Windows `debuggeePID` mapuje na identyfikator procesu systemu operacyjnego.  
  
 Zdarzenie jest sygnalizowane przed wykonaniem kodu zarządzanego przez środowisko CLR sygnalizujące zdarzenie.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** dbgshim. h  
  
 **Biblioteka:** dbgshim.dll  
  
 **.NET Framework wersje:** 3,5 SP1
