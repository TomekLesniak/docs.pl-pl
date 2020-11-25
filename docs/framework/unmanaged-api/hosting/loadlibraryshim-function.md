---
title: LoadLibraryShim — Funkcja
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
ms.openlocfilehash: d5e9ba0023b6516eb6190f32bc65b2b8b6af79f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727565"
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim — Funkcja

Ładuje określoną wersję biblioteki DLL dołączoną do pakietu redystrybucyjnego .NET Framework.  
  
 Ta funkcja jest przestarzała w .NET Framework 4. Zamiast tego użyj metody [ICLRRuntimeInfo:: LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `szDllName`  
 podczas Ciąg zakończony zerem, który reprezentuje nazwę biblioteki DLL, która ma zostać załadowana z biblioteki .NET Framework.  
  
 `szVersion`  
 podczas Ciąg zakończony zerem, który reprezentuje wersję biblioteki DLL, która ma zostać załadowana. Jeśli `szVersion` ma wartość null, wybrana wersja do załadowania to Najnowsza wersja określonej biblioteki DLL, która jest starsza niż wersja 4. Oznacza to, że wszystkie wersje, które są równe lub większe niż wersja 4 są ignorowane `szVersion` , jeśli ma wartość null, a jeśli nie jest zainstalowana wersja niższa niż 4, nie można załadować biblioteki DLL. Ma to na celu zapewnienie, że instalacja .NET Framework 4 nie ma wpływu na istniejące aplikacje lub składniki. Zapoznaj się z wpisem [w procesie SxS i szybki start migracji](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) w blogu zespołu CLR.  
  
 `pvReserved`  
 Zarezerwowane do użytku w przyszłości.  
  
 `phModDll`  
 określoną Wskaźnik do uchwytu modułu.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca kody błędów standardowego Component Object Model (COM), jak zdefiniowano w WinError. h, oprócz następujących wartości.  
  
|Kod powrotu|Opis|  
|-----------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|CLR_E_SHIM_RUNTIMELOAD|Ładowanie `szDllName` wymaga załadowania środowiska uruchomieniowego języka wspólnego (CLR) i niezbędna wersja środowiska CLR nie może zostać załadowana.|  
  
## <a name="remarks"></a>Uwagi  

 Ta funkcja służy do ładowania bibliotek DLL, które znajdują się w pakiecie redystrybucyjnym .NET Framework. Nie ładuje bibliotek DLL generowanych przez użytkownika.  
  
> [!NOTE]
> Począwszy od .NET Framework w wersji 2,0, ładowanie Fusion.dll powoduje, że środowisko CLR zostanie załadowane. Jest to spowodowane tym, że funkcje w Fusion.dll są teraz otokami, których implementacje są udostępniane przez środowisko uruchomieniowe.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
