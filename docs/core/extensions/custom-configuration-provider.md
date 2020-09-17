---
title: Implementowanie niestandardowego dostawcy konfiguracji w programie .NET
description: Dowiedz się, jak zaimplementować niestandardowego dostawcę konfiguracji w aplikacjach .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/16/2020
ms.topic: how-to
ms.openlocfilehash: 968bf202eeea32742444681260d5ab0b27b403f9
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720808"
---
# <a name="implement-a-custom-configuration-provider-in-net"></a><span data-ttu-id="a66de-103">Implementowanie niestandardowego dostawcy konfiguracji w programie .NET</span><span class="sxs-lookup"><span data-stu-id="a66de-103">Implement a custom configuration provider in .NET</span></span>

<span data-ttu-id="a66de-104">Istnieje wielu [dostawców konfiguracji](configuration-providers.md) dostępnych dla wspólnych źródeł konfiguracji, takich jak pliki JSON, XML i ini.</span><span class="sxs-lookup"><span data-stu-id="a66de-104">There are many [configuration providers](configuration-providers.md) available for common configuration sources such as JSON, XML, and INI files.</span></span> <span data-ttu-id="a66de-105">Może być konieczne zaimplementowanie niestandardowego dostawcy konfiguracji, gdy jeden z dostępnych dostawców nie odpowiada wymaganiom Twojej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a66de-105">You may need to implement a custom configuration provider when one of the available providers doesn't suit your application needs.</span></span> <span data-ttu-id="a66de-106">W tym artykule dowiesz się, jak zaimplementować niestandardowego dostawcę konfiguracji, który korzysta z bazy danych jako źródła konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a66de-106">In this article, you'll learn how to implement a custom configuration provider that relies on a database as its configuration source.</span></span>

## <a name="custom-configuration-provider"></a><span data-ttu-id="a66de-107">Niestandardowy dostawca konfiguracji</span><span class="sxs-lookup"><span data-stu-id="a66de-107">Custom configuration provider</span></span>

<span data-ttu-id="a66de-108">Przykładowa aplikacja pokazuje, jak utworzyć podstawowego dostawcę konfiguracji, który odczytuje pary klucz-wartość konfiguracji z bazy danych przy użyciu narzędzia [Entity Framework (EF) Core](/ef/core).</span><span class="sxs-lookup"><span data-stu-id="a66de-108">The sample app demonstrates how to create a basic configuration provider that reads configuration key-value pairs from a database using [Entity Framework (EF) Core](/ef/core).</span></span>

<span data-ttu-id="a66de-109">Dostawca ma następującą charakterystykę:</span><span class="sxs-lookup"><span data-stu-id="a66de-109">The provider has the following characteristics:</span></span>

- <span data-ttu-id="a66de-110">Baza danych EF w pamięci jest używana w celach demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="a66de-110">The EF in-memory database is used for demonstration purposes.</span></span> <span data-ttu-id="a66de-111">Aby użyć bazy danych, która wymaga parametrów połączenia, zaimplementuj dodatkową wartość w `ConfigurationBuilder` celu dostarczenia parametrów połączenia od innego dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a66de-111">To use a database that requires a connection string, implement a secondary `ConfigurationBuilder` to supply the connection string from another configuration provider.</span></span>
- <span data-ttu-id="a66de-112">Dostawca odczytuje tabelę bazy danych w konfiguracji podczas uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="a66de-112">The provider reads a database table into configuration at startup.</span></span> <span data-ttu-id="a66de-113">Dostawca nie wykonuje zapytania do bazy danych w oparciu o klucz.</span><span class="sxs-lookup"><span data-stu-id="a66de-113">The provider doesn't query the database on a per-key basis.</span></span>
- <span data-ttu-id="a66de-114">Ponowne załadowanie nie zostało zaimplementowane, więc aktualizacja bazy danych po uruchomieniu aplikacji nie ma wpływu na konfigurację aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a66de-114">Reload-on-change isn't implemented, so updating the database after the app starts has no effect on the app's configuration.</span></span>

<span data-ttu-id="a66de-115">Zdefiniuj `Settings` jednostkę typu rekordu do przechowywania wartości konfiguracji w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="a66de-115">Define a `Settings` record type entity for storing configuration values in the database.</span></span> <span data-ttu-id="a66de-116">Można na przykład dodać plik *Settings.cs* do folderu *models* :</span><span class="sxs-lookup"><span data-stu-id="a66de-116">For example, you could add a *Settings.cs* file in your *Models* folder:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Models/Settings.cs":::

<span data-ttu-id="a66de-117">Aby uzyskać informacje na temat typów rekordów, zobacz [typy rekordów w języku C# 9](../../csharp/whats-new/csharp-9.md#record-types).</span><span class="sxs-lookup"><span data-stu-id="a66de-117">For information on record types, see [Record types in C# 9](../../csharp/whats-new/csharp-9.md#record-types).</span></span>

<span data-ttu-id="a66de-118">Dodaj `EntityConfigurationContext` do magazynu i uzyskaj dostęp do skonfigurowanych wartości.</span><span class="sxs-lookup"><span data-stu-id="a66de-118">Add an `EntityConfigurationContext` to store and access the configured values.</span></span>

<span data-ttu-id="a66de-119">*Dostawcy/EntityConfigurationContext. cs*:</span><span class="sxs-lookup"><span data-stu-id="a66de-119">*Providers/EntityConfigurationContext.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationContext.cs":::

<span data-ttu-id="a66de-120">Utwórz klasę implementującą <xref:Microsoft.Extensions.Configuration.IConfigurationSource> .</span><span class="sxs-lookup"><span data-stu-id="a66de-120">Create a class that implements <xref:Microsoft.Extensions.Configuration.IConfigurationSource>.</span></span>

<span data-ttu-id="a66de-121">*Dostawcy/EntityConfigurationSource. cs*:</span><span class="sxs-lookup"><span data-stu-id="a66de-121">*Providers/EntityConfigurationSource.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationSource.cs":::

<span data-ttu-id="a66de-122">Utwórz niestandardowego dostawcę konfiguracji, dziedziczących od <xref:Microsoft.Extensions.Configuration.ConfigurationProvider> .</span><span class="sxs-lookup"><span data-stu-id="a66de-122">Create the custom configuration provider by inheriting from <xref:Microsoft.Extensions.Configuration.ConfigurationProvider>.</span></span> <span data-ttu-id="a66de-123">Dostawca konfiguracji inicjuje bazę danych, gdy jest pusta.</span><span class="sxs-lookup"><span data-stu-id="a66de-123">The configuration provider initializes the database when it's empty.</span></span> <span data-ttu-id="a66de-124">Ponieważ w kluczach konfiguracji jest rozróżniana wielkość liter, słownik używany do inicjowania bazy danych jest tworzony przy użyciu funkcji porównującej bez uwzględniania wielkości liter ([StringComparer. OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)).</span><span class="sxs-lookup"><span data-stu-id="a66de-124">Since configuration keys are case-insensitive, the dictionary used to initialize the database is created with the case-insensitive comparer ([StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)).</span></span>

<span data-ttu-id="a66de-125">*Dostawcy/EntityConfigurationProvider. cs*:</span><span class="sxs-lookup"><span data-stu-id="a66de-125">*Providers/EntityConfigurationProvider.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationProvider.cs":::

<span data-ttu-id="a66de-126">`AddEntityConfiguration`Metoda rozszerzająca zezwala na Dodawanie źródła konfiguracji do <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a66de-126">An `AddEntityConfiguration` extension method permits adding the configuration source to a <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> instance.</span></span>

<span data-ttu-id="a66de-127">*Rozszerzenia/ConfigurationBuilderExtensions. cs*:</span><span class="sxs-lookup"><span data-stu-id="a66de-127">*Extensions/ConfigurationBuilderExtensions.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Extensions/ConfigurationBuilderExtensions.cs":::

<span data-ttu-id="a66de-128">Poniższy kod pokazuje, jak używać niestandardowych `EntityConfigurationProvider` w *program.cs*:</span><span class="sxs-lookup"><span data-stu-id="a66de-128">The following code shows how to use the custom `EntityConfigurationProvider` in *Program.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Program.cs" highlight="21-22":::

## <a name="see-also"></a><span data-ttu-id="a66de-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a66de-129">See also</span></span>

- [<span data-ttu-id="a66de-130">Konfiguracja w programie .NET</span><span class="sxs-lookup"><span data-stu-id="a66de-130">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="a66de-131">Dostawcy konfiguracji w programie .NET</span><span class="sxs-lookup"><span data-stu-id="a66de-131">Configuration providers in .NET</span></span>](configuration-providers.md)
