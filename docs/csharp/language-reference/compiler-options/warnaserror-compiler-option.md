---
description: -warnaserror — (opcje kompilatora C#)
title: -warnaserror — (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: 3ccd4546402dbc8e5d9245af6411ba2d831d4959
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127246"
---
# <a name="-warnaserror-c-compiler-options"></a>-warnaserror — (opcje kompilatora C#)
Opcja **-warnaserror — +** traktuje wszystkie ostrzeżenia jako błędy  
  
## <a name="syntax"></a>Składnia  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a>Uwagi  
 Wszystkie komunikaty, które zwykle są raportowane jako ostrzeżenia, są raportowane jako błędy, a proces kompilacji jest zatrzymany (nie skompilowano plików wyjściowych).  
  
 Domyślnie **— warnaserror — —** obowiązuje, co powoduje, że ostrzeżenia nie uniemożliwiają generowania pliku wyjściowego. **-warnaserror —**, która jest taka sama jak **-warnaserror — +**, powoduje, że ostrzeżenia są traktowane jako błędy.  
  
 Opcjonalnie, jeśli chcesz, aby tylko kilka określonych ostrzeżeń było traktowane jako błędy, możesz określić rozdzieloną przecinkami listę numerów ostrzeżeń, które będą traktowane jako błędy. Zestaw wszystkich ostrzeżeń o wartości null można określić za pomocą skrótu **dopuszczający wartość** null.
  
 Użyj [-warn](./warn-compiler-option.md) , aby określić poziom ostrzeżeń, które mają być wyświetlane w kompilatorze. Użyj [-nowarn](./nowarn-compiler-option.md) , aby wyłączyć niektóre ostrzeżenia.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **kompilacja** .  
  
3. Zmodyfikuj właściwość **Traktuj ostrzeżenia jako błędy** .  
  
 Aby programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors> .  
  
## <a name="example"></a>Przykład  
 Kompiluj `in.cs` i czy kompilator nie wyświetli żadnych ostrzeżeń:  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652,nullable in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
