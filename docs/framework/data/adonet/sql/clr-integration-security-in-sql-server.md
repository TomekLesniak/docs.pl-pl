---
title: Zabezpieczenia integracji CLR w programie SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: e5d15b4e5ac36f7ecddf45179c65a60995a1a578
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147778"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="79942-102">Zabezpieczenia integracji CLR w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="79942-102">CLR Integration Security in SQL Server</span></span>

<span data-ttu-id="79942-103">Microsoft SQL Server zapewnia integrację składnika środowiska uruchomieniowego języka wspólnego (CLR) .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79942-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="79942-104">Integracja środowiska CLR pozwala pisać procedury składowane, wyzwalacze, typy zdefiniowane przez użytkownika, funkcje zdefiniowane przez użytkownika, agregacje zdefiniowane przez użytkownika i funkcję przesyłania strumieniowego z wartościami przechowywanymi w tabeli przy użyciu dowolnego .NET Framework języka, takiego jak Microsoft Visual Basic .NET lub Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="79942-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="79942-105">Środowisko CLR obsługuje model zabezpieczeń o nazwie zabezpieczenia dostępu kodu (CAS) dla kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="79942-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="79942-106">W tym modelu uprawnienia są przyznawane zestawom w oparciu o dowody dostarczone przez kod w metadanych.</span><span class="sxs-lookup"><span data-stu-id="79942-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="79942-107">SQL Server integruje model zabezpieczeń oparty na użytkownikach SQL Server z modelem zabezpieczeń opartym na kodzie w środowisku CLR.</span><span class="sxs-lookup"><span data-stu-id="79942-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="79942-108">Zasoby zewnętrzne</span><span class="sxs-lookup"><span data-stu-id="79942-108">External Resources</span></span>  

 <span data-ttu-id="79942-109">Aby uzyskać więcej informacji na temat integracji środowiska CLR z SQL Server, zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="79942-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="79942-110">Zasób</span><span class="sxs-lookup"><span data-stu-id="79942-110">Resource</span></span>|<span data-ttu-id="79942-111">Opis</span><span class="sxs-lookup"><span data-stu-id="79942-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="79942-112">Zabezpieczenia dostępu kodu</span><span class="sxs-lookup"><span data-stu-id="79942-112">Code Access Security</span></span>](../../../misc/code-access-security.md)|<span data-ttu-id="79942-113">Zawiera tematy opisujące urzędy certyfikacji w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79942-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="79942-114">Zabezpieczenia integracji środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="79942-114">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="79942-115">Omawia model zabezpieczeń dla kodu zarządzanego wykonywanego wewnątrz SQL Server.</span><span class="sxs-lookup"><span data-stu-id="79942-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79942-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="79942-116">See also</span></span>

- [<span data-ttu-id="79942-117">Zabezpieczanie aplikacji ADO.NET</span><span class="sxs-lookup"><span data-stu-id="79942-117">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="79942-118">Scenariusze zabezpieczeń aplikacji w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="79942-118">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="79942-119">Integracja aparatu plików wykonywalnych języka wspólnego z programem SQL Server</span><span class="sxs-lookup"><span data-stu-id="79942-119">SQL Server Common Language Runtime Integration</span></span>](sql-server-common-language-runtime-integration.md)
- [<span data-ttu-id="79942-120">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="79942-120">ADO.NET Overview</span></span>](../ado-net-overview.md)
