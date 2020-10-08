---
title: Wfc.exe (Narzędzie kompilatora wiersza polecenia dla przepływu pracy)
description: Informacje o wfc.exe, narzędziu kompilatora wiersza polecenia przepływu pracy.
ms.date: 10/10/2020
helpviewer_keywords:
- wfc [Workflow]
- compiler tool
- wfc.exe
- Workflow, compilation
- Workflow, XOML files
- Workflow, wcf
ms.openlocfilehash: cf89962014584adf098118044b063b38b29160b7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844604"
---
# <a name="wfcexe-workflow-command-line-compiler-tool"></a>wfc.exe (Narzędzie kompilatora wiersza polecenia dla przepływu pracy)
> [!NOTE]
> W tym materiale omówiono przestarzałe typy i przestrzenie nazw.

Narzędzie kompilatora wiersza polecenia wfc.exe Workflow działa ze starymi plikami znaczników przepływu pracy, które mają rozszerzenie pliku *xoml* (przestarzałe).

## <a name="compilation-process"></a>Proces kompilacji

Podczas kompilowania przepływów pracy następujące procedury są wykonywane w ramach procesu kompilacji:

- Sprawdzanie poprawności jest wykonywane w celu upewnienia się, że działania przepływu pracy są sprawdzane na podstawie zasad ustawionych dla siebie. Jeśli występują błędy walidacji, kompilator zwraca listę błędów.  
- Klasa częściowa jest generowana z definicji oznakowania, która jest wejściowa do kompilatora.  

- Kod jest generowany, aby pomóc w wykonywaniu działań w czasie wykonywania. Generowane są subskrypcje zdarzeń, które ułatwiają działania, gdy działania, które zawierają, są gotowe do wykonania.  
- Klasy częściowe wygenerowane na podstawie pliku znaczników i częściowych klas z pliku kodu są wprowadzane do kompilatora .NET Framework C# lub Visual Basic. Wyjściem tego procesu jest zestaw .NET, WorkflowSample.dll. Można to wdrożyć, aby uruchomić przepływ pracy.

### <a name="compiler-options"></a>Opcje kompilatora

W tej sekcji przedstawiono opcje kompilatora wiersza polecenia wfc.exe Workflow.

```output
    Microsoft (R) Windows Workflow Compiler version 3.0.0.0
    Copyright (C) Microsoft Corporation 2005. All rights reserved.

                      Windows Workflow Compiler Options

    wfc.exe <Xoml file list> /target:assembly [<vb/cs file list>] [/language:...]
            [/out:...] [/reference:...] [/library:...] [/debug...] [/nocode...]
             [/checktypes...] [/resource:<resource info>]

                            - OUTPUT FILE -
    /out:<file>             Output file name
    /target:assembly        Build a Windows Workflow assembly (default).
                            Short form: /t:assembly
    /target:exe             Build a Windows Workflow application.
                            Short form: /t:exe
    /delaysign[+|-]         Delay-sign the assembly using only the public portion
                            of the strong name key.
    /keyfile:<file>         Specifies a strong name key file.
    /keycontainer:<string>  Specifies a strong name key container.

                            - INPUT FILES -
    <Xoml file list>        Xoml source file name(s).
    <vb/cs file list>       Code-beside file name(s).
    /reference:<file list>  Reference metadata from the specified assembly file(s).
                            Short form is '/r:'.
    /library:<path list>    Set of directories where to lookup for the references.
                            Short form is '/lib:'.
    /resource:<resinfo>     Embed the specified resource. Short form is '/res:'.
                            resinfo format is <file>[,<name>[,public|private]].

    Rules and freeform layout files must be embedded as assembly resources.
    The resource name is constructed by using the namespace and type name
    of the activity. For example, an activity named "MyActivity" in namespace
    "WFProject" would require resource names "WFProject.MyActivity.rules"
    and/or "WFProject.MyActivity.layout".

                            - CODE GENERATION -
    /debug[+|-]             Emit full debugging information. The default is '+'.
    /nocode[+|-]            Disallow code-beside model.
                            The default is '-'. Short form is '/nc:'.
    /checktypes[+|-]        Check for permitted types in wfc.exe.config file.
                            The default is '-'. Short form is '/ct:'.

                            - LANGUAGE -
    /language:[cs|vb]       The language to use for the generated class.
                            The default is 'CS' (C#). Short form is '/l:'.
    /rootnamespace:<string> Specifies the root Namespace for all type declarations.
                            Valid only for 'VB' (Visual Basic) language.
                            Short form is '/rns:'.

                            - MISCELLANEOUS -
    /help                   Display this usage message. Short form is '/?'.
    /nologo                 Suppress compiler copyright message. Short form is '/n'.

    /nowarn                 Ignore compiler warnings. Short form is '/w'.
```

## <a name="remarks"></a>Uwagi
> [!NOTE]
> W tym materiale omówiono przestarzałe typy i przestrzenie nazw.

Lista autoryzowanych typów jest zwykle zdefiniowana w pliku *wfc.exe.config* . W fazie walidacji kompilacji przepływu pracy dokument źródłowy przepływu pracy jest odrzucany, jeśli lub plik reguł pomocnika bezpośrednio odwołuje się do wszystkich typów .NET Framework nieobecnych na liście autoryzowanych typów. Lista autoryzowanych typów jest dokumentem XML, gdzie każdy wpis wskazuje, a, a `Assembly` `Namespace` `TypeName` i autoryzowany `True` wskaźnik {&#124;`False` }. `AuthorizedType` odnosi się do wpisu na liście. Oznaczenia symboli wieloznacznych, które mogą służyć do dołączania lub wykluczania kompletnych przestrzeni nazw, są dozwolone. Na przykład `Type="System.*"` zawiera wszystkie typy w <xref:System> , w tym typy zawarte w podrzędnych przestrzeniach nazw.
  
Użycie listy autoryzowanych typów jest kontrolowane przez <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> opcję `'/checktypes'` .

```xml  
<configuration>  
  <System.Workflow.ComponentModel.WorkflowCompiler>
    <authorizedTypes>
      <targetFx version="v4.0">
        ...
        <authorizedType Assembly="System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True"/>
        ...
      </targetFx>
    </authorizedTypes>
  </System.Workflow.ComponentModel.WorkflowCompiler>  
</configuration>  
```

> [!WARNING]
> Gdy `Type="System.*"` Typ jest obecny, można dołączyć do kompilacji inne niezamierzone typy, takie jak `Type="System.Configuration"` . Należy zachować ostrożność i zapoznać się z każdym z nich. Dla dowolnego typu, który powinien być ograniczony, należy ustawić wartość `Authorized` `False` .

## <a name="see-also"></a>Zobacz też

- [Autoryzowanetype — Klasa](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)
