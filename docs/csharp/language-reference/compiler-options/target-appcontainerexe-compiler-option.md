---
description: '-target: appcontainerexe (opcje kompilatora C#)'
title: '-target: appcontainerexe (opcje kompilatora C#)'
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: e4aa60ebc9dcc1a63b63863385b0ee9f13d6d78d
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193741"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a>-target: appcontainerexe (opcje kompilatora C#)

W przypadku użycia opcji kompilatora **-target: appcontainerexe** kompilator tworzy plik wykonywalny systemu Windows (exe), który musi być uruchamiany w kontenerze aplikacji. Ta opcja jest równoznaczna z parametrem [-target: winexe](./target-winexe-compiler-option.md) , ale jest przeznaczona dla aplikacji ze sklepu Windows 8. x.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a>Uwagi  

 Aby wymagać uruchamiania aplikacji w kontenerze aplikacji, ta opcja ustawia bit w [przenośnym pliku wykonywalnym](/windows/desktop/Debug/pe-format) (PE). Gdy ten bit jest ustawiony, występuje błąd, jeśli metoda CreateProcess podejmie próbę uruchomienia pliku wykonywalnego poza kontenerem aplikacji.  
  
 O ile nie zostanie użyta opcja [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pliku wejściowego, który zawiera metodę [Main](../../programming-guide/main-and-command-args/index.md) .  
  
 Po określeniu tej opcji w wierszu polecenia wszystkie pliki do momentu użycia opcji **Dalej lub** **-Target** są używane do tworzenia pliku wykonywalnego.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>Aby ustawić tę opcję kompilatora w IDE  
  
1. W **Eksplorator rozwiązań** Otwórz menu skrótów dla projektu, a następnie wybierz polecenie **Właściwości**.  
  
2. Na karcie **aplikacja** na liście **Typ danych wyjściowych** wybierz pozycję **aplikacja ze sklepu Windows**.  
  
     Ta opcja jest dostępna tylko dla szablonów aplikacji ze sklepu Windows 8. x.  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .  
  
## <a name="example"></a>Przykład  

 Następujące polecenie kompiluje `filename.cs` do pliku wykonywalnego systemu Windows, który można uruchomić tylko w kontenerze aplikacji.  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [-Target (opcje kompilatora C#)](./target-compiler-option.md)
- [-target: winexe (opcje kompilatora C#)](./target-winexe-compiler-option.md)
- [Opcje kompilatora C#](./index.md)
