---
title: dotnet sln — polecenie
description: Polecenie dotnet-sln udostępnia wygodną opcję dodawania, usuwania i wyświetlania listy projektów w pliku rozwiązania.
ms.date: 02/14/2020
ms.openlocfilehash: 898c53772a28b8cc3b65532dfc3d9bd6e73d467c
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634373"
---
# <a name="dotnet-sln"></a><span data-ttu-id="17d96-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="17d96-103">dotnet sln</span></span>

<span data-ttu-id="17d96-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 2. x SDK i nowszych wersji</span><span class="sxs-lookup"><span data-stu-id="17d96-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="17d96-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="17d96-105">Name</span></span>

<span data-ttu-id="17d96-106">`dotnet sln` -Wyświetla lub modyfikuje projekty w pliku rozwiązania platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="17d96-106">`dotnet sln` - Lists or modifies the projects in a .NET solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="17d96-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="17d96-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a><span data-ttu-id="17d96-108">Opis</span><span class="sxs-lookup"><span data-stu-id="17d96-108">Description</span></span>

<span data-ttu-id="17d96-109">`dotnet sln`Polecenie zapewnia wygodny sposób wyświetlania i modyfikowania projektów w pliku rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="17d96-110">Aby użyć `dotnet sln` polecenia, plik rozwiązania musi już istnieć.</span><span class="sxs-lookup"><span data-stu-id="17d96-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="17d96-111">Jeśli trzeba ją utworzyć, użyj polecenia [dotnet New](dotnet-new.md) , jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="17d96-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="17d96-112">Argumenty</span><span class="sxs-lookup"><span data-stu-id="17d96-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="17d96-113">Plik rozwiązania, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="17d96-113">The solution file to use.</span></span> <span data-ttu-id="17d96-114">Jeśli ten argument zostanie pominięty, polecenie przeszukuje bieżący katalog.</span><span class="sxs-lookup"><span data-stu-id="17d96-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="17d96-115">Jeśli nie zostanie znaleziony żaden plik rozwiązania lub wiele plików rozwiązania, polecenie nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="17d96-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="17d96-116">Opcje</span><span class="sxs-lookup"><span data-stu-id="17d96-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="17d96-117">Drukuje opis sposobu użycia polecenia.</span><span class="sxs-lookup"><span data-stu-id="17d96-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="17d96-118">Polecenia</span><span class="sxs-lookup"><span data-stu-id="17d96-118">Commands</span></span>

### `list`

<span data-ttu-id="17d96-119">Wyświetla wszystkie projekty w pliku rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="17d96-120">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="17d96-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="17d96-121">Argumenty</span><span class="sxs-lookup"><span data-stu-id="17d96-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="17d96-122">Plik rozwiązania, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="17d96-122">The solution file to use.</span></span> <span data-ttu-id="17d96-123">Jeśli ten argument zostanie pominięty, polecenie przeszukuje bieżący katalog.</span><span class="sxs-lookup"><span data-stu-id="17d96-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="17d96-124">Jeśli nie zostanie znaleziony żaden plik rozwiązania lub wiele plików rozwiązania, polecenie nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="17d96-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="17d96-125">Opcje</span><span class="sxs-lookup"><span data-stu-id="17d96-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="17d96-126">Drukuje opis sposobu użycia polecenia.</span><span class="sxs-lookup"><span data-stu-id="17d96-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="17d96-127">Dodaje jeden lub więcej projektów do pliku rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="17d96-128">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="17d96-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="17d96-129">Argumenty</span><span class="sxs-lookup"><span data-stu-id="17d96-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="17d96-130">Plik rozwiązania, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="17d96-130">The solution file to use.</span></span> <span data-ttu-id="17d96-131">Jeśli nie jest określony, polecenie przeszukuje bieżący katalog dla jednego i kończy się niepowodzeniem, jeśli istnieje wiele plików rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="17d96-132">Ścieżka do projektu lub projektów, które mają zostać dodane do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="17d96-133">Rozszerzenia [wzorca obsługi symboli wieloznacznych](https://en.wikipedia.org/wiki/Glob_(programming)) powłoki systemu UNIX/Linux są przetwarzane prawidłowo przez `dotnet sln` polecenie.</span><span class="sxs-lookup"><span data-stu-id="17d96-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="17d96-134">Opcje</span><span class="sxs-lookup"><span data-stu-id="17d96-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="17d96-135">Drukuje opis sposobu użycia polecenia.</span><span class="sxs-lookup"><span data-stu-id="17d96-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="17d96-136">Umieszcza projekty w katalogu głównym rozwiązania zamiast tworzenia folderu rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="17d96-137">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="17d96-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder <PATH>`**

  <span data-ttu-id="17d96-138">Ścieżka folderu rozwiązania docelowego, do którego mają zostać dodane projekty.</span><span class="sxs-lookup"><span data-stu-id="17d96-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="17d96-139">Dostępne od wersji .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="17d96-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="17d96-140">Usuwa projekt lub wiele projektów z pliku rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="17d96-141">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="17d96-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="17d96-142">Argumenty</span><span class="sxs-lookup"><span data-stu-id="17d96-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="17d96-143">Plik rozwiązania, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="17d96-143">The solution file to use.</span></span> <span data-ttu-id="17d96-144">Jeśli pozostanie nieokreślony, polecenie przeszukuje bieżący katalog dla jednego i kończy się niepowodzeniem, jeśli istnieje wiele plików rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="17d96-145">Ścieżka do projektu lub projektów, które mają zostać dodane do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="17d96-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="17d96-146">Rozszerzenia [wzorca obsługi symboli wieloznacznych](https://en.wikipedia.org/wiki/Glob_(programming)) powłoki systemu UNIX/Linux są przetwarzane prawidłowo przez `dotnet sln` polecenie.</span><span class="sxs-lookup"><span data-stu-id="17d96-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="17d96-147">Opcje</span><span class="sxs-lookup"><span data-stu-id="17d96-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="17d96-148">Drukuje opis sposobu użycia polecenia.</span><span class="sxs-lookup"><span data-stu-id="17d96-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="17d96-149">Przykłady</span><span class="sxs-lookup"><span data-stu-id="17d96-149">Examples</span></span>

- <span data-ttu-id="17d96-150">Utwórz listę projektów w rozwiązaniu:</span><span class="sxs-lookup"><span data-stu-id="17d96-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="17d96-151">Dodaj projekt C# do rozwiązania:</span><span class="sxs-lookup"><span data-stu-id="17d96-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="17d96-152">Usuń projekt C# z rozwiązania:</span><span class="sxs-lookup"><span data-stu-id="17d96-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="17d96-153">Dodaj wiele projektów C# do katalogu głównego rozwiązania:</span><span class="sxs-lookup"><span data-stu-id="17d96-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="17d96-154">Dodaj wiele projektów C# do rozwiązania:</span><span class="sxs-lookup"><span data-stu-id="17d96-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="17d96-155">Usuń wiele projektów C# z rozwiązania:</span><span class="sxs-lookup"><span data-stu-id="17d96-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="17d96-156">Dodawanie wielu projektów C# do rozwiązania przy użyciu wzorca obsługi symboli wieloznacznych (tylko w systemie UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="17d96-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="17d96-157">Dodawanie wielu projektów C# do rozwiązania przy użyciu wzorca obsługi symboli wieloznacznych (tylko program Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="17d96-157">Add multiple C# projects to a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- <span data-ttu-id="17d96-158">Usuwanie wielu projektów C# z rozwiązania przy użyciu wzorca obsługi symboli wieloznacznych (tylko w systemie UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="17d96-158">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- <span data-ttu-id="17d96-159">Usuwanie wielu projektów C# z rozwiązania przy użyciu wzorca obsługi symboli wieloznacznych (tylko program Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="17d96-159">Remove multiple C# projects from a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```
