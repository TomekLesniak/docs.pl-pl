---
title: Szyfrowanie
ms.date: 09/08/2020
description: Dowiedz się, jak zaszyfrować plik bazy danych.
ms.openlocfilehash: 1b33e1510a269aba87caba2cd39faab33791aa55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203413"
---
# <a name="encryption"></a><span data-ttu-id="2b306-103">Szyfrowanie</span><span class="sxs-lookup"><span data-stu-id="2b306-103">Encryption</span></span>

<span data-ttu-id="2b306-104">Program SQLite domyślnie nie obsługuje szyfrowania plików bazy danych.</span><span class="sxs-lookup"><span data-stu-id="2b306-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="2b306-105">Zamiast tego należy użyć zmodyfikowanej wersji oprogramowania SQLite, takiego jak [See](https://www.hwaci.com/sw/sqlite/see.html), [SQLCIPHER](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/)lub [wxSQLite3](https://utelle.github.io/wxsqlite3).</span><span class="sxs-lookup"><span data-stu-id="2b306-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="2b306-106">W tym artykule pokazano, jak korzystać z nieobsługiwanej kompilacji SQLCIPHER typu open source, ale informacje dotyczą również innych rozwiązań, ponieważ zwykle są one zgodne z tym samym wzorcem.</span><span class="sxs-lookup"><span data-stu-id="2b306-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="2b306-107">Instalacja</span><span class="sxs-lookup"><span data-stu-id="2b306-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="2b306-108">Interfejs wiersza polecenia platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="2b306-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="2b306-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2b306-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="2b306-110">Aby uzyskać więcej informacji na temat korzystania z innej biblioteki natywnej na potrzeby szyfrowania, zobacz [niestandardowe wersje oprogramowania SQLite](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="2b306-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="2b306-111">Określ klucz</span><span class="sxs-lookup"><span data-stu-id="2b306-111">Specify the key</span></span>

<span data-ttu-id="2b306-112">Aby włączyć szyfrowanie dla nowej bazy danych, określ klucz za pomocą `Password` słowa kluczowego Connection.</span><span class="sxs-lookup"><span data-stu-id="2b306-112">To enable encryption on a new database, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="2b306-113">Służy <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> do dodawania lub aktualizowania wartości z danych wejściowych użytkownika i zapobiegania atakom z iniekcją parametrów połączenia.</span><span class="sxs-lookup"><span data-stu-id="2b306-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> <span data-ttu-id="2b306-114">Metoda szyfrowania i odszyfrowywania istniejących baz danych różni się w zależności od używanego rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="2b306-114">The method for encrypting and decrypting existing databases varies depending on which solution you're using.</span></span> <span data-ttu-id="2b306-115">Na przykład należy użyć `sqlcipher_export()` funkcji dla elementu SQLCIPHER.</span><span class="sxs-lookup"><span data-stu-id="2b306-115">For example, you need to use the `sqlcipher_export()` function on SQLCipher.</span></span> <span data-ttu-id="2b306-116">Aby uzyskać szczegółowe informacje, zapoznaj się z dokumentacją rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="2b306-116">Check your solution's documentation for details.</span></span>

## <a name="rekeying-the-database"></a><span data-ttu-id="2b306-117">Ponowne tworzenie klucza bazy danych</span><span class="sxs-lookup"><span data-stu-id="2b306-117">Rekeying the database</span></span>

<span data-ttu-id="2b306-118">Jeśli chcesz zmienić klucz zaszyfrowanej bazy danych, wygeneruj `PRAGMA rekey` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="2b306-118">If you want to change the key of an encrypted database, issue a `PRAGMA rekey` statement.</span></span>

<span data-ttu-id="2b306-119">Niestety, program SQLite nie obsługuje parametrów w `PRAGMA` instrukcjach.</span><span class="sxs-lookup"><span data-stu-id="2b306-119">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="2b306-120">Zamiast tego należy użyć `quote()` funkcji, aby zapobiec iniekcji kodu SQL.</span><span class="sxs-lookup"><span data-stu-id="2b306-120">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
