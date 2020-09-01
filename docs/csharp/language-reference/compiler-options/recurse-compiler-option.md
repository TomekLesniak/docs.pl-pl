---
description: -rekursywnie (opcje kompilatora C#)
title: -rekursywnie (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 3edd7e23358bc0569dae6204d519209df1ade290
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124828"
---
# <a name="-recurse-c-compiler-options"></a>-rekursywnie (opcje kompilatora C#)
Opcja-rekursywnie umożliwia skompilowanie plików kodu źródłowego we wszystkich katalogach podrzędnych określonego katalogu (dir) lub katalogu projektu.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumenty  
 `dir` (opcjonalnie)  
 Katalog, w którym ma zostać rozpoczęte wyszukiwanie. Jeśli ta wartość nie jest określona, wyszukiwanie rozpoczyna się w katalogu projektu.  
  
 `file`  
 Pliki do wyszukania. Symbole wieloznaczne są dozwolone.  
  
## <a name="remarks"></a>Uwagi  
 Opcja **-rekursywnie** umożliwia skompilowanie plików kodu źródłowego we wszystkich katalogach podrzędnych określonego katalogu ( `dir` ) lub katalogu projektu.  
  
 W nazwie pliku można użyć symboli wieloznacznych, aby skompilować wszystkie zgodne pliki w katalogu projektu bez użycia opcji **-rekursywnie**.  
  
 Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.  
  
## <a name="example"></a>Przykład  
 Kompiluje wszystkie pliki C# w bieżącym katalogu:  
  
```console  
csc *.cs  
```  
  
 Kompiluje wszystkie pliki C# w katalogu dir1\dir2 i wszystkie znajdujące się w nim katalogi i generuje dir2.dll:  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
