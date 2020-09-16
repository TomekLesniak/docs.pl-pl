---
title: Parametry połączeń
ms.date: 12/13/2019
description: Obsługiwane słowa kluczowe i wartości parametrów połączenia.
ms.openlocfilehash: 3c50b31689abf6d47aa8f83a6f6f755bcfec0ea3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555396"
---
# <a name="connection-strings"></a>Parametry połączeń

Parametry połączenia służą do określania sposobu łączenia się z bazą danych. Parametry połączenia w firmie Microsoft. Data. sqlite są zgodne ze standardową [składnią ADO.NET](../../../framework/data/adonet/connection-strings.md) jako listę słów kluczowych i wartości rozdzielonych średnikami.

## <a name="keywords"></a>Słowa kluczowe

Następujące słowa kluczowe parametrów połączenia mogą być używane z firmą Microsoft. Data. sqlite:

### <a name="data-source"></a>Źródło danych

Ścieżka do pliku bazy danych. *Źródła danych* (bez spacji) i *filename* są aliasami tego słowa kluczowego.

SQLite traktuje ścieżki względem bieżącego katalogu roboczego. Można również określić ścieżki bezwzględne.

Jeśli ta wartość jest **pusta**, program SQLite tworzy tymczasową bazę danych na dysku, która jest usuwana po zamknięciu połączenia.

Jeśli `:memory:` używana jest baza danych w pamięci. Aby uzyskać więcej informacji, zobacz [bazy danych w pamięci](in-memory-databases.md).

Ścieżki, które zaczynają się od `|DataDirectory|` ciągu podstawiania są traktowane tak samo jak ścieżki względne. W przypadku ustawienia ścieżki są tworzone względem wartości właściwości domena aplikacji usługi DataDirectory.

To słowo kluczowe obsługuje również [nazwy plików URI](https://www.sqlite.org/uri.html).

### <a name="mode"></a>Tryb

Tryb połączenia.

| Wartość           | Opis                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | Otwiera bazę danych do odczytu i zapisu, a następnie tworzy ją, jeśli nie istnieje. Jest to opcja domyślna. |
| Odczyt/zapis       | Otwiera bazę danych do odczytu i zapisu.                                                        |
| ReadOnly        | Otwiera bazę danych w trybie tylko do odczytu.                                                              |
| Pamięć          | Otwiera bazę danych w pamięci.                                                                       |

### <a name="cache"></a>Pamięć podręczna

Tryb buforowania używany przez połączenie.

| Wartość   | Opis                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| Domyślny | Używa domyślnego trybu podstawowej biblioteki programu SQLite. Jest to opcja domyślna.                   |
| Private | Każde połączenie używa prywatnej pamięci podręcznej.                                                          |
| Shared  | Połączenia korzystają z pamięci podręcznej. Ten tryb pozwala zmienić zachowanie blokowania transakcji i tabel. |

### <a name="password"></a>Hasło

Klucz szyfrowania. Gdy ta `PRAGMA key` wartość jest określona, jest wysyłana natychmiast po otwarciu połączenia.

> [!WARNING]
> Hasło nie ma znaczenia, jeśli szyfrowanie nie jest obsługiwane przez natywną bibliotekę oprogramowania SQLite.

### <a name="foreign-keys"></a>Klucze obce

Wartość wskazująca, czy należy włączyć ograniczenia klucza obcego.

| Wartość   | Opis
| ------- | --- |
| Prawda    | Wysyła `PRAGMA foreign_keys = 1` natychmiast po otwarciu połączenia.
| Fałsz   | Wysyła `PRAGMA foreign_keys = 0` natychmiast po otwarciu połączenia.
| ciągiem | Nie wysyła `PRAGMA foreign_keys` . Jest to opcja domyślna. |

Nie ma potrzeby włączania kluczy obcych, jeśli tak, jak w e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS został użyty do skompilowania natywnej biblioteki programu SQLite.

### <a name="recursive-triggers"></a>Wyzwalacze cykliczne

Wartość wskazująca, czy włączyć Wyzwalacze cykliczne.

| Wartość | Opis                                                                 |
| ----- | --------------------------------------------------------------------------- |
| Prawda  | Wysyła `PRAGMA recursive_triggers` natychmiast po otwarciu połączenia. |
| Fałsz | Nie wysyła `PRAGMA recursive_triggers` . Jest to opcja domyślna.              |

## <a name="connection-string-builder"></a>Konstruktor parametrów połączenia

Można użyć <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> jako jednoznacznie określonego sposobu tworzenia parametrów połączenia. Można go również użyć, aby zapobiec atakom polegającym na iniekcji parametrów połączenia.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>Przykłady

### <a name="basic"></a>Podstawowy

Podstawowe parametry połączenia z udostępnioną pamięcią podręczną w celu zwiększenia współbieżności.

```connectionstring
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>Zaszyfrowane

Zaszyfrowana baza danych.

```connectionstring
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>Tylko odczyt

Baza danych tylko do odczytu, która nie może być modyfikowana przez aplikację.

```connectionstring
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>W pamięci

Prywatna baza danych w pamięci.

```connectionstring
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>Współużytkowana pamięć

Współużytkowana baza danych w pamięci identyfikowana przy użyciu nazwy, którą można *udostępniać*.

```connectionstring
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>Zobacz także

* [Parametry połączenia w ADO.NET](../../../framework/data/adonet/connection-strings.md)
* [Bazy danych w pamięci](in-memory-databases.md)
* [Transakcje](transactions.md)
