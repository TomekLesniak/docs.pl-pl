---
description: -out (opcje kompilatora C#)
title: -out (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 409760ee0b147065a2128c62c304fb5d70cfcf42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193884"
---
# <a name="-out-c-compiler-options"></a>-out (opcje kompilatora C#)

Opcja **-out** określa nazwę pliku wyjściowego.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argumenty  

 `filename`  
 Nazwa pliku wyjściowego utworzonego przez kompilator.  
  
## <a name="remarks"></a>Uwagi  

 W wierszu polecenia można określić wiele plików wyjściowych dla kompilacji. Kompilator oczekuje na znalezienie co najmniej jednego pliku kodu źródłowego po opcji **-out** . Następnie wszystkie pliki kodu źródłowego zostaną skompilowane do pliku wyjściowego określonego **przez tę opcję** .  
  
 Określ pełną nazwę i rozszerzenie pliku, który chcesz utworzyć.  
  
 Jeśli nie określisz nazwy pliku wyjściowego:  
  
- Plik. exe zajmie swoją nazwę z pliku kodu źródłowego, który zawiera metodę **Main** .  
  
- Plik. dll lub. webmodule przyjmuje swoją nazwę z pierwszego pliku kodu źródłowego.  
  
 Plik kodu źródłowego używany do kompilowania jednego pliku wyjściowego nie może być używany w tej samej kompilacji dla kompilacji innego pliku wyjściowego.  
  
 W przypadku tworzenia wielu plików wyjściowych w kompilacji wiersza polecenia należy pamiętać, że tylko jeden z plików wyjściowych może być zestawem i że tylko pierwszy plik wyjściowy określony (niejawnie lub jawnie w **trybie out**) może być zestawem.  
  
 Wszystkie moduły tworzone w ramach kompilacji stają się plikami skojarzonymi z dowolnym zestawem również w kompilacji. Użyj [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) , aby wyświetlić manifest zestawu, aby wyświetlić skojarzone pliki.  
  
 Opcja kompilatora-out jest wymagana, aby plik exe był elementem docelowym zestawu zaprzyjaźnionego. Aby uzyskać więcej informacji, zobacz [zaprzyjaźnione zestawy](../../../standard/assembly/friend.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **aplikacji** .  
  
3. Zmodyfikuj właściwość **nazwy zestawu** .  
  
     Aby programowo ustawić tę opcję kompilatora: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> jest to właściwość tylko do odczytu, która jest określana przez kombinację typu projektu (exe, biblioteka i tak dalej) i nazwę zestawu. Modyfikacja jednej lub obu tych właściwości będzie konieczna do ustawienia nazwy pliku wyjściowego.  
  
## <a name="example"></a>Przykład  

 Kompiluj `t.cs` i twórz plik wyjściowy `t.exe` , a także Kompiluj `t2.cs` i twórz plik wyjściowy modułu `mymodule.netmodule` :  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zaprzyjaźnione zestawy](../../../standard/assembly/friend.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
