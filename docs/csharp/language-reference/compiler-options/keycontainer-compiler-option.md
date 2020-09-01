---
description: -containerer (opcje kompilatora C#)
title: -containerer (opcje kompilatora C#)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: 8b11380683159b7792149558a5dd432707ba3818
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125504"
---
# <a name="-keycontainer-c-compiler-options"></a>-containerer (opcje kompilatora C#)
Określa nazwę kontenera klucza kryptograficznego.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a>Argumenty  
 `string`  
 Nazwa kontenera klucza o silnej nazwie.  
  
## <a name="remarks"></a>Uwagi  
 Gdy jest używana opcja **-containerer** , kompilator tworzy składnik udostępniony. Kompilator wstawia klucz publiczny z określonego kontenera do manifestu zestawu i podpisuje końcowy zestaw z kluczem prywatnym. Aby wygenerować plik klucza, wpisz `sn -k file` w wierszu polecenia. `sn -i` instaluje parę kluczy w kontenerze. Ta opcja nie jest obsługiwana, gdy kompilator działa w CoreCLR. Aby podpisać zestaw podczas kompilowania na CoreCLR, użyj opcji [-KeyFile](keyfile-compiler-option.md) .
  
 W przypadku kompilowania z [modułem-target:](./target-module-compiler-option.md)nazwa pliku klucza jest przechowywana w module i wbudowana w zestaw podczas kompilowania tego modułu do zestawu za pomocą [-addmodule](./addmodule-compiler-option.md).  
  
 Można również określić tę opcję jako atrybut niestandardowy ( <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType> ) w kodzie źródłowym dla dowolnego modułu języka pośredniego (MSIL) firmy Microsoft.  
  
 Możesz również przekazać informacje o szyfrowaniu do kompilatora za pomocą [-KeyFile](./keyfile-compiler-option.md). Użyj [-delaysign](./delaysign-compiler-option.md) , jeśli chcesz, aby klucz publiczny został dodany do manifestu zestawu, ale chcesz opóźnić podpisywanie zestawu do momentu przetestowania.  
  
 Aby uzyskać więcej informacji, zobacz [Tworzenie i używanie zestawów o silnych nazwach](../../../standard/assembly/create-use-strong-named.md) oraz [opóźnienie podpisywania zestawu](../../../standard/assembly/delay-sign.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Ta opcja kompilatora nie jest dostępna w środowisku deweloperskim programu Visual Studio.  
  
 Można programowo uzyskać dostęp do tej opcji kompilatora przy użyciu <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> .  
  
## <a name="see-also"></a>Zobacz też

- [Kompilator języka C# — opcja keyfile](keyfile-compiler-option.md)
- [Opcje kompilatora C#](index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
