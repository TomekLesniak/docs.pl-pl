---
title: Dodatek-gRPC dla deweloperów WCF
description: Omówienie transakcji rozproszonych i ich implementacji w nowoczesnych architekturach mikrousług.
ms.date: 09/02/2019
ms.openlocfilehash: f60899463a13e9f740f6ae63150d18eab3069124
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165861"
---
# <a name="appendix-a---transactions"></a>Dodatek A — transakcje

Windows Communication Foundation (WCF) obsługuje transakcje rozproszone, umożliwiając wykonywanie operacji niepodzielnych w wielu usługach. Ta funkcja jest oparta na [Distributed Transaction Coordinator firmy Microsoft](/previous-versions/windows/desktop/ms684146(v=vs.85)).

W przypadku nowszych mikrousług na poziomie, ten typ zautomatyzowanego przetwarzania transakcji rozproszonych nie jest możliwy. Istnieje zbyt wiele różnych technologii, w tym relacyjne bazy danych, NoSQLe magazyny danych i systemy obsługi komunikatów. Może to być również kombinacja systemów operacyjnych, języków programowania i platform używanych w jednym środowisku.

Transakcja rozproszona WCF to implementacja tego, co jest znane jako [dwufazowe zatwierdzanie (2PC)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol). Transakcje 2PC można zaimplementować ręcznie przez koordynowanie komunikatów między usługami, tworzenie otwartych transakcji w ramach każdej usługi i wysyłanie komunikatów zatwierdzania lub wycofywania, w zależności od sukcesu lub niepowodzenia. Jednak stopień złożoności związany z zarządzaniem 2PC może wzrosnąć w miarę rozwoju systemów. Otwarte transakcje przechowują blokady bazy danych, które mogą negatywnie wpłynąć na wydajność, lub gorszą, powodują zakleszczenie między usługami.

Jeśli to możliwe, najlepiej jest unikać transakcji rozproszonych. Jeśli dwa elementy danych są tak połączone jak w celu żądania niepodzielnych aktualizacji, należy rozważyć ich obsługę zarówno w ramach tej samej usługi. Zastosuj te niepodzielne zmiany za pomocą pojedynczego żądania lub wiadomości do tej usługi.

Jeśli to nie jest możliwe, jedną alternatywą jest użycie [wzorca Saga](https://microservices.io/patterns/data/saga.html). W Saga aktualizacje są przetwarzane sekwencyjnie; Po pomyślnej aktualizacji każda z nich zostanie wyzwolona. Te wyzwalacze mogą być propagowane z usługi do usługi lub zarządzane przez koordynatora Saga lub program Orchestrator. Jeśli aktualizacja nie powiedzie się w dowolnym momencie w trakcie tego procesu, usługi, które już ukończyły aktualizacje, stosują określoną logikę do odwrócenia.

Kolejną opcją jest użycie konstrukcji opartej na domenie (DDD) i polecenia/zapytania (CQRS), zgodnie z opisem w [książce elektronicznej mikrousług .NET](../microservices/microservice-ddd-cqrs-patterns/index.md). W szczególności użycie zdarzeń domeny lub [źródła zdarzeń](https://martinfowler.com/eaaDev/EventSourcing.html) może pomóc w zapewnieniu, że aktualizacje są spójne, jeśli nie zostaną zastosowane natychmiast.

>[!div class="step-by-step"]
>[Poprzednie](application-performance-management.md)
