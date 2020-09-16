---
title: Transakcje
ms.date: 09/08/2020
description: Dowiedz się, jak używać transakcji.
ms.openlocfilehash: 50c4cd1023eac892cafc3ae4395e9168bd8e9f36
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678865"
---
# <a name="transactions"></a>Transakcje

Transakcje umożliwiają grupowanie wielu instrukcji SQL w jednej jednostce pracy, która jest zatwierdzona do bazy danych jako jedną jednostką niepodzielną. Jeśli jakakolwiek instrukcja w transakcji nie powiedzie się, zmiany wprowadzone przez poprzednie instrukcje można wycofać. Początkowy stan bazy danych, gdy transakcja została uruchomiona, jest zachowywany. Korzystanie z transakcji może również zwiększyć wydajność na konferencji SQLite podczas jednoczesnego wprowadzania wielu zmian w bazie danych.

## <a name="concurrency"></a>Współbieżność

W przypadku oprogramowania SQLite w danej chwili w bazie danych może istnieć tylko jedna transakcja oczekująca na zmianę. Z tego powodu wywołania <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> i `Execute` metody w programie <xref:Microsoft.Data.Sqlite.SqliteCommand> mogą przekroczyć limit czasu, jeśli wykonywanie innej transakcji trwa zbyt długo.

Aby uzyskać więcej informacji na temat blokowania, ponawiania prób i przekroczeń limitu czasu, zobacz [Błędy bazy danych](database-errors.md).

## <a name="isolation-levels"></a>Poziomy izolacji

Transakcje są domyślnie **serializowane** w programie SQLite. Ten poziom izolacji gwarantuje, że wszelkie zmiany wprowadzone w ramach transakcji są całkowicie odizolowane. Zmiany transakcji nie wpływają na inne instrukcje wykonywane poza transakcją.

W przypadku korzystania z udostępnionej pamięci podręcznej program SQLite obsługuje także **Odczyt niezatwierdzony** . Ten poziom umożliwia odczyty zanieczyszczone, odczyty niepowtarzalne i fantomy:

- *Nieprzeczytany odczyt* występuje, gdy zmiany oczekujące w jednej transakcji są zwracane przez zapytanie poza transakcją, ale zmiany transakcji są wycofywane. Wyniki zawierają dane, które nigdy nie zostały przekazane do bazy danych.

- Odczyt, który nie jest *powtarzany* , występuje, gdy transakcja kwerendy tego samego wiersza dwa razy, ale wyniki są różne, ponieważ zostały zmienione przez inną transakcję.

- *Fantomy* to wiersze, które są zmieniane lub dodawane, aby spełniały klauzulę WHERE zapytania podczas transakcji. Jeśli jest to dozwolone, to samo zapytanie może zwracać różne wiersze, gdy są wykonywane dwa razy w tej samej transakcji.

Microsoft. Data. sqlite traktuje IsolationLevel <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> jako poziom minimalny. Rzeczywisty poziom izolacji zostanie podwyższony do odczytu niezatwierdzonego lub możliwego do serializacji.

Poniższy kod symuluje przeczytanie zanieczyszczone. Należy pamiętać, że parametry połączenia muszą zawierać `Cache=Shared` .

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]

## <a name="deferred-transactions"></a>Odroczone transakcje

Począwszy od firmy Microsoft. Data. sqlite w wersji 5,0, można odroczyć transakcje. W ten sposób zostanie wykonane tworzenie rzeczywistej transakcji w bazie danych do momentu wykonania pierwszego polecenia. Powoduje to również, że transakcja jest stopniowo uaktualniana z transakcji odczytu do transakcji zapisu, zgodnie z wymaganiami poleceń. Może to być przydatne w przypadku włączania współbieżnego dostępu do bazy danych podczas transakcji.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DeferredTransactionSample/Program.cs?name=snippet_DeferredTransaction)]

> [!WARNING]
> Polecenia wewnątrz odroczonej transakcji mogą się nie powieść, jeśli powodują, że transakcja zostanie uaktualniona z transakcji odczytu do transakcji zapisu, gdy baza danych jest zablokowana. W takim przypadku aplikacja będzie musiała ponowić próbę całej transakcji.
