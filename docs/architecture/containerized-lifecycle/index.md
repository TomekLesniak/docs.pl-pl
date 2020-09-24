---
title: Cykl życia konteneryzowanych aplikacji platformy Docker korzystających z platformy i narzędzi firmy Microsoft
description: Zapoznaj się z ogólnym omówieniem procesu opracowywania i wdrażania na potrzeby tworzenia i wdrażania aplikacji kontenerowych przy użyciu platformy Docker i platform i narzędzi firmy Microsoft.
ms.date: 07/30/2020
ms.openlocfilehash: c506a3423ac4511f23452192e361e88dce6efec4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160700"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a><span data-ttu-id="db0d1-103">Cykl życia konteneryzowanych aplikacji platformy Docker korzystających z platformy i narzędzi firmy Microsoft</span><span class="sxs-lookup"><span data-stu-id="db0d1-103">Containerized Docker Application Lifecycle with Microsoft Platform and Tools</span></span>

![Pokrycie książki](./media/devops-book-cover-large-we.png)

<span data-ttu-id="db0d1-105">**Edition w wersji 3.1** — zaktualizowany do ASP.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="db0d1-105">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="db0d1-106">Ten przewodnik jest ogólnym omówieniem tworzenia i wdrażania kontenerów ASP.NET Core aplikacji z platformą Docker przy użyciu platformy i narzędzi firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db0d1-106">This guide is a general overview for developing and deploying containerized ASP.NET Core applications with Docker, using the Microsoft platform and tools.</span></span> <span data-ttu-id="db0d1-107">Przewodnik zawiera ogólne wprowadzenie do usługi Azure DevOps w celu zaimplementowania potoków ciągłej integracji/ciągłego wdrażania, a także Azure Container Registry (ACR) i Azure Kubernetes Services AKS do wdrożenia.</span><span class="sxs-lookup"><span data-stu-id="db0d1-107">The guide includes a high-level introduction to Azure DevOps, for implementing CI/CD pipelines, as well as Azure Container Registry (ACR), and Azure Kubernetes Services AKS for deployment.</span></span>

<span data-ttu-id="db0d1-108">W przypadku szczegółowych informacji związanych z programowaniem można zobaczyć [mikrousługi platformy .NET: architektura dla Zakontenerów aplikacji .NET](../microservices/index.md) i powiązanych z nią aplikacji referencyjnych [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="db0d1-108">For low-level, development-related details you can see the [.NET Microservices: Architecture for Containerized .NET Applications](../microservices/index.md) guide and it related reference application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="db0d1-109">Wyślij nam swoją opinię!</span><span class="sxs-lookup"><span data-stu-id="db0d1-109">Send us your feedback!</span></span>

<span data-ttu-id="db0d1-110">Utworzyliśmy ten przewodnik, aby ułatwić zrozumienie architektury aplikacji i mikrousług w programie .NET.</span><span class="sxs-lookup"><span data-stu-id="db0d1-110">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="db0d1-111">Przewodnik i powiązana aplikacja referencyjna będą rozwijane, więc będziemy nam powitać Twoją opinię.</span><span class="sxs-lookup"><span data-stu-id="db0d1-111">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="db0d1-112">Jeśli masz komentarze dotyczące tego, jak można ulepszyć ten przewodnik, Prześlij opinię na temat <https://aka.ms/ebookfeedback> .</span><span class="sxs-lookup"><span data-stu-id="db0d1-112">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="db0d1-113">Środki</span><span class="sxs-lookup"><span data-stu-id="db0d1-113">Credits</span></span>

<span data-ttu-id="db0d1-114">Autor:</span><span class="sxs-lookup"><span data-stu-id="db0d1-114">Author:</span></span>

> <span data-ttu-id="db0d1-115">**Cesar de La Torre**, SR. PM, zespół produktu .NET, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="db0d1-115">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>

<span data-ttu-id="db0d1-116">Edytor pozyskiwania:</span><span class="sxs-lookup"><span data-stu-id="db0d1-116">Acquisitions Editor:</span></span>

> <span data-ttu-id="db0d1-117">**Janine Patryk**</span><span class="sxs-lookup"><span data-stu-id="db0d1-117">**Janine Patrick**</span></span>

<span data-ttu-id="db0d1-118">Edytor programistyczny:</span><span class="sxs-lookup"><span data-stu-id="db0d1-118">Developmental Editor:</span></span>

> <span data-ttu-id="db0d1-119">**Robert Russell**, Solutions Professional w firmie Microsoft</span><span class="sxs-lookup"><span data-stu-id="db0d1-119">**Bob Russell**, Solutions Professional at Microsoft</span></span>
>
> [<span data-ttu-id="db0d1-120">**Publikacja ósemkowa, Inc.**</span><span class="sxs-lookup"><span data-stu-id="db0d1-120">**Octal Publishing, Inc.**</span></span>](http://www.octalpub.com/)

<span data-ttu-id="db0d1-121">Produkcja redakcyjna:</span><span class="sxs-lookup"><span data-stu-id="db0d1-121">Editorial Production:</span></span>

> [<span data-ttu-id="db0d1-122">Dianne Russell</span><span class="sxs-lookup"><span data-stu-id="db0d1-122">Dianne Russell</span></span>](http://www.octalpub.com/)
>
> <span data-ttu-id="db0d1-123">**Publikacja ósemkowa, Inc.**</span><span class="sxs-lookup"><span data-stu-id="db0d1-123">**Octal Publishing, Inc.**</span></span>

<span data-ttu-id="db0d1-124">Copyeditor:</span><span class="sxs-lookup"><span data-stu-id="db0d1-124">Copyeditor:</span></span>

> <span data-ttu-id="db0d1-125">**Robert Russell**, Solutions Professional w firmie Microsoft</span><span class="sxs-lookup"><span data-stu-id="db0d1-125">**Bob Russell**, Solutions Professional at Microsoft</span></span>

<span data-ttu-id="db0d1-126">Uczestnicy i recenzenci:</span><span class="sxs-lookup"><span data-stu-id="db0d1-126">Participants and reviewers:</span></span>

> <span data-ttu-id="db0d1-127">**Nish Anil**, SR. Program Manager, .NET Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="db0d1-127">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="db0d1-128">**Miguel Veloso**, inżynier ds. opracowywania oprogramowania z zwykłymi pojęciami</span><span class="sxs-lookup"><span data-stu-id="db0d1-128">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="db0d1-129">**Sumit Ghosh**, główny konsultant w firmie Neudesic</span><span class="sxs-lookup"><span data-stu-id="db0d1-129">**Sumit Ghosh**, Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="db0d1-130">Prawa autorskie</span><span class="sxs-lookup"><span data-stu-id="db0d1-130">Copyright</span></span>

<span data-ttu-id="db0d1-131">OPUBLIKOWANA PRZEZ</span><span class="sxs-lookup"><span data-stu-id="db0d1-131">PUBLISHED BY</span></span>

<span data-ttu-id="db0d1-132">Dział deweloperów firmy Microsoft, zespoły produktów .NET i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="db0d1-132">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="db0d1-133">Dział firmy Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="db0d1-133">A division of Microsoft Corporation</span></span>

<span data-ttu-id="db0d1-134">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="db0d1-134">One Microsoft Way</span></span>

<span data-ttu-id="db0d1-135">Redmond, Waszyngton 98052-6399</span><span class="sxs-lookup"><span data-stu-id="db0d1-135">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="db0d1-136">Copyright &copy; 2020 od firmy Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="db0d1-136">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="db0d1-137">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="db0d1-137">All rights reserved.</span></span> <span data-ttu-id="db0d1-138">Żadna część zawartości tej księgi nie może być odtwarzana ani przekazywana w żadnej formie ani za pomocą jakichkolwiek środków bez zgody na wydawcę.</span><span class="sxs-lookup"><span data-stu-id="db0d1-138">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="db0d1-139">Ta książka jest świadczona w postaci "AS-IS" i zawiera widoki i opinie autora.</span><span class="sxs-lookup"><span data-stu-id="db0d1-139">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="db0d1-140">Widoki, opinie i informacje wyrażone w tej książce, w tym adresy URL i inne odwołania do witryn internetowych, mogą ulec zmianie bez powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="db0d1-140">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="db0d1-141">Niektóre z przykładów przedstawiono wyłącznie do celów informacyjnych i są one fikcyjne.</span><span class="sxs-lookup"><span data-stu-id="db0d1-141">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="db0d1-142">Żadne rzeczywiste skojarzenia lub związki nie są zamierzone ani wnioskowane.</span><span class="sxs-lookup"><span data-stu-id="db0d1-142">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="db0d1-143">Firma Microsoft i znaki towarowe wymienione na <https://www.microsoft.com> stronie "znaki towarowe" są znakami towarowymi grupy firm Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db0d1-143">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="db0d1-144">Komputery Mac i macOS są znakami towarowymi firmy Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="db0d1-144">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="db0d1-145">Logo Docker Whale jest zastrzeżonym znakiem towarowym platformy Docker, Inc. używanym przez uprawnienie.</span><span class="sxs-lookup"><span data-stu-id="db0d1-145">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="db0d1-146">Wszystkie inne znaczniki i logo są własnością odpowiednich właścicieli.</span><span class="sxs-lookup"><span data-stu-id="db0d1-146">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="db0d1-147">Dalej</span><span class="sxs-lookup"><span data-stu-id="db0d1-147">Next</span></span>](introduction-to-containers-and-docker.md)
