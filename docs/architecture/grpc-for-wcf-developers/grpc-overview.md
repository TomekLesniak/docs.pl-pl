---
title: Omówienie gRPC-gRPC dla deweloperów programu WCF
description: Dowiedz się więcej na temat zestawu zasad dotyczących opracowywania gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: b372cc9dcdb2efd605b3d9b688513e4ff8530b01
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184443"
---
# <a name="grpc-overview"></a><span data-ttu-id="4f4a9-103">gRPC — Omówienie</span><span class="sxs-lookup"><span data-stu-id="4f4a9-103">gRPC overview</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="4f4a9-104">Po przejrzeniu Genesis zarówno programu WCF, jak i gRPC w ostatnim rozdziale, ten rozdział będzie uwzględniać niektóre kluczowe funkcje gRPC i porównać je z programem WCF.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-104">After looking at the genesis of both WCF and gRPC in the last chapter, this chapter will consider some of the key features of gRPC and how they compare to WCF.</span></span>

<span data-ttu-id="4f4a9-105">ASP.NET Core 3,0 to pierwsza wersja ASP.NET, która natywnie obsługuje gRPC jako obywatel pierwszej klasy, a firma Microsoft Teams uczestniczy w oficjalnej implementacji platformy .NET gRPC.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-105">ASP.NET Core 3.0 is the first release of ASP.NET that natively supports gRPC as a first-class citizen, with Microsoft teams contributing to the official .NET implementation of gRPC.</span></span> <span data-ttu-id="4f4a9-106">Zaleca się, aby najlepszym podejściem do kompilowania aplikacji rozproszonych za pomocą platformy .NET było współdziałanie ze wszystkimi innymi głównymi językami programowania i strukturami.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-106">It's recommended as the best approach for building distributed applications with .NET that can interoperate with all other major programming languages and frameworks.</span></span>

## <a name="key-principles"></a><span data-ttu-id="4f4a9-107">Podstawowe zasady</span><span class="sxs-lookup"><span data-stu-id="4f4a9-107">Key principles</span></span>

<span data-ttu-id="4f4a9-108">Jak zostało to omówione w rozdziale 1, firma Google chciała wykorzystać wprowadzenie protokołu HTTP/2 do współdziałania stubby, jego wewnętrznej infrastruktury usługi RPC ogólnego przeznaczenia.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-108">As discussed in chapter 1, Google wanted to use the introduction of HTTP/2 to rework Stubby, its internal, general purpose RPC infrastructure.</span></span> <span data-ttu-id="4f4a9-109">Stubby, zmieniono nazwę gRPC, teraz może wykorzystać standaryzację i spowodować jej zastosowanie do przetwarzania przenośnego, chmury i Internet rzeczy.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-109">Stubby, renamed gRPC, now could take advantage of standardization and would extend its applicability to mobile computing, the cloud, and the Internet of Things.</span></span>

<span data-ttu-id="4f4a9-110">Aby to osiągnąć, w [chmurze Native Computing Foundation (CNCF)](https://www.cncf.io/) ustanowiono zestaw zasad, które mogłyby zarządzać gRPC.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-110">To achieve this, the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) established a set of principles that would govern gRPC.</span></span> <span data-ttu-id="4f4a9-111">Na poniższej liście przedstawiono najbardziej odpowiednie, te, które zostały głównie objęte maksymalizacją dostępności i użyteczność:</span><span class="sxs-lookup"><span data-stu-id="4f4a9-111">The following list shows the most relevant ones, which are mainly concerned with maximizing accessibility and usability:</span></span>

- <span data-ttu-id="4f4a9-112">**Bezpłatna i otwarta** — wszystkie artefakty powinny być otwarte w ramach licencjonowania, które nie ograniczają deweloperom przyjmowania gRPC.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-112">**Free and open** – all artifacts should be open source with licensing that doesn't constrain developers from adopting gRPC.</span></span>
- <span data-ttu-id="4f4a9-113">**Zakres i prostota** — gRPC powinna być dostępna dla każdej popularnej platformy i jest wystarczająco prosta do kompilowania na dowolnej platformie.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-113">**Coverage and simplicity** – gRPC should be available across every popular platform and simple enough to build on any platform.</span></span>
- <span data-ttu-id="4f4a9-114">**Współdziałanie i zasięg** — powinno być możliwe korzystanie z gRPC w dowolnej sieci, niezależnie od przepustowości lub opóźnienia, przy użyciu powszechnie dostępnych standardów sieci.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-114">**Interoperability and reach** – it should be possible to use gRPC on any network, regardless of bandwidth or latency, using widely available network standards.</span></span>
- <span data-ttu-id="4f4a9-115">**Ogólnego przeznaczenia i wykonywania** — struktura powinna być użyteczna w szerokim zakresie przypadków użycia bez kompromisu wydajności.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-115">**General purpose and performant** – the framework should be usable by as broad a range of use-cases as possible without compromising performance.</span></span>
- <span data-ttu-id="4f4a9-116">**Przesyłanie strumieniowe** — protokół powinien udostępniać semantykę przesyłania strumieniowego dla dużych zestawów danych lub asynchronicznej obsługi komunikatów.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-116">**Streaming** – the protocol should provide streaming semantics for large data-sets or asynchronous messaging.</span></span>
- <span data-ttu-id="4f4a9-117">**Wymiana metadanych** — protokół zezwala na obsługę danych nienależących do firmy, takich jak tokeny uwierzytelniania, niezależnie od rzeczywistych danych firmy.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-117">**Metadata exchange** – the protocol allow non-business data, such as authentication tokens, to be handled separately from actual business data.</span></span>
- <span data-ttu-id="4f4a9-118">**Standardowe kody Stanów** — zmienność kodów błędów powinna być zredukowana, aby umożliwić bardziej przejrzyste podejmowanie decyzji o obsłudze błędów oraz, gdy wymagana jest dodatkowa obsługa błędów, należy zapewnić mechanizm zarządzania w ramach wymiany metadanych.</span><span class="sxs-lookup"><span data-stu-id="4f4a9-118">**Standardized status codes** – the variability of error codes should be reduced to make error handling decisions clearer and, where additional richer error handling is required, a mechanism should be provided for managing this within the metadata exchange.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4f4a9-119">[Poprzedni](introduction.md)
>[Następny](approach.md)</span><span class="sxs-lookup"><span data-stu-id="4f4a9-119">[Previous](introduction.md)
[Next](approach.md)</span></span>