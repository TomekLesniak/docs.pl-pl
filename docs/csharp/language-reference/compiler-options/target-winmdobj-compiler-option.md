---
description: '-target: winmdobj (opcje kompilatora C#)'
title: '-target: winmdobj (opcje kompilatora C#)'
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: 66a4bddb34832705ad4779829e561afd9442be8f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139089"
---
# <a name="-targetwinmdobj-c-compiler-options"></a>-target: winmdobj (opcje kompilatora C#)
W przypadku użycia opcji kompilatora **-target: winmdobj** kompilator tworzy plik pośredni. winmdobj, który można przekonwertować na środowisko wykonawcze systemu Windows plik binarny (. winmd). Plik. winmd może być następnie używany przez programy JavaScript i C++, a także do programów języka zarządzanego.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a>Uwagi  
 Ustawienie **winmdobj** sygnalizuje kompilatorowi, że wymagany jest moduł pośredni. W odpowiedzi program Visual Studio kompiluje bibliotekę klas C# jako plik. winmdobj. Plik. winmdobj można następnie uzyskać za pomocą <xref:Microsoft.Build.Tasks.WinMDExp> narzędzia eksportu w celu utworzenia pliku metadanych systemu Windows (WinMD). Plik. winmd zawiera zarówno kod z oryginalnej biblioteki, jak i metadane WinMD, które są używane przez skrypty JavaScript lub C++ i środowisko wykonawcze systemu Windows.  
  
 Dane wyjściowe pliku, który jest kompilowany przy użyciu opcji **-target: winmdobj** kompilatora, jest przeznaczony do użycia tylko jako dane wejściowe dla narzędzia eksportu WimMDExp; sam plik. winmdobj nie jest bezpośrednio przywoływany.  
  
 O ile nie zostanie użyta opcja [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pierwszego pliku wejściowego. Metoda [Main](../../programming-guide/main-and-command-args/index.md) nie jest wymagana.  
  
 W przypadku określenia opcji-target: winmdobj w wierszu polecenia wszystkie pliki do momentu, w którym zostanie użyta opcja modułu "Następny **-out** " lub ["target: module"](./target-module-compiler-option.md) , są używane do tworzenia programu systemu Windows.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>Aby ustawić tę opcję kompilatora w programie Visual Studio IDE dla aplikacji magazynu systemu Windows  
  
1. W **Eksplorator rozwiązań**Otwórz menu skrótów dla projektu, a następnie wybierz polecenie **Właściwości**.  
  
2. Wybierz kartę **aplikacja** .  
  
3. Na liście **Typ danych wyjściowych** wybierz pozycję **plik WinMD**.  
  
     Opcja **plik WinMD** jest dostępna tylko dla szablonów aplikacji ze sklepu Windows 8. x.  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .  
  
## <a name="example"></a>Przykład  
 Następujące polecenie kompiluje `filename.cs` do pośredniego pliku. winmdobj.  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [-Target (opcje kompilatora C#)](./target-compiler-option.md)
- [Opcje kompilatora C#](./index.md)
