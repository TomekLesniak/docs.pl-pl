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
ms.openlocfilehash: 9e84ff95f7f0addac1c2c2d79af0ab53572da27f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193806"
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
