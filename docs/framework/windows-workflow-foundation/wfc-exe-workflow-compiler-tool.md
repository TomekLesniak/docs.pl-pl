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
# <a name="wfcexe-workflow-command-line-compiler-tool"></a><span data-ttu-id="b2a2c-103">wfc.exe (Narzędzie kompilatora wiersza polecenia dla przepływu pracy)</span><span class="sxs-lookup"><span data-stu-id="b2a2c-103">wfc.exe (Workflow Command-line Compiler Tool)</span></span>
> [!NOTE]
> <span data-ttu-id="b2a2c-104">W tym materiale omówiono przestarzałe typy i przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-104">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="b2a2c-105">Narzędzie kompilatora wiersza polecenia wfc.exe Workflow działa ze starymi plikami znaczników przepływu pracy, które mają rozszerzenie pliku *xoml* (przestarzałe).</span><span class="sxs-lookup"><span data-stu-id="b2a2c-105">The wfc.exe workflow command-line compiler tool works with old workflow markup files that have the file extension *.xoml* (obsoleted).</span></span>

## <a name="compilation-process"></a><span data-ttu-id="b2a2c-106">Proces kompilacji</span><span class="sxs-lookup"><span data-stu-id="b2a2c-106">Compilation process</span></span>

<span data-ttu-id="b2a2c-107">Podczas kompilowania przepływów pracy następujące procedury są wykonywane w ramach procesu kompilacji:</span><span class="sxs-lookup"><span data-stu-id="b2a2c-107">When workflows are compiled, the following procedures are performed as part of the compilation process:</span></span>

- <span data-ttu-id="b2a2c-108">Sprawdzanie poprawności jest wykonywane w celu upewnienia się, że działania przepływu pracy są sprawdzane na podstawie zasad ustawionych dla siebie.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-108">Validation is performed to ensure that the workflow activities validate based on the rules that the activities have set for themselves.</span></span> <span data-ttu-id="b2a2c-109">Jeśli występują błędy walidacji, kompilator zwraca listę błędów.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-109">If there are validation errors, the compiler returns a list of the errors.</span></span>  
- <span data-ttu-id="b2a2c-110">Klasa częściowa jest generowana z definicji oznakowania, która jest wejściowa do kompilatora.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-110">A partial class is generated from the markup definition that is input into the compiler.</span></span>  

- <span data-ttu-id="b2a2c-111">Kod jest generowany, aby pomóc w wykonywaniu działań w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-111">Code is generated to help with the run-time execution of the activities.</span></span> <span data-ttu-id="b2a2c-112">Generowane są subskrypcje zdarzeń, które ułatwiają działania, gdy działania, które zawierają, są gotowe do wykonania.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-112">Event subscriptions are generated, which help activities know when the activities they contain are finished executing.</span></span>  
- <span data-ttu-id="b2a2c-113">Klasy częściowe wygenerowane na podstawie pliku znaczników i częściowych klas z pliku kodu są wprowadzane do kompilatora .NET Framework C# lub Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-113">The partial classes generated from the markup file and the partial classes from the code file are entered into the .NET Framework C# or Visual Basic compiler.</span></span> <span data-ttu-id="b2a2c-114">Wyjściem tego procesu jest zestaw .NET, WorkflowSample.dll.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-114">The output of this process is the .NET assembly, WorkflowSample.dll.</span></span> <span data-ttu-id="b2a2c-115">Można to wdrożyć, aby uruchomić przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-115">This can be deployed to run the workflow.</span></span>

### <a name="compiler-options"></a><span data-ttu-id="b2a2c-116">Opcje kompilatora</span><span class="sxs-lookup"><span data-stu-id="b2a2c-116">Compiler options</span></span>

<span data-ttu-id="b2a2c-117">W tej sekcji przedstawiono opcje kompilatora wiersza polecenia wfc.exe Workflow.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-117">This section shows the options for the wfc.exe workflow command-line compiler.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b2a2c-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b2a2c-118">Remarks</span></span>
> [!NOTE]
> <span data-ttu-id="b2a2c-119">W tym materiale omówiono przestarzałe typy i przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-119">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="b2a2c-120">Lista autoryzowanych typów jest zwykle zdefiniowana w pliku *wfc.exe.config* .</span><span class="sxs-lookup"><span data-stu-id="b2a2c-120">A list of authorized types is usually defined in the *wfc.exe.config* file.</span></span> <span data-ttu-id="b2a2c-121">W fazie walidacji kompilacji przepływu pracy dokument źródłowy przepływu pracy jest odrzucany, jeśli lub plik reguł pomocnika bezpośrednio odwołuje się do wszystkich typów .NET Framework nieobecnych na liście autoryzowanych typów.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-121">During the validation phase of workflow compilation, a workflow source document is rejected if it or the companion rules file directly references any .NET Framework types not present in a list of authorized types.</span></span> <span data-ttu-id="b2a2c-122">Lista autoryzowanych typów jest dokumentem XML, gdzie każdy wpis wskazuje, a, a `Assembly` `Namespace` `TypeName` i autoryzowany `True` wskaźnik {&#124;`False` }.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-122">The list of authorized types is an XML document where each entry indicates an `Assembly`, a `Namespace`, a `TypeName`, and an Authorized {`True`&#124;`False`} indicator.</span></span> <span data-ttu-id="b2a2c-123">`AuthorizedType` odnosi się do wpisu na liście.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-123">`AuthorizedType` corresponds to an entry in the list.</span></span> <span data-ttu-id="b2a2c-124">Oznaczenia symboli wieloznacznych, które mogą służyć do dołączania lub wykluczania kompletnych przestrzeni nazw, są dozwolone.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-124">Wildcard character designations, which can be used to include or exclude complete namespaces, are allowed.</span></span> <span data-ttu-id="b2a2c-125">Na przykład `Type="System.*"` zawiera wszystkie typy w <xref:System> , w tym typy zawarte w podrzędnych przestrzeniach nazw.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-125">For example, `Type="System.*"` includes all types in <xref:System>, including types contained in child namespaces.</span></span>
  
<span data-ttu-id="b2a2c-126">Użycie listy autoryzowanych typów jest kontrolowane przez <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> opcję `'/checktypes'` .</span><span class="sxs-lookup"><span data-stu-id="b2a2c-126">The use of a list of authorized types is controlled by the <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> option `'/checktypes'`.</span></span>

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
> <span data-ttu-id="b2a2c-127">Gdy `Type="System.*"` Typ jest obecny, można dołączyć do kompilacji inne niezamierzone typy, takie jak `Type="System.Configuration"` .</span><span class="sxs-lookup"><span data-stu-id="b2a2c-127">When `Type="System.*"` type is present, it's possible to include other unintended types, such as `Type="System.Configuration"`, for compilation.</span></span> <span data-ttu-id="b2a2c-128">Należy zachować ostrożność i zapoznać się z każdym z nich.</span><span class="sxs-lookup"><span data-stu-id="b2a2c-128">You should be cautious and review each one.</span></span> <span data-ttu-id="b2a2c-129">Dla dowolnego typu, który powinien być ograniczony, należy ustawić wartość `Authorized` `False` .</span><span class="sxs-lookup"><span data-stu-id="b2a2c-129">For any type that should be restricted, be sure to set `Authorized` to `False`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2a2c-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b2a2c-130">See also</span></span>

- [<span data-ttu-id="b2a2c-131">Autoryzowanetype — Klasa</span><span class="sxs-lookup"><span data-stu-id="b2a2c-131">AuthorizedType class</span></span>](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)
