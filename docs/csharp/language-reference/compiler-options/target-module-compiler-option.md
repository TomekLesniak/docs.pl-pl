---
description: '-target: module (opcje kompilatora C#)'
title: '-target: module (opcje kompilatora C#)'
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 2c592d2fe001bb0908a06a6eb3287a39040b8715
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128455"
---
# <a name="-targetmodule-c-compiler-options"></a>-target: module (opcje kompilatora C#)
Ta opcja powoduje, że kompilator nie generuje manifestu zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a>Uwagi  
 Domyślnie plik wyjściowy utworzony przez kompilację z tą opcją będzie miał rozszerzenie.  
  
 Nie można załadować pliku, który nie zawiera manifestu zestawu, za pomocą środowiska uruchomieniowego języka wspólnego .NET Framework. Jednak taki plik można włączyć do manifestu zestawu zestawu za pomocą [-addmodule](./addmodule-compiler-option.md).  
  
 W przypadku utworzenia więcej niż jednego modułu w pojedynczej kompilacji typy [wewnętrzne](../keywords/internal.md) w jednym module będą dostępne dla innych modułów w kompilacji. Gdy kod w jednym module odwołuje się do `internal` typów w innym module, oba moduły muszą być dołączone do manifestu zestawu, za pomocą **-addmodule**.  
  
 Tworzenie modułu nie jest obsługiwane w środowisku deweloperskim programu Visual Studio.  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .  
  
## <a name="example"></a>Przykład  
 Kompiluj `in.cs` , Utwórz `in.netmodule` :  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [-Target (opcje kompilatora C#)](./target-compiler-option.md)
- [Opcje kompilatora C#](./index.md)
