---
title: Cykl życia konteneryzowanych aplikacji platformy Docker korzystających z platformy i narzędzi firmy Microsoft
description: Zapoznaj się z ogólnym omówieniem procesu opracowywania i wdrażania na potrzeby tworzenia i wdrażania aplikacji kontenerowych przy użyciu platformy Docker i platform i narzędzi firmy Microsoft.
ms.date: 07/30/2020
ms.openlocfilehash: d8055315b25f73d7b0b355026ab6b2c4767f9d89
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915170"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a>Cykl życia konteneryzowanych aplikacji platformy Docker korzystających z platformy i narzędzi firmy Microsoft

![Pokrycie książki](./media/devops-book-cover-large-we.png)

**Edition w wersji 3.1** — zaktualizowany do ASP.NET Core 3,1

Ten przewodnik jest ogólnym omówieniem tworzenia i wdrażania kontenerów ASP.NET Core aplikacji z platformą Docker przy użyciu platformy i narzędzi firmy Microsoft. Przewodnik zawiera ogólne wprowadzenie do usługi Azure DevOps w celu zaimplementowania potoków ciągłej integracji/ciągłego wdrażania, a także Azure Container Registry (ACR) i Azure Kubernetes Services AKS do wdrożenia.

W przypadku szczegółowych informacji związanych z programowaniem można zobaczyć [mikrousługi platformy .NET: architektura dla Zakontenerów aplikacji .NET](https://docs.microsoft.com/dotnet/architecture/microservices/) i powiązanych z nią aplikacji referencyjnych [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).

## <a name="send-us-your-feedback"></a>Wyślij nam swoją opinię.

Utworzyliśmy ten przewodnik, aby ułatwić zrozumienie architektury aplikacji i mikrousług w programie .NET. Przewodnik i powiązana aplikacja referencyjna będą rozwijane, więc będziemy nam powitać Twoją opinię. Jeśli masz komentarze dotyczące tego, jak można ulepszyć ten przewodnik, Prześlij opinię na temat <https://aka.ms/ebookfeedback> .

## <a name="credits"></a>Środki

Autor:

> **Cesar de La Torre**, SR. PM, zespół produktu .NET, Microsoft Corp.

Edytor pozyskiwania:

> **Janine Patryk**

Edytor programistyczny:

> **Robert Russell**, Solutions Professional w firmie Microsoft
>
> [**Publikacja ósemkowa, Inc.**](http://www.octalpub.com/)

Produkcja redakcyjna:

> [Dianne Russell](http://www.octalpub.com/)
>
> **Publikacja ósemkowa, Inc.**

Copyeditor:

> **Robert Russell**, Solutions Professional w firmie Microsoft

Uczestnicy i recenzenci:

> **Nish Anil**, SR. Program Manager, .NET Team, Microsoft
>
> **Miguel Veloso**, inżynier ds. opracowywania oprogramowania z zwykłymi pojęciami
>
> **Sumit Ghosh**, główny konsultant w firmie Neudesic

## <a name="copyright"></a>Prawa autorskie

OPUBLIKOWANA PRZEZ

Dział deweloperów firmy Microsoft, zespoły produktów .NET i Visual Studio

Dział firmy Microsoft Corporation

One Microsoft Way

Redmond, Waszyngton 98052-6399

Copyright &copy; 2020 od firmy Microsoft Corporation

All rights reserved. Żadna część zawartości tej księgi nie może być odtwarzana ani przekazywana w żadnej formie ani za pomocą jakichkolwiek środków bez zgody na wydawcę.

Ta książka jest świadczona w postaci "AS-IS" i zawiera widoki i opinie autora. Widoki, opinie i informacje wyrażone w tej książce, w tym adresy URL i inne odwołania do witryn internetowych, mogą ulec zmianie bez powiadomienia.

Niektóre z przykładów przedstawiono wyłącznie do celów informacyjnych i są one fikcyjne. Żadne rzeczywiste skojarzenia lub związki nie są zamierzone ani wnioskowane.

Firma Microsoft i znaki towarowe wymienione na <https://www.microsoft.com> stronie "znaki towarowe" są znakami towarowymi grupy firm Microsoft.

Komputery Mac i macOS są znakami towarowymi firmy Apple Inc.

Logo Docker Whale jest zastrzeżonym znakiem towarowym platformy Docker, Inc. używanym przez uprawnienie.

Wszystkie inne znaczniki i logo są własnością odpowiednich właścicieli.

>[!div class="step-by-step"]
>[Dalej](introduction-to-containers-and-docker.md)
