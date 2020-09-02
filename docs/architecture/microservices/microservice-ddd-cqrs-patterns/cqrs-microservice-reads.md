---
title: Implementowanie odczytów i zapytań w mikrousłudze CQRS
description: Architektura mikrousług platformy .NET dla aplikacji platformy .NET w kontenerze | Zapoznaj się z implementacją zapytania CQRS na mikrousłudze porządkowania w eShopOnContainers przy użyciu Dapper.
ms.date: 10/08/2018
ms.openlocfilehash: 41932122326cf4c49b9c9e2c344d2ac17da7466b
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "89358898"
---
# <a name="implement-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="46ad2-103">Implementowanie operacji odczytu/zapytań w CQRS mikrousługi</span><span class="sxs-lookup"><span data-stu-id="46ad2-103">Implement reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="46ad2-104">W przypadku operacji odczytu/zapytań, mikrousługa porządkowania z aplikacji referencyjnej eShopOnContainers implementuje zapytania niezależnie od modelu DDD i obszaru transakcyjnego.</span><span class="sxs-lookup"><span data-stu-id="46ad2-104">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="46ad2-105">Zostało to zrobione przede wszystkim dlatego, że wymagania dotyczące zapytań i transakcji są znacząco inne.</span><span class="sxs-lookup"><span data-stu-id="46ad2-105">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="46ad2-106">Zapisuje transakcje wykonania, które muszą być zgodne z logiką domeny.</span><span class="sxs-lookup"><span data-stu-id="46ad2-106">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="46ad2-107">Zapytania, z drugiej strony, są idempotentne i mogą być segregowane z reguł domeny.</span><span class="sxs-lookup"><span data-stu-id="46ad2-107">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="46ad2-108">Podejście jest proste, jak pokazano na rysunku 7-3.</span><span class="sxs-lookup"><span data-stu-id="46ad2-108">The approach is simple, as shown in Figure 7-3.</span></span> <span data-ttu-id="46ad2-109">Interfejs API jest implementowany przez kontrolery interfejsu API sieci Web przy użyciu dowolnej infrastruktury, takiej jak relacyjne mapowanie mikroobiektu (ORM), takie jak Dapper, i zwracanie dynamicznego modele widoków w zależności od potrzeb aplikacji interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="46ad2-109">The API interface is implemented by the Web API controllers using any infrastructure, such as a micro Object Relational Mapper (ORM) like Dapper, and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![Diagram przedstawiający zapytania wysokiego poziomu — po stronie uproszczonej CQRS.](./media/cqrs-microservice-reads/simple-approach-cqrs-queries.png)

<span data-ttu-id="46ad2-111">**Rysunek 7-3**.</span><span class="sxs-lookup"><span data-stu-id="46ad2-111">**Figure 7-3**.</span></span> <span data-ttu-id="46ad2-112">Najprostszym podejściem do wykonywania zapytań w mikrousłudze CQRS</span><span class="sxs-lookup"><span data-stu-id="46ad2-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="46ad2-113">Najprostszym podejściem dla zapytań w uproszczone podejście CQRS można zaimplementować, wykonując zapytania do bazy danych za pomocą mikroorm, takiego jak Dapper, zwracając dynamiczny modele widoków.</span><span class="sxs-lookup"><span data-stu-id="46ad2-113">The simplest approach for the queries-side in a simplified CQRS approach can be implemented by querying the database with a Micro-ORM like Dapper, returning dynamic ViewModels.</span></span> <span data-ttu-id="46ad2-114">Definicje zapytania zapytania do bazy danych i zwracają dynamiczny ViewModel zbudowany na bieżąco dla każdego zapytania.</span><span class="sxs-lookup"><span data-stu-id="46ad2-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="46ad2-115">Ponieważ zapytania są idempotentne, nie zmieniają danych niezależnie od tego, ile razy zostało uruchomione zapytanie.</span><span class="sxs-lookup"><span data-stu-id="46ad2-115">Since the queries are idempotent, they won't change the data no matter how many times you run a query.</span></span> <span data-ttu-id="46ad2-116">W związku z tym nie trzeba ograniczać się przez żaden wzorzec DDD używany w stronie transakcyjnej, taki jak agregacje i inne wzorce, a także to, dlaczego zapytania są oddzielone od obszaru transakcyjnego.</span><span class="sxs-lookup"><span data-stu-id="46ad2-116">Therefore, you don't need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="46ad2-117">Kwerenda bazy danych wymaga danych, które są wymagane przez interfejs użytkownika i zwracają dynamiczny ViewModel, który nie musi być statycznie zdefiniowany w dowolnym miejscu (brak klas dla modele widoków), z wyjątkiem samych instrukcji SQL.</span><span class="sxs-lookup"><span data-stu-id="46ad2-117">You query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="46ad2-118">Ponieważ takie podejście jest proste, kod wymagany dla strony zapytania (na przykład kod korzystający z mikroorm like [Dapper](https://github.com/StackExchange/Dapper)) można zaimplementować [w ramach tego samego projektu interfejsu API sieci Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span><span class="sxs-lookup"><span data-stu-id="46ad2-118">Since this approach is simple, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="46ad2-119">Przedstawiono to na rysunku 7-4.</span><span class="sxs-lookup"><span data-stu-id="46ad2-119">Figure 7-4 shows this.</span></span> <span data-ttu-id="46ad2-120">Zapytania są definiowane w projekcie **porządkowania. API** mikrousług w ramach rozwiązania eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="46ad2-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![Zrzut ekranu przedstawiający folder zapytania projektu porządkowania. API.](./media/cqrs-microservice-reads/ordering-api-queries-folder.png)

<span data-ttu-id="46ad2-122">**Rysunek 7-4**.</span><span class="sxs-lookup"><span data-stu-id="46ad2-122">**Figure 7-4**.</span></span> <span data-ttu-id="46ad2-123">Zapytania w mikrousłudze porządkowania w eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="46ad2-123">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="use-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="46ad2-124">Używaj modele widoków określonych dla aplikacji klienckich, niezależnie od ograniczeń modelu domeny</span><span class="sxs-lookup"><span data-stu-id="46ad2-124">Use ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="46ad2-125">Ponieważ zapytania są wykonywane w celu uzyskania danych wymaganych przez aplikacje klienckie, zwracany typ może być przeznaczony dla klientów na podstawie danych zwróconych przez zapytania.</span><span class="sxs-lookup"><span data-stu-id="46ad2-125">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="46ad2-126">Te modele lub Transfer danych obiekty (DTO) są nazywane modele widoków.</span><span class="sxs-lookup"><span data-stu-id="46ad2-126">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="46ad2-127">Zwrócone dane (ViewModel) mogą wynikać z dołączania danych z wielu jednostek lub tabel w bazie danych, a nawet wielu agregacji zdefiniowanych w modelu domeny dla obszaru transakcyjnego.</span><span class="sxs-lookup"><span data-stu-id="46ad2-127">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="46ad2-128">W tym przypadku, ponieważ tworzysz zapytania niezależnie od modelu domeny, granice zagregowane i ograniczenia są ignorowane i można wysyłać zapytania do dowolnej tabeli i kolumny, które mogą być potrzebne.</span><span class="sxs-lookup"><span data-stu-id="46ad2-128">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are ignored and you're free to query any table and column you might need.</span></span> <span data-ttu-id="46ad2-129">Takie podejście zapewnia dużą elastyczność i produktywność dla deweloperów tworzących lub aktualizujących zapytania.</span><span class="sxs-lookup"><span data-stu-id="46ad2-129">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="46ad2-130">Modele widoków mogą być typami statycznymi zdefiniowanymi w klasach (zgodnie z implementacją mikrousługi porządkowania).</span><span class="sxs-lookup"><span data-stu-id="46ad2-130">The ViewModels can be static types defined in classes (as is implemented in the ordering microservice).</span></span> <span data-ttu-id="46ad2-131">Lub mogą być tworzone dynamicznie na podstawie wykonanych zapytań, które są bardzo elastyczne dla deweloperów.</span><span class="sxs-lookup"><span data-stu-id="46ad2-131">Or they can be created dynamically based on the queries performed, which is very agile for developers.</span></span>

## <a name="use-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="46ad2-132">Używanie Dapper jako mikroorm do wykonywania zapytań</span><span class="sxs-lookup"><span data-stu-id="46ad2-132">Use Dapper as a micro ORM to perform queries</span></span>

<span data-ttu-id="46ad2-133">Do wykonywania zapytań można użyć dowolnego mikroorm, Entity Framework Core lub nawet zwykłego ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="46ad2-133">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="46ad2-134">W przykładowej aplikacji Dapper został wybrany dla mikrousługi porządkowania w eShopOnContainers jako dobry przykład popularnego mikroorm.</span><span class="sxs-lookup"><span data-stu-id="46ad2-134">In the sample application, Dapper was selected for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="46ad2-135">Może uruchamiać zwykłe zapytania SQL o doskonałej wydajności, ponieważ jest to platforma uproszczona.</span><span class="sxs-lookup"><span data-stu-id="46ad2-135">It can run plain SQL queries with great performance, because it's a light framework.</span></span> <span data-ttu-id="46ad2-136">Za pomocą Dapper można napisać zapytanie SQL, które może uzyskać dostęp do wielu tabel i dołączyć do nich.</span><span class="sxs-lookup"><span data-stu-id="46ad2-136">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="46ad2-137">Dapper to projekt typu "open source" (oryginalny utworzony przez sam Saffron) i jest częścią bloków konstrukcyjnych używanych w [Stack Overflow](https://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="46ad2-137">Dapper is an open-source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="46ad2-138">Aby korzystać z Dapper, wystarczy zainstalować go za pomocą [pakietu NuGet Dapper](https://www.nuget.org/packages/Dapper), jak pokazano na poniższym rysunku:</span><span class="sxs-lookup"><span data-stu-id="46ad2-138">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure:</span></span>

![Zrzut ekranu przedstawiający pakiet Dapper w widoku pakiety NuGet.](./media/cqrs-microservice-reads/drapper-package-nuget.png)

<span data-ttu-id="46ad2-140">Należy również dodać `using` dyrektywę, aby kod miał dostęp do metod rozszerzenia Dapper.</span><span class="sxs-lookup"><span data-stu-id="46ad2-140">You also need to add a `using` directive so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="46ad2-141">Gdy używasz Dapper w kodzie, możesz bezpośrednio użyć <xref:System.Data.SqlClient.SqlConnection> klasy dostępnej w <xref:System.Data.SqlClient> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="46ad2-141">When you use Dapper in your code, you directly use the <xref:System.Data.SqlClient.SqlConnection> class available in the <xref:System.Data.SqlClient> namespace.</span></span> <span data-ttu-id="46ad2-142">Za pomocą metody QueryAsync i innych metod rozszerzających, które rozszerzają <xref:System.Data.SqlClient.SqlConnection> klasę, można uruchamiać zapytania w sposób prosty i wydajny.</span><span class="sxs-lookup"><span data-stu-id="46ad2-142">Through the QueryAsync method and other extension methods that extend the <xref:System.Data.SqlClient.SqlConnection> class, you can run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-versus-static-viewmodels"></a><span data-ttu-id="46ad2-143">Dynamiczny a statyczny modele widoków</span><span class="sxs-lookup"><span data-stu-id="46ad2-143">Dynamic versus static ViewModels</span></span>

<span data-ttu-id="46ad2-144">Po powrocie modele widoków z serwera do aplikacji klienckich można myśleć o tych modele widoków jako DTO (Transfer danych obiektów), które mogą być różne dla wewnętrznych jednostek domeny modelu jednostki, ponieważ modele widoków przechowuje dane w sposób potrzeb aplikacji klienta.</span><span class="sxs-lookup"><span data-stu-id="46ad2-144">When returning ViewModels from the server-side to client apps, you can think about those ViewModels as DTOs (Data Transfer Objects) that can be different to the internal domain entities of your entity model because the ViewModels hold the data the way the client app needs.</span></span> <span data-ttu-id="46ad2-145">Z tego względu w wielu przypadkach można agregować dane pochodzące z wielu jednostek domeny i precyzyjnie redagować modele widoków według sposobu, w jaki aplikacja kliencka wymaga tych danych.</span><span class="sxs-lookup"><span data-stu-id="46ad2-145">Therefore, in many cases, you can aggregate data coming from multiple domain entities and compose the ViewModels precisely according to how the client app needs that data.</span></span>

<span data-ttu-id="46ad2-146">Te modele widoków lub DTO mogą być zdefiniowane jawnie (jako klasy posiadaczy danych), takie jak `OrderSummary` Klasa pokazana w późniejszym fragmencie kodu.</span><span class="sxs-lookup"><span data-stu-id="46ad2-146">Those ViewModels or DTOs can be defined explicitly (as data holder classes), like the `OrderSummary` class shown in a later code snippet.</span></span> <span data-ttu-id="46ad2-147">Lub można po prostu zwrócić dynamiczny modele widoków lub dynamiczny DTO na podstawie atrybutów zwracanych przez zapytania jako typ dynamiczny.</span><span class="sxs-lookup"><span data-stu-id="46ad2-147">Or, you could just return dynamic ViewModels or dynamic DTOs based on the attributes returned by your queries as a dynamic type.</span></span>

### <a name="viewmodel-as-dynamic-type"></a><span data-ttu-id="46ad2-148">ViewModel jako typ dynamiczny</span><span class="sxs-lookup"><span data-stu-id="46ad2-148">ViewModel as dynamic type</span></span>

<span data-ttu-id="46ad2-149">Jak pokazano w poniższym kodzie, `ViewModel` można zwrócić bezpośrednio przez zapytania, zwracając typ *dynamiczny* , który wewnętrznie jest oparty na atrybutach zwracanych przez zapytanie.</span><span class="sxs-lookup"><span data-stu-id="46ad2-149">As shown in the following code, a `ViewModel` can be directly returned by the queries by just returning a *dynamic* type that internally is based on the attributes returned by a query.</span></span> <span data-ttu-id="46ad2-150">Oznacza to, że podzbiór atrybutów do zwrócenia jest oparty na zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="46ad2-150">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="46ad2-151">W związku z tym, jeśli dodasz nową kolumnę do zapytania lub sprzężenia, dane te są dynamicznie dodawane do zwracanego `ViewModel` .</span><span class="sxs-lookup"><span data-stu-id="46ad2-151">Therefore, if you add a new column to the query or join, that data is dynamically added to the returned `ViewModel`.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
                @"SELECT o.[Id] as ordernumber,
                o.[OrderDate] as [date],os.[Name] as [status],
                SUM(oi.units*oi.unitprice) as total
                FROM [ordering].[Orders] o
                LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
                LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
    }
}
```

<span data-ttu-id="46ad2-152">Ważnym punktem jest to, że za pomocą typu dynamicznego, zwrócona kolekcja danych jest dynamicznie zmontowany jako ViewModel.</span><span class="sxs-lookup"><span data-stu-id="46ad2-152">The important point is that by using a dynamic type, the returned collection of data is dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="46ad2-153">**Specjaliści:** Takie podejście zmniejsza konieczność modyfikacji statycznych klas ViewModel za każdym razem, gdy aktualizujesz zdanie SQL zapytania, dzięki czemu ten podejście projektowe jest elastyczne podczas kodowania, bezpośrednie i szybkiej ewolucji w odniesieniu do przyszłych zmian.</span><span class="sxs-lookup"><span data-stu-id="46ad2-153">**Pros:** This approach reduces the need to modify static ViewModel classes whenever you update the SQL sentence of a query, making this design approach agile when coding, straightforward, and quick to evolve in regard to future changes.</span></span>

<span data-ttu-id="46ad2-154">**Wady:** W długim okresie typy dynamiczne mogą mieć negatywny wpływ na przejrzystość i zgodność usługi z aplikacjami klienckimi.</span><span class="sxs-lookup"><span data-stu-id="46ad2-154">**Cons:** In the long term, dynamic types can negatively impact the clarity and the compatibility of a service with client apps.</span></span> <span data-ttu-id="46ad2-155">Ponadto oprogramowanie pośredniczące, takie jak Swashbuckle, nie może zapewnić tego samego poziomu dokumentacji dla zwracanych typów, jeśli są używane typy dynamiczne.</span><span class="sxs-lookup"><span data-stu-id="46ad2-155">In addition, middleware software like Swashbuckle cannot provide the same level of documentation on returned types if using dynamic types.</span></span>

### <a name="viewmodel-as-predefined-dto-classes"></a><span data-ttu-id="46ad2-156">ViewModel jako wstępnie zdefiniowane klasy DTO</span><span class="sxs-lookup"><span data-stu-id="46ad2-156">ViewModel as predefined DTO classes</span></span>

<span data-ttu-id="46ad2-157">**Specjaliści**: posiadanie statycznych, wstępnie zdefiniowanych klas ViewModel, takich jak "kontrakty", opartych na jawnych klasach DTO, jest w pełni lepszym rozwiązaniem dla publicznych interfejsów API, ale również dla mikrousług, nawet jeśli są one używane tylko przez tę samą aplikację.</span><span class="sxs-lookup"><span data-stu-id="46ad2-157">**Pros**: Having static, predefined ViewModel classes, like "contracts" based on explicit DTO classes, is definitely better for public APIs but also for long-term microservices, even if they are only used by the same application.</span></span>

<span data-ttu-id="46ad2-158">Jeśli chcesz określić typy odpowiedzi dla struktury Swagger, musisz użyć jawnych klas DTO jako typu zwracanego.</span><span class="sxs-lookup"><span data-stu-id="46ad2-158">If you want to specify response types for Swagger, you need to use explicit DTO classes as the return type.</span></span> <span data-ttu-id="46ad2-159">W związku z tym wstępnie zdefiniowane klasy DTO umożliwiają oferowanie bardziej szczegółowych informacji z struktury Swagger.</span><span class="sxs-lookup"><span data-stu-id="46ad2-159">Therefore, predefined DTO classes allow you to offer richer information from Swagger.</span></span> <span data-ttu-id="46ad2-160">Poprawia to dokumentację interfejsu API i zgodność przy korzystaniu z interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="46ad2-160">That improves the API documentation and compatibility when consuming an API.</span></span>

<span data-ttu-id="46ad2-161">**Wady**: jak wspomniano wcześniej, podczas aktualizowania kodu należy wykonać kilka kroków, aby zaktualizować klasy DTO.</span><span class="sxs-lookup"><span data-stu-id="46ad2-161">**Cons**: As mentioned earlier, when updating the code, it takes some more steps to update the DTO classes.</span></span>

<span data-ttu-id="46ad2-162">*Porada oparta na naszym doświadczeniu*: w zapytaniach zaimplementowanych w mikrousłudze porządkowania w programie eShopOnContainers rozpoczynamy Programowanie przy użyciu dynamicznych modele widoków, ponieważ było to proste i elastyczne na wczesnych etapach tworzenia.</span><span class="sxs-lookup"><span data-stu-id="46ad2-162">*Tip based on our experience*: In the queries implemented at the Ordering microservice in eShopOnContainers, we started developing by using dynamic ViewModels as it was straightforward and agile on the early development stages.</span></span> <span data-ttu-id="46ad2-163">Jednak po ustabilizowaniu rozwoju wybieramy do refaktoryzacji interfejsy API i używają statycznego lub wstępnie zdefiniowanego DTO dla modele widoków, ponieważ jest to wyraźniejsze dla konsumentów mikrousług, aby znać jawne typy DTO, używane jako "kontrakty".</span><span class="sxs-lookup"><span data-stu-id="46ad2-163">But, once the development was stabilized, we chose to refactor the APIs and use static or pre-defined DTOs for the ViewModels, because it is clearer for the microservice's consumers to know explicit DTO types, used as "contracts".</span></span>

<span data-ttu-id="46ad2-164">W poniższym przykładzie można zobaczyć, jak zapytanie zwraca dane przy użyciu jawnej klasy ViewModel DTO: klasy OrderSummary.</span><span class="sxs-lookup"><span data-stu-id="46ad2-164">In the following example, you can see how the query is returning data by using an explicit ViewModel DTO class: the OrderSummary class.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
  public async Task<IEnumerable<OrderSummary>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<OrderSummary>(
                  @"SELECT o.[Id] as ordernumber,
                  o.[OrderDate] as [date],os.[Name] as [status],
                  SUM(oi.units*oi.unitprice) as total
                  FROM [ordering].[Orders] o
                  LEFT JOIN[ordering].[orderitems] oi ON  o.Id = oi.orderid
                  LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                  GROUP BY o.[Id], o.[OrderDate], os.[Name]
                  ORDER BY o.[Id]");
        }
    }
}
```

#### <a name="describe-response-types-of-web-apis"></a><span data-ttu-id="46ad2-165">Opisywanie typów odpowiedzi interfejsów API sieci Web</span><span class="sxs-lookup"><span data-stu-id="46ad2-165">Describe response types of Web APIs</span></span>

<span data-ttu-id="46ad2-166">Deweloperzy korzystający z interfejsów API sieci Web i mikrousług są najbardziej zainteresowani tym, co jest zwracane — w szczególności typy odpowiedzi i kody błędów (jeśli nie są standardem).</span><span class="sxs-lookup"><span data-stu-id="46ad2-166">Developers consuming web APIs and microservices are most concerned with what is returned—specifically response types and error codes (if not standard).</span></span> <span data-ttu-id="46ad2-167">Typy odpowiedzi są obsługiwane w komentarzach XML i adnotacjach danych.</span><span class="sxs-lookup"><span data-stu-id="46ad2-167">The response types are handled in the XML comments and data annotations.</span></span>

<span data-ttu-id="46ad2-168">Bez odpowiedniej dokumentacji w interfejsie użytkownika programu Swagger klient nie ma wiedzy na temat typów zwracanych lub kodów HTTP, które mogą być zwracane.</span><span class="sxs-lookup"><span data-stu-id="46ad2-168">Without proper documentation in the Swagger UI, the consumer lacks knowledge of what types are being returned or what HTTP codes can be returned.</span></span> <span data-ttu-id="46ad2-169">Ten problem został rozwiązany przez dodanie <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType> , więc Swashbuckle może generować bogatsze informacje o modelu i wartościach zwracanych przez interfejs API, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="46ad2-169">That problem is fixed by adding the <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, so Swashbuckle can generate richer information about the API return model and values, as shown in the following code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class OrdersController : Controller
    {
        //Additional code...
        [Route("")]
        [HttpGet]
        [ProducesResponseType(typeof(IEnumerable<OrderSummary>),
            (int)HttpStatusCode.OK)]
        public async Task<IActionResult> GetOrders()
        {
            var userid = _identityService.GetUserIdentity();
            var orders = await _orderQueries
                .GetOrdersFromUserAsync(Guid.Parse(userid));
            return Ok(orders);
        }
    }
}
```

<span data-ttu-id="46ad2-170">Jednak `ProducesResponseType` atrybut nie może używać elementu dynamicznego jako typu, ale wymaga użycia jawnych typów, takich jak `OrderSummary` ViewModel DTO, pokazany w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="46ad2-170">However, the `ProducesResponseType` attribute cannot use dynamic as a type but requires to use explicit types, like the `OrderSummary` ViewModel DTO, shown in the following example:</span></span>

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

<span data-ttu-id="46ad2-171">Jest to kolejny powód, dla którego jawne zwracane typy są lepsze niż typy dynamiczne w długim okresie.</span><span class="sxs-lookup"><span data-stu-id="46ad2-171">This is another reason why explicit returned types are better than dynamic types, in the long term.</span></span> <span data-ttu-id="46ad2-172">Przy użyciu `ProducesResponseType` atrybutu można także określić oczekiwany wynik w odniesieniu do możliwych błędów/kodów http, takich jak 200, 400 itd.</span><span class="sxs-lookup"><span data-stu-id="46ad2-172">When using the `ProducesResponseType` attribute, you can also specify what is the expected outcome in regards possible HTTP errors/codes, like 200, 400, etc.</span></span>

<span data-ttu-id="46ad2-173">Na poniższej ilustracji widać, jak interfejs użytkownika struktury Swagger wyświetla informacje o odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="46ad2-173">In the following image, you can see how Swagger UI shows the ResponseType information.</span></span>

![Zrzut ekranu przedstawiający stronę interfejsu użytkownika programu Swagger dla interfejsu API porządkowania.](./media/cqrs-microservice-reads/swagger-ordering-http-api.png)

<span data-ttu-id="46ad2-175">**Rysunek 7-5**.</span><span class="sxs-lookup"><span data-stu-id="46ad2-175">**Figure 7-5**.</span></span> <span data-ttu-id="46ad2-176">Interfejs użytkownika struktury Swagger pokazujący typy odpowiedzi i możliwe kody stanu HTTP z internetowego interfejsu API</span><span class="sxs-lookup"><span data-stu-id="46ad2-176">Swagger UI showing response types and possible HTTP status codes from a Web API</span></span>

<span data-ttu-id="46ad2-177">Obraz pokazuje kilka przykładowych wartości na podstawie typów ViewModel i możliwych kodów stanu HTTP, które mogą być zwracane.</span><span class="sxs-lookup"><span data-stu-id="46ad2-177">The image shows some example values based on the ViewModel types and the possible HTTP status codes that can be returned.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46ad2-178">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="46ad2-178">Additional resources</span></span>

- <span data-ttu-id="46ad2-179">**Dapper**</span><span class="sxs-lookup"><span data-stu-id="46ad2-179">**Dapper**</span></span>  
 <https://github.com/StackExchange/dapper-dot-net>

- <span data-ttu-id="46ad2-180">**Julie Lerman. Punkty danych — Dapper, Entity Framework i aplikacje hybrydowe (artykuł z magazynu MSDN)**</span><span class="sxs-lookup"><span data-stu-id="46ad2-180">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN magazine article)**</span></span>  
  <https://docs.microsoft.com/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps>

- <span data-ttu-id="46ad2-181">**ASP.NET Core stronach pomocy interfejsu API sieci Web przy użyciu programu Swagger**</span><span class="sxs-lookup"><span data-stu-id="46ad2-181">**ASP.NET Core Web API Help Pages using Swagger**</span></span>  
  <https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio>

>[!div class="step-by-step"]
><span data-ttu-id="46ad2-182">[Poprzedni](eshoponcontainers-cqrs-ddd-microservice.md) 
> [Dalej](ddd-oriented-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="46ad2-182">[Previous](eshoponcontainers-cqrs-ddd-microservice.md)
[Next](ddd-oriented-microservice.md)</span></span>
