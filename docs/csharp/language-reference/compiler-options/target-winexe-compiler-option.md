---
description: '-target: winexe (opcje kompilatora C#)'
title: '-target: winexe (opcje kompilatora C#)'
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 8a1be07455b54b375106fef1fb480d7abd2f1ca4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124724"
---
# <a name="-targetwinexe-c-compiler-options"></a>-target: winexe (opcje kompilatora C#)
Opcja **-target: winexe** powoduje, że kompilator tworzy plik wykonywalny (exe), program systemu Windows.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a>Uwagi  
 Plik wykonywalny zostanie utworzony z rozszerzeniem. exe. Program systemu Windows to taki, który udostępnia interfejs użytkownika z biblioteki .NET Framework lub interfejsów API systemu Windows.  
  
 Użyj [-target: exe](./target-exe-compiler-option.md) , aby utworzyć aplikację konsolową.  
  
 O ile nie określono inaczej z opcją [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pliku wejściowego, który zawiera metodę [Main](../../programming-guide/main-and-command-args/index.md) .  
  
 Gdy jest określony w wierszu polecenia, wszystkie pliki do momentu użycia **opcji Dalej lub** [-Target](./target-compiler-option.md) są używane do tworzenia programu systemu Windows.  
  
 Jedna i tylko jedna metoda **Main** jest wymagana w plikach kodu źródłowego, które są kompilowane w pliku. exe. Opcja [-Main](./main-compiler-option.md) pozwala określić, która Klasa zawiera metodę **Main** , w przypadkach, gdy kod zawiera więcej niż jedną klasę przy użyciu metody **Main** .  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **aplikacji** .  
  
3. Zmodyfikuj właściwość **typu danych wyjściowych** .  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .  
  
## <a name="example"></a>Przykład  
 Kompiluj `in.cs` do programu Windows:  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [-Target (opcje kompilatora C#)](./target-compiler-option.md)
- [Opcje kompilatora C#](./index.md)
