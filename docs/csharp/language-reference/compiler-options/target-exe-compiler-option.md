---
description: '-target: exe (opcje kompilatora C#)'
title: '-target: exe (opcje kompilatora C#)'
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: ae1706f1ecdd396e24711070d19420faa6d34761
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193766"
---
# <a name="-targetexe-c-compiler-options"></a>-target: exe (opcje kompilatora C#)

Opcja **-target: exe** powoduje, że kompilator tworzy plik wykonywalny (exe), aplikację konsolową.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a>Uwagi  

 Opcja **-target: exe** domyślnie działa. Plik wykonywalny zostanie utworzony z rozszerzeniem. exe.  
  
 USE [-target: winexe](./target-winexe-compiler-option.md) do utworzenia pliku wykonywalnego programu systemu Windows.  
  
 O ile nie określono inaczej z opcją [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pliku wejściowego, który zawiera metodę [Main](../../programming-guide/main-and-command-args/index.md) .  
  
 W przypadku określenia w wierszu polecenia wszystkie pliki **do następnej lub** **docelowej opcji modułu** są używane do tworzenia pliku. exe  
  
 Jedna i tylko jedna metoda **Main** jest wymagana w plikach kodu źródłowego, które są kompilowane w pliku. exe. [-Main —](./main-compiler-option.md) opcja kompilatora pozwala określić, która Klasa zawiera metodę **Main** , w przypadkach, gdy kod zawiera więcej niż jedną klasę za pomocą metody **Main** .  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **aplikacji** .  
  
3. Zmodyfikuj właściwość **typu danych wyjściowych** .  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .  
  
## <a name="example"></a>Przykład  

 Każdy z następujących wierszy poleceń zostanie skompilowany `in.cs` , tworzenie `in.exe` :  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [-Target (opcje kompilatora C#)](./target-compiler-option.md)
- [Opcje kompilatora C#](./index.md)
