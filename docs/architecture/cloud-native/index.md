---
title: Tworzenie architektury natywnych aplikacji .NET w chmurze dla platformy Azure
description: Przewodnik tworzenia aplikacji natywnych w chmurze wykorzystujących kontenery, mikrousługi i funkcje bezserwerowe platformy Azure.
author: ardalis
ms.date: 11/10/2020
ms.openlocfilehash: 673bfef27c3767f68b1c30d4383cee010ba377f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506652"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="67789-103">Tworzenie architektury natywnych aplikacji .NET w chmurze dla platformy Azure</span><span class="sxs-lookup"><span data-stu-id="67789-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![obraz okładki](./media/cover.png)

<span data-ttu-id="67789-105">**Wersja 1.0**</span><span class="sxs-lookup"><span data-stu-id="67789-105">**EDITION v1.0**</span></span>

<span data-ttu-id="67789-106">Odwołaj się do [dziennika zmian](https://aka.ms/cn-ebook-changelog) dotyczących aktualizacji książki i wkładów społecznościowych.</span><span class="sxs-lookup"><span data-stu-id="67789-106">Refer [changelog](https://aka.ms/cn-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="67789-107">OPUBLIKOWANA PRZEZ</span><span class="sxs-lookup"><span data-stu-id="67789-107">PUBLISHED BY</span></span>

<span data-ttu-id="67789-108">Zespoły deweloperów firmy Microsoft, .NET i Visual Studio</span><span class="sxs-lookup"><span data-stu-id="67789-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="67789-109">Dział firmy Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="67789-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="67789-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="67789-110">One Microsoft Way</span></span>

<span data-ttu-id="67789-111">Redmond, Waszyngton 98052-6399</span><span class="sxs-lookup"><span data-stu-id="67789-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="67789-112">Copyright &copy; 2020 od firmy Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="67789-112">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="67789-113">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="67789-113">All rights reserved.</span></span> <span data-ttu-id="67789-114">Żadna część zawartości tej księgi nie może być odtwarzana ani przekazywana w żadnej formie ani za pomocą jakichkolwiek środków bez zgody na wydawcę.</span><span class="sxs-lookup"><span data-stu-id="67789-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="67789-115">Ta książka jest świadczona w postaci "AS-IS" i zawiera widoki i opinie autora.</span><span class="sxs-lookup"><span data-stu-id="67789-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="67789-116">Widoki, opinie i informacje wyrażone w tej książce, w tym adresy URL i inne odwołania do witryn internetowych, mogą ulec zmianie bez powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="67789-116">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="67789-117">Niektóre z przykładów przedstawiono wyłącznie do celów informacyjnych i są one fikcyjne.</span><span class="sxs-lookup"><span data-stu-id="67789-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="67789-118">Żadne rzeczywiste skojarzenia lub związki nie są zamierzone ani wnioskowane.</span><span class="sxs-lookup"><span data-stu-id="67789-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="67789-119">Firma Microsoft i znaki towarowe wymienione na <https://www.microsoft.com> stronie "znaki towarowe" są znakami towarowymi grupy firm Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67789-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="67789-120">Komputery Mac i macOS są znakami towarowymi firmy Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="67789-120">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="67789-121">Logo Docker Whale jest zastrzeżonym znakiem towarowym platformy Docker, Inc. używanym przez uprawnienie.</span><span class="sxs-lookup"><span data-stu-id="67789-121">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="67789-122">Wszystkie inne znaczniki i logo są własnością odpowiednich właścicieli.</span><span class="sxs-lookup"><span data-stu-id="67789-122">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="67789-123">Autorów</span><span class="sxs-lookup"><span data-stu-id="67789-123">Authors:</span></span>

> <span data-ttu-id="67789-124">**Rob Vettor** , główny architekt systemu w chmurze/IP architekt- [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span><span class="sxs-lookup"><span data-stu-id="67789-124">**Rob Vettor** , Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="67789-125">**Steve "ardalis" Smith** , architekt oprogramowania i Trainer- [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="67789-125">**Steve "ardalis" Smith** , Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="67789-126">Uczestnicy i recenzenci:</span><span class="sxs-lookup"><span data-stu-id="67789-126">Participants and Reviewers:</span></span>

> <span data-ttu-id="67789-127">**Cesar de La Torre** , główny Menedżer programu, zespół .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="67789-127">**Cesar De la Torre** , Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="67789-128">**Nish Anil** , starszy kierownik ds. programów, .NET Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="67789-128">**Nish Anil** , Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="67789-129">**Jeremy Likness** , starszy kierownik ds. programów, .NET Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="67789-129">**Jeremy Likness** , Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="67789-130">**Cecil Phillip** , starszy ambasador w chmurze, Microsoft</span><span class="sxs-lookup"><span data-stu-id="67789-130">**Cecil Phillip** , Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="67789-131">Edytory</span><span class="sxs-lookup"><span data-stu-id="67789-131">Editors:</span></span>

> <span data-ttu-id="67789-132">**Maira Wenzel** , Menedżer programów, .NET Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="67789-132">**Maira Wenzel** , Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="67789-133">Wersja</span><span class="sxs-lookup"><span data-stu-id="67789-133">Version</span></span>

<span data-ttu-id="67789-134">Ten przewodnik został zapisany w celu uwzględnienia wersji **programu .NET Core 3,1** wraz z wieloma dodatkowymi aktualizacjami związanymi z tym samym "" Wave "technologiami (czyli platformą Azure i dodatkowymi technologiami innych firm), które są zgodne z wersją platformy .net Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="67789-134">This guide has been written to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="67789-135">Kto powinien korzystać z tego przewodnika</span><span class="sxs-lookup"><span data-stu-id="67789-135">Who should use this guide</span></span>

<span data-ttu-id="67789-136">Odbiorcy tego przewodnika są głównie deweloperzy, potencjalni klienci programistyczni i architektzy, którzy interesują się tworzeniem aplikacji przeznaczonych dla chmury.</span><span class="sxs-lookup"><span data-stu-id="67789-136">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="67789-137">Dodatkowymi odbiorcami są, którzy decydują o wyborze, czy kompilować aplikacje przy użyciu podejścia natywnego w chmurze.</span><span class="sxs-lookup"><span data-stu-id="67789-137">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="67789-138">Jak można użyć tego przewodnika</span><span class="sxs-lookup"><span data-stu-id="67789-138">How you can use this guide</span></span>

<span data-ttu-id="67789-139">Ten przewodnik rozpoczyna się od zdefiniowania natywnej chmury i wprowadzenia aplikacji referencyjnej skompilowanej przy użyciu zasad i technologii natywnych w chmurze.</span><span class="sxs-lookup"><span data-stu-id="67789-139">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="67789-140">Oprócz tych pierwszych dwóch rozdziałów pozostała część książki jest dzielona do określonych rozdziałów ukierunkowanych na tematy wspólne dla większości aplikacji natywnych w chmurze.</span><span class="sxs-lookup"><span data-stu-id="67789-140">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="67789-141">Możesz przejść do dowolnego z tych rozdziałów, aby dowiedzieć się więcej na temat podejścia natywnego w chmurze:</span><span class="sxs-lookup"><span data-stu-id="67789-141">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="67789-142">Dostęp do danych i danych</span><span class="sxs-lookup"><span data-stu-id="67789-142">Data and data access</span></span>
- <span data-ttu-id="67789-143">Wzorce komunikacji</span><span class="sxs-lookup"><span data-stu-id="67789-143">Communication patterns</span></span>
- <span data-ttu-id="67789-144">Skalowanie i skalowalność</span><span class="sxs-lookup"><span data-stu-id="67789-144">Scaling and scalability</span></span>
- <span data-ttu-id="67789-145">Odporność aplikacji</span><span class="sxs-lookup"><span data-stu-id="67789-145">Application resiliency</span></span>
- <span data-ttu-id="67789-146">Monitorowanie i kondycja</span><span class="sxs-lookup"><span data-stu-id="67789-146">Monitoring and health</span></span>
- <span data-ttu-id="67789-147">Obsługa tożsamości i zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="67789-147">Identity and security</span></span>
- <span data-ttu-id="67789-148">DevOps</span><span class="sxs-lookup"><span data-stu-id="67789-148">DevOps</span></span>

<span data-ttu-id="67789-149">Ten przewodnik jest dostępny zarówno w formacie [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) , jak i w trybie online.</span><span class="sxs-lookup"><span data-stu-id="67789-149">This guide is available both in [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) form and online.</span></span> <span data-ttu-id="67789-150">Możesz przesłać dalej ten dokument lub linki do swojej wersji online swojego zespołu, aby pomóc w zapewnieniu powszechnego poznania się z tymi tematami.</span><span class="sxs-lookup"><span data-stu-id="67789-150">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="67789-151">Większość z tych tematów korzysta ze spójnych zasad i wzorców, a także tych, których dotyczą decyzje związane z tymi tematami.</span><span class="sxs-lookup"><span data-stu-id="67789-151">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="67789-152">Naszym celem tego dokumentu jest wyposażenie zespołów i ich liderów z informacjami potrzebnymi do podejmowania świadomych decyzji o architekturze, programowaniu i hostingu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="67789-152">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="67789-153">Wyślij opinię</span><span class="sxs-lookup"><span data-stu-id="67789-153">Send your feedback</span></span>

<span data-ttu-id="67789-154">Ta książka i powiązane przykłady są ciągle zmieniane, dzięki czemu Twoje opinie są gotowe!</span><span class="sxs-lookup"><span data-stu-id="67789-154">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="67789-155">Jeśli masz komentarze dotyczące sposobu, w jaki można ulepszyć tę książkę, Skorzystaj z sekcji opinia w dolnej części strony utworzonej w witrynie [GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="67789-155">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="67789-156">Dalej</span><span class="sxs-lookup"><span data-stu-id="67789-156">Next</span></span>](introduction.md)
