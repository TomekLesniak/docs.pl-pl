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
# <a name="encryption"></a>Szyfrowanie

Program SQLite domyślnie nie obsługuje szyfrowania plików bazy danych. Zamiast tego należy użyć zmodyfikowanej wersji oprogramowania SQLite, takiego jak [See](https://www.hwaci.com/sw/sqlite/see.html), [SQLCIPHER](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/)lub [wxSQLite3](https://utelle.github.io/wxsqlite3). W tym artykule pokazano, jak korzystać z nieobsługiwanej kompilacji SQLCIPHER typu open source, ale informacje dotyczą również innych rozwiązań, ponieważ zwykle są one zgodne z tym samym wzorcem.

## <a name="installation"></a>Instalacja

### <a name="net-core-cli"></a>[Interfejs wiersza polecenia platformy .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

Aby uzyskać więcej informacji na temat korzystania z innej biblioteki natywnej na potrzeby szyfrowania, zobacz [niestandardowe wersje oprogramowania SQLite](custom-versions.md).

## <a name="specify-the-key"></a>Określ klucz

Aby włączyć szyfrowanie dla nowej bazy danych, określ klucz za pomocą `Password` słowa kluczowego Connection. Służy <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> do dodawania lub aktualizowania wartości z danych wejściowych użytkownika i zapobiegania atakom z iniekcją parametrów połączenia.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> Metoda szyfrowania i odszyfrowywania istniejących baz danych różni się w zależności od używanego rozwiązania. Na przykład należy użyć `sqlcipher_export()` funkcji dla elementu SQLCIPHER. Aby uzyskać szczegółowe informacje, zapoznaj się z dokumentacją rozwiązania.

## <a name="rekeying-the-database"></a>Ponowne tworzenie klucza bazy danych

Jeśli chcesz zmienić klucz zaszyfrowanej bazy danych, wygeneruj `PRAGMA rekey` instrukcję.

Niestety, program SQLite nie obsługuje parametrów w `PRAGMA` instrukcjach. Zamiast tego należy użyć `quote()` funkcji, aby zapobiec iniekcji kodu SQL.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
