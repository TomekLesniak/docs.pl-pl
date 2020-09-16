---
title: Zabezpieczanie aplikacji
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: af184f64b43c2d3dc39f8c0add08940d3b002c24
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550758"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="ea0dc-102">Zabezpieczanie aplikacji ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea0dc-102">Securing ADO.NET applications</span></span>

<span data-ttu-id="ea0dc-103">Pisanie zabezpieczonej aplikacji ADO.NET obejmuje więcej niż uniknięcie wspólnego kodowania pułapek, takie jak nieweryfikowanie danych wejściowych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="ea0dc-104">Aplikacja, która uzyskuje dostęp do danych, ma wiele potencjalnych punktów awarii, których atakujący może wykorzystać do pobierania, manipulowania lub niszczenia poufnych danych.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="ea0dc-105">W związku z tym ważne jest, aby zrozumieć wszystkie aspekty zabezpieczeń, od procesu modelowania zagrożeń podczas fazy projektowania aplikacji, do ostatecznego wdrożenia i trwającej konserwacji.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
<span data-ttu-id="ea0dc-106">.NET Framework zawiera wiele przydatnych klas, usług i narzędzi do zabezpieczania i administrowania aplikacjami baz danych.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="ea0dc-107">Środowisko uruchomieniowe języka wspólnego (CLR) zapewnia bezpieczne dla typów środowisko kodu do uruchamiania w programie, a zabezpieczenia dostępu kodu (CAS) ograniczają dalsze uprawnienia do kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="ea0dc-108">Zgodnie z bezpiecznymi praktykami kodowania dostępu do danych ograniczają szkody, które mogą zostać spowodowane przez potencjalną osobę atakującą.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
<span data-ttu-id="ea0dc-109">Pisanie bezpiecznego kodu nie chroni przed atakami z użyciem niezarządzanych zasobów, takich jak bazy danych.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="ea0dc-110">Większość baz danych serwera, takich jak SQL Server, ma własne systemy zabezpieczeń, które zwiększają bezpieczeństwo po poprawnym wdrożeniu.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="ea0dc-111">Jednak nawet źródło danych z niezawodnym systemem zabezpieczeń może być ofiarą ataku, jeśli nie jest odpowiednio skonfigurowany.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea0dc-112">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="ea0dc-112">In this section</span></span>

 [<span data-ttu-id="ea0dc-113">Przegląd zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="ea0dc-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="ea0dc-114">Zawiera zalecenia dotyczące projektowania bezpiecznych aplikacji ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="ea0dc-115">Bezpieczny dostęp do danych</span><span class="sxs-lookup"><span data-stu-id="ea0dc-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="ea0dc-116">Opisuje sposób pracy z danymi z zabezpieczonego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="ea0dc-117">Zabezpieczanie aplikacji klienckich</span><span class="sxs-lookup"><span data-stu-id="ea0dc-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="ea0dc-118">Opisuje zagadnienia dotyczące zabezpieczeń aplikacji klienckich.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="ea0dc-119">Zabezpieczenia dostępu kodu i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea0dc-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="ea0dc-120">Opisuje, jak urzędy certyfikacji mogą chronić kod ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="ea0dc-121">Omówiono również sposób pracy z częściowym zaufaniem.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="ea0dc-122">Bezpieczeństwo danych i poufności informacji</span><span class="sxs-lookup"><span data-stu-id="ea0dc-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="ea0dc-123">Opisuje opcje szyfrowania dla aplikacji ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ea0dc-124">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="ea0dc-124">Related sections</span></span>

 [<span data-ttu-id="ea0dc-125">Wskazówki dotyczące zabezpieczeń zestawów danych i DataTable</span><span class="sxs-lookup"><span data-stu-id="ea0dc-125">DataSet and DataTable security guidance</span></span>](dataset-datatable-dataview/security-guidance.md)  
 <span data-ttu-id="ea0dc-126">Zapewnia wskazówki dotyczące zabezpieczeń dla <xref:System.Data.DataSet> i <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="ea0dc-126">Provides security guidance for <xref:System.Data.DataSet> and <xref:System.Data.DataTable>.</span></span>

 [<span data-ttu-id="ea0dc-127">Zabezpieczenia serwera SQL</span><span class="sxs-lookup"><span data-stu-id="ea0dc-127">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="ea0dc-128">Opisuje funkcje zabezpieczeń SQL Server z perspektywy dewelopera.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-128">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="ea0dc-129">Zagadnienia dotyczące zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="ea0dc-129">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="ea0dc-130">Opisuje zabezpieczenia Entity Framework aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-130">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="ea0dc-131">Bezpieczeństwo</span><span class="sxs-lookup"><span data-stu-id="ea0dc-131">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="ea0dc-132">Zawiera łącza do artykułów opisujących wszystkie aspekty zabezpieczeń w programie .NET.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-132">Contains links to articles describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="ea0dc-133">[Narzędzia zabezpieczeń](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ea0dc-133">[Security Tools](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="ea0dc-134">.NET Framework narzędzia do zabezpieczania zasad zabezpieczeń i administrowania nimi.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-134">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="ea0dc-135">[Zasoby do tworzenia bezpiecznych aplikacji](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ea0dc-135">[Resources for Creating Secure Applications](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="ea0dc-136">Zawiera łącza do artykułów na potrzeby tworzenia bezpiecznych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-136">Provides links to articles for creating secure applications.</span></span>  
  
 [<span data-ttu-id="ea0dc-137">Bibliografia dotycząca zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="ea0dc-137">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="ea0dc-138">Oferuje linki do zasobów zewnętrznych dostępnych w trybie online i drukowania.</span><span class="sxs-lookup"><span data-stu-id="ea0dc-138">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea0dc-139">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ea0dc-139">See also</span></span>

- [<span data-ttu-id="ea0dc-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea0dc-140">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="ea0dc-141">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea0dc-141">ADO.NET Overview</span></span>](ado-net-overview.md)
