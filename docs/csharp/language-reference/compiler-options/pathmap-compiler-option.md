---
description: -elemencie pathmap (opcje kompilatora C#)
title: -elemencie pathmap (opcje kompilatora C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 707a37c6946cfcaf429552f0aeece6b87f3ad71d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125010"
---
# <a name="-pathmap-c-compiler-options"></a>-elemencie pathmap (opcje kompilatora C#)

Opcja kompilatora **-elemencie pathmap** określa sposób mapowania ścieżek fizycznych do nazw ścieżek źródłowych wyjściowych przez kompilator.

## <a name="syntax"></a>Składnia

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a>Argumenty

 `path1` Pełna ścieżka do plików źródłowych w bieżącym środowisku

 `sourcePath1` Ścieżka źródłowa zastępują dla `path1` plików wyjściowych.

Aby określić wiele mapowanych ścieżek źródłowych, rozdziel je przecinkami.

## <a name="remarks"></a>Uwagi

Kompilator zapisuje ścieżkę źródłową do danych wyjściowych z następujących powodów:

1. Ścieżka źródłowa jest zastępowana argumentem, gdy <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> jest stosowany do opcjonalnego parametru.
1. Ścieżka źródłowa jest osadzona w pliku PDB.
1. Ścieżka pliku PDB jest osadzona w pliku PE (przenośny plik wykonywalny).

Ta opcja mapuje każdą ścieżkę fizyczną na komputerze, na którym kompilator jest uruchamiany do odpowiedniej ścieżki, która powinna być zapisywana w plikach wyjściowych.

## <a name="example"></a>Przykład

Kompiluj `t.cs` w katalogu **C: \\ Work \\ Tests** i Mapuj ten katalog na **\publish** w danych wyjściowych:

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
