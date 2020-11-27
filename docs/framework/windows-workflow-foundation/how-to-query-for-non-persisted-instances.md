---
title: 'Instrukcje: Zapytanie dotyczące wystąpień nietrwałych'
ms.date: 03/30/2017
ms.assetid: 294019b1-c1a7-4b81-a14f-b47c106cd723
ms.openlocfilehash: 54a442dab6700dda33cf05df1fb5c60a96bcbd56
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280003"
---
# <a name="how-to-query-for-non-persisted-instances"></a>Instrukcje: Zapytanie dotyczące wystąpień nietrwałych

Gdy tworzone jest nowe wystąpienie usługi, a usługa ma zdefiniowane zachowanie magazynu wystąpień przepływu pracy SQL, Host usługi tworzy wpis początkowy dla tego wystąpienia usługi w magazynie wystąpień. Następnie gdy wystąpienie usługi będzie się powtarzać po raz pierwszy, zachowanie magazynu wystąpień przepływu pracy SQL zapisuje bieżący stan wystąpienia wraz z dodatkowymi danymi, które są wymagane do aktywacji, odzyskiwania i kontroli.

Jeśli wystąpienie nie zostanie utrwalone po utworzeniu początkowego wpisu wystąpienia, wystąpienie usługi jest uznawane za nieutrwalone. Wszystkie utrwalone wystąpienia usługi mogą być badane i kontrolowane. Nie można wykonać zapytania ani kontrolować wystąpień nieutrwalonych usług. Jeśli wystąpienie nieutrwalone zostanie zawieszone z powodu nieobsługiwanego wyjątku, może ono być zapytania, ale nie kontrolowane.

Trwałe wystąpienia usługi, które nie są jeszcze utrwalane, pozostają w stanie nieutrwalonym w następujących scenariuszach:

- Host usługi ulega awarii, zanim wystąpienie zostanie utrwalone po raz pierwszy. Początkowy wpis dla wystąpienia pozostaje w magazynie wystąpień. Wystąpienie nie jest możliwe do odzyskania. Po nadejściu skorelowanego komunikatu wystąpienie zostanie ponownie uaktywnione.

- Wystąpienie napotka nieobsłużony wyjątek, zanim zostanie utrwalone po raz pierwszy. Powstają następujące scenariusze

  - Jeśli wartość właściwości **UnhandledExceptionAction** jest ustawiona na **Abandon**, informacje o wdrożeniu usługi są zapisywane w magazynie wystąpień, a wystąpienie zostanie zwolnione z pamięci. Wystąpienie pozostaje w stanie nieutrwalonym w bazie danych trwałości.

  - Jeśli wartość właściwości **UnhandledExceptionAction** jest ustawiona na **AbandonAndSuspend**, informacje o wdrożeniu usługi są zapisywane w bazie danych trwałości i stan wystąpienia jest ustawiony na **zawieszone**. Nie można wznowić, anulować lub przerwać wystąpienia. Host usługi nie może załadować wystąpienia, ponieważ wystąpienie nie zostało jeszcze utrwalone i dlatego wpis bazy danych dla tego wystąpienia nie został ukończony.

  - Jeśli wartość właściwości **UnhandledExceptionAction** jest ustawiona na **Cancel** lub **Terminate**, informacje o wdrożeniu usługi są zapisywane w magazynie wystąpień i stan wystąpienia jest ustawiony na **ukończone**.

Poniższe sekcje zawierają przykładowe zapytania umożliwiające znalezienie nieutrwalonych wystąpień w bazie danych trwałości SQL i usunięcie tych wystąpień z bazy danych.

## <a name="to-find-all-instances-not-persisted-yet"></a>Aby znaleźć wszystkie wystąpienia nieutrwalone jeszcze

Następujące zapytanie SQL zwraca identyfikator i czas utworzenia dla wszystkich wystąpień, które nie są jeszcze utrwalone w bazie danych trwałości.

```sql
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0;
```

## <a name="to-find-all-instances-not-persisted-yet-and-also-not-loaded"></a>Aby znaleźć wszystkie wystąpienia, które nie zostały jeszcze utrwalone i nie zostały załadowane

 Następujące zapytanie SQL zwraca identyfikator i czas utworzenia dla wszystkich wystąpień, które nie są utrwalone i nie są ładowane.

```sql
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and CurrentMachine is NULL;
```

## <a name="to-find-all-suspended-instances-not-persisted-yet"></a>Aby znaleźć wszystkie wstrzymane wystąpienia, które nie zostały jeszcze utrwalone

Następujące zapytanie SQL zwraca identyfikator, czas utworzenia, przyczynę zawieszenia i nazwę wyjątku zawieszenia dla wszystkich wystąpień, które nie są utrwalane, a także w stanie wstrzymania.

```sql
select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and IsSuspended = 1;
```

## <a name="to-delete-non-persisted-instances-from-the-persistence-database"></a>Aby usunąć nieutrwalone wystąpienia z bazy danych trwałości

Należy okresowo sprawdzać magazyn wystąpień dla nieutrwalonych wystąpień i usuwać wystąpienia z magazynu wystąpień, jeśli masz pewność, że wystąpienie nie otrzyma komunikatu skorelowanego. Jeśli na przykład wystąpienie znajduje się w bazie danych przez kilka miesięcy i wiadomo, że przepływ pracy ma zwykle okres istnienia kilku dni, można bezpiecznie założyć, że jest to niezainicjowane wystąpienie, które uległo awarii.

Ogólnie rzecz biorąc, można bezpiecznie usunąć nieutrwalone wystąpienia, które nie zostały zawieszone lub nie zostały załadowane. Nie należy usuwać **wszystkich** nieutrwalonych wystąpień, ponieważ to ustawienie obejmuje wystąpienia, które zostały właśnie utworzone, ale nie zostały jeszcze utrwalone. Należy usunąć tylko nieutrwalone wystąpienia, które zostały pozostawione, ponieważ Host usługi przepływu pracy z załadowanym wystąpieniem spowodował wyjątek lub samo wystąpienie spowodowało wyjątek.

> [!WARNING]
> Usuwanie nieutrwalonych wystąpień z magazynu wystąpień zmniejsza rozmiar magazynu i może poprawić wydajność operacji magazynu.
