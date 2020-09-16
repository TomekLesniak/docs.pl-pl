---
ms.openlocfilehash: 19002cce40fdc929716a761a5e01303be4decb35
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537834"
---
<span data-ttu-id="931d0-101">Nie trzeba uruchamiać programu [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) , ponieważ jest on uruchamiany niejawnie przez wszystkie polecenia, które wymagają wykonania przywracania, takie jak,,,, `dotnet new` `dotnet build` `dotnet run` `dotnet test` `dotnet publish` i `dotnet pack` .</span><span class="sxs-lookup"><span data-stu-id="931d0-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="931d0-102">Aby wyłączyć Przywracanie niejawne, użyj `--no-restore` opcji.</span><span class="sxs-lookup"><span data-stu-id="931d0-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="931d0-103">`dotnet restore`Polecenie jest nadal przydatne w niektórych scenariuszach, w których jawne jest przywracanie, takie jak [kompilacje ciągłej integracji w Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) lub w systemach kompilacji, które muszą jawnie kontrolować po wystąpieniu przywracania.</span><span class="sxs-lookup"><span data-stu-id="931d0-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="931d0-104">Informacje o sposobach zarządzania źródłami danych NuGet znajdują się w [ `dotnet restore` dokumentacji](../docs/core/tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="931d0-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>

<span data-ttu-id="931d0-105">To polecenie obsługuje `dotnet restore` Opcje, gdy są przesyłane w postaci długiej (na przykład `--source` ).</span><span class="sxs-lookup"><span data-stu-id="931d0-105">This command supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="931d0-106">Opcje krótkiej formy, takie jak `-s` , nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="931d0-106">Short form options, such as `-s`, are not supported.</span></span>
