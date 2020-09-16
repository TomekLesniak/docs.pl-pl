---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ecaff179378eb417393c0a0d17d0a00d3b99e5a4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541301"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>ICorProfilerInfo9:: GetCodeInfo4, Metoda

Przy podanym adresie początkowym kodu natywnego program zwraca bloki pamięci wirtualnej, która przechowuje ten kod.

## <a name="syntax"></a>Składnia

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a>Parametry

- `pNativeCodeStartAddress`

  \[w] wskaźnik do początku funkcji natywnej.

- `cCodeInfos`

  \[w] rozmiar `codeInfos` tablicy.

- `pcCodeInfos`

  \[out] wskaźnik do łącznej liczby dostępnych struktur [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .

- `codeInfos`

  \[out] bufor dostarczony przez wywołującego. Po powrocie metody zawiera tablicę `COR_PRF_CODE_INFO` struktur, z których każdy opisuje blok kodu natywnego.

## <a name="remarks"></a>Uwagi

`GetCodeInfo4`Metoda jest podobna do [GetCodeInfo3 —](icorprofilerinfo4-getcodeinfo3-method.md), z tą różnicą, że może wyszukiwać informacje o kodzie dla różnych natywnych wersji metody.

> [!NOTE]
> `GetCodeInfo4` może wyzwolić wyrzucanie elementów bezużytecznych.

Zakresy są sortowane w kolejności rosnącego, typowego przesunięcia języka pośredniego (CIL).

Po `GetCodeInfo4` powrocie należy sprawdzić, czy `codeInfos` bufor jest wystarczająco duży, aby zawierał wszystkie struktury [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) . W tym celu należy porównać wartość `cCodeInfos` z wartością `cchName` parametru. Jeśli `cCodeInfos` podzielona przez rozmiar struktury [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) jest mniejsza niż `pcCodeInfos` , Przydziel większy `codeInfos` bufor, zaktualizuj `cCodeInfos` przy użyciu nowego, większego rozmiaru i ponownie wywołaj `GetCodeInfo4` .

Alternatywnie, można najpierw wywołać `GetCodeInfo4` z buforem o zerowej długości, `codeInfos` Aby uzyskać prawidłowy rozmiar buforu. Następnie można ustawić `codeInfos` rozmiar buforu na wartość zwróconą w `pcCodeInfos` , pomnożoną przez rozmiar struktury [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) i `GetCodeInfo4` ponownie wywołać.

## <a name="requirements"></a>Wymagania

**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).

**Nagłówek:** CorProf. idl, CorProf. h

**Biblioteka:** CorGuids. lib

**Wersje .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo9, interfejs](ICorProfilerInfo9-interface.md)
