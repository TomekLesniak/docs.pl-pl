---
title: Funkcje Canonical
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: 11e22d527c4266f45ea5d26f2ec95926ebe46332
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185252"
---
# <a name="canonical-functions"></a><span data-ttu-id="e49dc-102">Funkcje Canonical</span><span class="sxs-lookup"><span data-stu-id="e49dc-102">Canonical Functions</span></span>

<span data-ttu-id="e49dc-103">W tej sekcji omówiono funkcje kanoniczne, które są obsługiwane przez wszystkich dostawców danych, i mogą być używane przez wszystkie technologie zapytań.</span><span class="sxs-lookup"><span data-stu-id="e49dc-103">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="e49dc-104">Nie można rozszerzyć funkcji kanonicznych przez dostawcę.</span><span class="sxs-lookup"><span data-stu-id="e49dc-104">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="e49dc-105">Te funkcje kanoniczne zostaną przetłumaczone na odpowiednie funkcje źródła danych dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="e49dc-105">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="e49dc-106">Pozwala to na wywołania funkcji wyrażone w typowym formacie między źródłami danych.</span><span class="sxs-lookup"><span data-stu-id="e49dc-106">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="e49dc-107">Ponieważ te funkcje kanoniczne są niezależne od źródeł danych, argument i zwracane typy funkcji kanonicznych są zdefiniowane w kategoriach typów w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="e49dc-107">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="e49dc-108">Jednak niektóre źródła danych mogą nie obsługiwać wszystkich typów w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="e49dc-108">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="e49dc-109">Jeśli w zapytaniu są używane funkcje kanoniczne [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , odpowiednia funkcja zostanie wywołana w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="e49dc-109">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="e49dc-110">Wszystkie funkcje kanoniczne mają zarówno zachowanie danych wejściowych, jak i jawne określone warunki błędu.</span><span class="sxs-lookup"><span data-stu-id="e49dc-110">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="e49dc-111">Dostawcy sklepu powinni przestrzegać tego zachowania, ale Entity Framework nie wymusza tego zachowania.</span><span class="sxs-lookup"><span data-stu-id="e49dc-111">Store providers should comply with that behavior, but Entity Framework does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="e49dc-112">W przypadku scenariuszy LINQ zapytania dotyczące Entity Framework obejmują mapowanie metod CLR do metod w podstawowym źródle danych.</span><span class="sxs-lookup"><span data-stu-id="e49dc-112">For LINQ scenarios, queries against the Entity Framework involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="e49dc-113">Metody CLR mapują na funkcje kanoniczne, dzięki czemu określony zestaw metod będzie poprawnie mapowany, niezależnie od źródła danych.</span><span class="sxs-lookup"><span data-stu-id="e49dc-113">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="e49dc-114">Przestrzeń nazw funkcji kanonicznych</span><span class="sxs-lookup"><span data-stu-id="e49dc-114">Canonical Functions Namespace</span></span>  

 <span data-ttu-id="e49dc-115">Przestrzeń nazw dla funkcji kanonicznej to <xref:System.Data.Metadata.Edm> .</span><span class="sxs-lookup"><span data-stu-id="e49dc-115">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="e49dc-116"><xref:System.Data.Metadata.Edm>Przestrzeń nazw jest automatycznie dołączana do wszystkich zapytań.</span><span class="sxs-lookup"><span data-stu-id="e49dc-116">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="e49dc-117">Jeśli jednak zostanie zaimportowana inna przestrzeń nazw, która zawiera funkcję o takiej samej nazwie jak funkcja kanoniczna (w <xref:System.Data.Metadata.Edm> przestrzeni nazw), należy określić przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="e49dc-117">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e49dc-118">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="e49dc-118">In This Section</span></span>  

 [<span data-ttu-id="e49dc-119">Funkcje agregujące Canonical</span><span class="sxs-lookup"><span data-stu-id="e49dc-119">Aggregate Canonical Functions</span></span>](aggregate-canonical-functions.md)  
 <span data-ttu-id="e49dc-120">Omawia agregacje funkcji w postaci [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonicznej.</span><span class="sxs-lookup"><span data-stu-id="e49dc-120">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="e49dc-121">Funkcje matematyczne Canonical</span><span class="sxs-lookup"><span data-stu-id="e49dc-121">Math Canonical Functions</span></span>](math-canonical-functions.md)  
 <span data-ttu-id="e49dc-122">Omawia funkcje matematyczne w postaci [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonicznej.</span><span class="sxs-lookup"><span data-stu-id="e49dc-122">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="e49dc-123">Funkcje ciągów Canonical</span><span class="sxs-lookup"><span data-stu-id="e49dc-123">String Canonical Functions</span></span>](string-canonical-functions.md)  
 <span data-ttu-id="e49dc-124">Omawia [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Funkcje ciągów kanonicznych.</span><span class="sxs-lookup"><span data-stu-id="e49dc-124">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="e49dc-125">Funkcji daty i godziny Canonical</span><span class="sxs-lookup"><span data-stu-id="e49dc-125">Date and Time Canonical Functions</span></span>](date-and-time-canonical-functions.md)  
 <span data-ttu-id="e49dc-126">Omawia [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funkcje kanoniczne daty i godziny.</span><span class="sxs-lookup"><span data-stu-id="e49dc-126">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="e49dc-127">Funkcje bitowe Canonical</span><span class="sxs-lookup"><span data-stu-id="e49dc-127">Bitwise Canonical Functions</span></span>](bitwise-canonical-functions.md)  
 <span data-ttu-id="e49dc-128">Omawia bitowe [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funkcje kanoniczne.</span><span class="sxs-lookup"><span data-stu-id="e49dc-128">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="e49dc-129">Funkcje przestrzenne</span><span class="sxs-lookup"><span data-stu-id="e49dc-129">Spatial Functions</span></span>](spatial-functions.md)  
 <span data-ttu-id="e49dc-130">Omawia funkcje przestrzenne w postaci [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonicznej.</span><span class="sxs-lookup"><span data-stu-id="e49dc-130">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="e49dc-131">Inne funkcje Canonical</span><span class="sxs-lookup"><span data-stu-id="e49dc-131">Other Canonical Functions</span></span>](other-canonical-functions.md)  
 <span data-ttu-id="e49dc-132">Omawia funkcje niesklasyfikowane jako bitowe, daty/godziny, String, Math lub Aggregate.</span><span class="sxs-lookup"><span data-stu-id="e49dc-132">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49dc-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e49dc-133">See also</span></span>

- [<span data-ttu-id="e49dc-134">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="e49dc-134">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="e49dc-135">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="e49dc-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="e49dc-136">Model koncepcyjny Canonical do mapowania funkcji serwera SQL</span><span class="sxs-lookup"><span data-stu-id="e49dc-136">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [<span data-ttu-id="e49dc-137">Funkcje zdefiniowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="e49dc-137">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)
