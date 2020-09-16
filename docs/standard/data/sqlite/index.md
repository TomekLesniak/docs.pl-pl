---
title: Omówienie
ms.date: 12/13/2019
description: Omówienie programu Microsoft. Data. sqlite
ms.openlocfilehash: 7c952848f7e7ea04f11fe9340f77a1f376a1be07
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552443"
---
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="96c64-103">Microsoft. Data. sqlite — Omówienie</span><span class="sxs-lookup"><span data-stu-id="96c64-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="96c64-104">Microsoft. Data. sqlite to lekki dostawca [ADO.NET](../../../framework/data/adonet/index.md) dla oprogramowania SQLite.</span><span class="sxs-lookup"><span data-stu-id="96c64-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="96c64-105">Dostawca [Entity Framework Core](/ef/core/) dla oprogramowania SQLite został utworzony na podstawie tej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="96c64-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="96c64-106">Można go również używać niezależnie lub z innymi bibliotekami dostępu do danych.</span><span class="sxs-lookup"><span data-stu-id="96c64-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="96c64-107">Instalacja</span><span class="sxs-lookup"><span data-stu-id="96c64-107">Installation</span></span>

<span data-ttu-id="96c64-108">Najnowsza stabilna wersja jest dostępna w programie [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span><span class="sxs-lookup"><span data-stu-id="96c64-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="96c64-109">Interfejs wiersza polecenia platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="96c64-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[<span data-ttu-id="96c64-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96c64-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="96c64-111">Użycie</span><span class="sxs-lookup"><span data-stu-id="96c64-111">Usage</span></span>

<span data-ttu-id="96c64-112">Ta biblioteka implementuje typowe abstrakcje ADO.NET dla połączeń, poleceń, czytników danych i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="96c64-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="96c64-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="96c64-113">See also</span></span>

* [<span data-ttu-id="96c64-114">Parametry połączeń</span><span class="sxs-lookup"><span data-stu-id="96c64-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="96c64-115">Dokumentacja interfejsu API</span><span class="sxs-lookup"><span data-stu-id="96c64-115">API Reference</span></span>](../../../../api/index.md?view=msdata-sqlite-3.0)
* [<span data-ttu-id="96c64-116">Składnia SQL</span><span class="sxs-lookup"><span data-stu-id="96c64-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
