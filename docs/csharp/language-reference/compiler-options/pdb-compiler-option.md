---
description: -PDB (opcje kompilatora C#)
title: -PDB (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: ced1ee1f4f079830a032a628da96a389ba27da90
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193858"
---
# <a name="-pdb-c-compiler-options"></a>-PDB (opcje kompilatora C#)

**-PDB —** opcja kompilatora określa nazwę i lokalizację pliku symboli debugowania.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a>Argumenty  

 `filename`  
 Nazwa i lokalizacja pliku symboli debugowania.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli określisz polecenie [-debug (opcje kompilatora C#)](./debug-compiler-option.md), kompilator utworzy plik. pdb w tym samym katalogu, w którym kompilator utworzy plik wyjściowy (. exe lub. dll) z nazwą pliku, która jest taka sama jak nazwa pliku wyjściowego.  
  
 **-PDB** umożliwia określenie niedomyślnej nazwy pliku i lokalizacji dla pliku. pdb.  
  
 Nie można ustawić tej opcji kompilatora w środowisku deweloperskim programu Visual Studio, ani programowo zmienić.  
  
## <a name="example"></a>Przykład  

 Kompiluj `t.cs` i Utwórz plik. pdb o nazwie TT. pdb:  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
