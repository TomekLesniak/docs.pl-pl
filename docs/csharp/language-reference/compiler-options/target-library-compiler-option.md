---
description: '-target: Library (opcje kompilatora C#)'
title: '-target: Library (opcje kompilatora C#)'
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 0f5b1e1bec8fd601bf111e1c2c64adf22d0a064e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193728"
---
# <a name="-targetlibrary-c-compiler-options"></a>-target: Library (opcje kompilatora C#)

Opcja **-target: Library** powoduje, że kompilator tworzy bibliotekę dołączaną dynamicznie (dll), a nie plik wykonywalny (exe).  
  
## <a name="syntax"></a>Składnia  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a>Uwagi  

 Biblioteka DLL zostanie utworzona z rozszerzeniem dll.  
  
 O ile nie określono inaczej z opcją [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pierwszego pliku wejściowego.  
  
 W przypadku określenia w wierszu polecenia wszystkie pliki **do następnej lub** **docelowej opcji modułu** są używane do tworzenia pliku dll.  
  
 Podczas kompilowania pliku DLL Metoda [Main](../../programming-guide/main-and-command-args/index.md) nie jest wymagana.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **aplikacji** .  
  
3. Zmodyfikuj właściwość **typu danych wyjściowych** .  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .  
  
## <a name="example"></a>Przykład  

 Kompiluj `in.cs` , Utwórz `in.dll` :  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [-Target (opcje kompilatora C#)](./target-compiler-option.md)
- [Opcje kompilatora C#](./index.md)
