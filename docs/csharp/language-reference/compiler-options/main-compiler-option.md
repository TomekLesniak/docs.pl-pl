---
description: -Main (opcje kompilatora C#)
title: -Main (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: c27898de2a7cc2f3c01c51f8de1122e81b2233b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194118"
---
# <a name="-main-c-compiler-options"></a>-Main (opcje kompilatora C#)

Ta opcja określa klasę, która zawiera punkt wejścia do programu, jeśli więcej niż jedna Klasa zawiera metodę **Main** .

## <a name="syntax"></a>Składnia

```console
-main:class
```

## <a name="arguments"></a>Argumenty

 `class`  
 Typ, który zawiera metodę **Main** .  
 Podana nazwa klasy musi być w pełni kwalifikowana; musi zawierać pełną przestrzeń nazw zawierającą klasę, a po niej nazwę klasy. Na przykład, gdy metoda znajduje się `Main` wewnątrz `Program` klasy w `MyApplication.Core` przestrzeni nazw, opcja kompilatora musi mieć wartość `-main:MyApplication.Core.Program` .

## <a name="remarks"></a>Uwagi

Jeśli kompilacja zawiera więcej niż jeden typ z metodą [Main](../../programming-guide/main-and-command-args/index.md) , można określić, który typ zawiera metodę **Main** , która ma być używana jako punkt wejścia do programu.

Ta opcja jest używana podczas kompilowania pliku *. exe* .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz stronę **Właściwości** projektu.

2. Kliknij stronę właściwości **aplikacji** .

3. Zmodyfikuj właściwość **obiektu uruchomieniowego** .

    Aby programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.StartupObject%2A> .

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a>Aby ustawić tę opcję kompilatora, ręcznie edytując plik *. csproj*

Tę opcję można ustawić, edytując plik. csproj i dodając element `StartupObject` w `PropertyGroup` sekcji. Na przykład:

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a>Przykład

Kompiluj `t2.cs` i `t3.cs` , określając, że metoda **Main** zostanie znaleziona w `Test2` :

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
