---
title: Włączanie uzupełniania po naciśnięciu tabulatora
description: W tym artykule opisano, jak włączyć uzupełnianie kart dla interfejs wiersza polecenia platformy .NET Core dla programu PowerShell, bash i ZSH.
author: adegeo
ms.author: adegeo
ms.topic: how-to
ms.date: 11/03/2019
ms.openlocfilehash: cd46305b8cd82825671a3a1568e8b93de1bbab26
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062811"
---
# <a name="how-to-enable-tab-completion-for-the-net-core-cli"></a><span data-ttu-id="c6c35-103">Jak włączyć uzupełnianie kart dla interfejs wiersza polecenia platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="c6c35-103">How to enable TAB completion for the .NET Core CLI</span></span>

<span data-ttu-id="c6c35-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,1 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="c6c35-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="c6c35-105">W tym artykule opisano sposób konfigurowania uzupełniania tabulatorów dla trzech powłok, programu PowerShell, bash i ZSH.</span><span class="sxs-lookup"><span data-stu-id="c6c35-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="c6c35-106">W przypadku innych powłok należy zapoznać się z dokumentacją dotyczącą konfigurowania uzupełniania kart.</span><span class="sxs-lookup"><span data-stu-id="c6c35-106">For other shells, refer to their documentation on how to configure tab completion.</span></span>

<span data-ttu-id="c6c35-107">Po skonfigurowaniu, uzupełnianie kart dla interfejs wiersza polecenia platformy .NET Core jest wyzwalane przez wpisanie `dotnet` polecenia w powłoce, a następnie naciśnięcie klawisza Tab.</span><span class="sxs-lookup"><span data-stu-id="c6c35-107">Once set up, tab completion for the .NET Core CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="c6c35-108">Bieżący wiersz polecenia jest wysyłany do `dotnet complete` polecenia, a wyniki są przetwarzane przez powłokę.</span><span class="sxs-lookup"><span data-stu-id="c6c35-108">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="c6c35-109">Wyniki można testować bez włączania kończenia karty, wysyłając coś bezpośrednio do `dotnet complete` polecenia.</span><span class="sxs-lookup"><span data-stu-id="c6c35-109">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="c6c35-110">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="c6c35-110">For example:</span></span>

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="c6c35-111">Jeśli to polecenie nie działa, upewnij się, że jest zainstalowany zestaw .NET Core 2,0 SDK lub nowszy.</span><span class="sxs-lookup"><span data-stu-id="c6c35-111">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="c6c35-112">Jeśli jest zainstalowana, ale to polecenie nadal nie działa, upewnij się, że `dotnet` polecenie jest rozpoznawane jako wersja zestawu SDK platformy .NET Core 2,0 i nowsze.</span><span class="sxs-lookup"><span data-stu-id="c6c35-112">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="c6c35-113">Użyj `dotnet --version` polecenia, aby sprawdzić `dotnet` , która wersja bieżącej ścieżki jest rozpoznawana.</span><span class="sxs-lookup"><span data-stu-id="c6c35-113">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="c6c35-114">Aby uzyskać więcej informacji, zobacz [Wybieranie wersji platformy .NET Core do użycia](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="c6c35-114">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="c6c35-115">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c6c35-115">Examples</span></span>

<span data-ttu-id="c6c35-116">Poniżej przedstawiono kilka przykładów zapewniania przez uzupełnianie kart:</span><span class="sxs-lookup"><span data-stu-id="c6c35-116">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="c6c35-117">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c6c35-117">Input</span></span>                                | <span data-ttu-id="c6c35-118">stanowi</span><span class="sxs-lookup"><span data-stu-id="c6c35-118">becomes</span></span>                                                                     | <span data-ttu-id="c6c35-119">, ponieważ klienci usługi</span><span class="sxs-lookup"><span data-stu-id="c6c35-119">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="c6c35-120">`add`to pierwsze polecenie, alfabetycznie.</span><span class="sxs-lookup"><span data-stu-id="c6c35-120">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="c6c35-121">Uzupełnianie tabulacji dopasowuje podciągi i pojawia się w `--help` pierwszej kolejności alfabetycznie.</span><span class="sxs-lookup"><span data-stu-id="c6c35-121">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="c6c35-122">Naciśnięcie klawisza Tab drugi raz spowoduje wyświetlenie następnej sugestii.</span><span class="sxs-lookup"><span data-stu-id="c6c35-122">Pressing tab a second time brings up the next suggestion.</span></span>
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="c6c35-123">Wyniki są zwracane w porządku alfabetycznym.</span><span class="sxs-lookup"><span data-stu-id="c6c35-123">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="c6c35-124">Uzupełnianie karty jest świadome pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="c6c35-124">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="c6c35-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6c35-125">PowerShell</span></span>

<span data-ttu-id="c6c35-126">Aby dodać uzupełnianie tabulatorów do **programu PowerShell** dla interfejs wiersza polecenia platformy .NET Core, Utwórz lub Edytuj profil przechowywany w zmiennej `$PROFILE` .</span><span class="sxs-lookup"><span data-stu-id="c6c35-126">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="c6c35-127">Aby uzyskać więcej informacji, zobacz [jak utworzyć profil](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) i [zasady wykonywania](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span><span class="sxs-lookup"><span data-stu-id="c6c35-127">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span></span>

<span data-ttu-id="c6c35-128">Dodaj następujący kod do swojego profilu:</span><span class="sxs-lookup"><span data-stu-id="c6c35-128">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="c6c35-129">bash</span><span class="sxs-lookup"><span data-stu-id="c6c35-129">bash</span></span>

<span data-ttu-id="c6c35-130">Aby dodać uzupełnianie karty do powłoki **bash** dla interfejs wiersza polecenia platformy .NET Core, Dodaj następujący kod do `.bashrc` pliku:</span><span class="sxs-lookup"><span data-stu-id="c6c35-130">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}" 2>/dev/null)"
  if [ $? -ne 0 ]; then
    completions=""
  fi

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="c6c35-131">zsh</span><span class="sxs-lookup"><span data-stu-id="c6c35-131">zsh</span></span>

<span data-ttu-id="c6c35-132">Aby dodać uzupełnianie karty do powłoki **ZSH** dla interfejs wiersza polecenia platformy .NET Core, Dodaj następujący kod do `.zshrc` pliku:</span><span class="sxs-lookup"><span data-stu-id="c6c35-132">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
