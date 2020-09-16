---
title: 'Instrukcje: Określanie parametrów połączenia'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9b029644e0d4e4c7467fbe1e1144579e6edb3478
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536213"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="15803-102">Instrukcje: Określanie parametrów połączenia</span><span class="sxs-lookup"><span data-stu-id="15803-102">How to: Define the Connection String</span></span>

<span data-ttu-id="15803-103">W tym temacie przedstawiono sposób definiowania parametrów połączenia, które są używane podczas nawiązywania połączenia z modelem koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="15803-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="15803-104">Ten temat jest oparty na modelu koncepcyjnym [sprzedaży AdventureWorks](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) .</span><span class="sxs-lookup"><span data-stu-id="15803-104">This topic is based on the [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="15803-105">Model sprzedaży AdventureWorks jest używany w całym temacie tematy związane z zadaniami w dokumentacji Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="15803-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="15803-106">W tym temacie założono, że skonfigurowano już Entity Framework i zdefiniowano model sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="15803-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="15803-107">Aby uzyskać więcej informacji, zobacz [jak: ręcznie zdefiniować model i pliki mapowania](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="15803-107">For more information, see [How to: Manually Define the Model and Mapping Files](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="15803-108">Procedury opisane w tym temacie są również dołączone [do: ręczne Konfigurowanie projektu Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="15803-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="15803-109">W przypadku używania Kreatora Entity Data Model w projekcie programu Visual Studio program automatycznie generuje plik. edmx i konfiguruje projekt do korzystania z Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="15803-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="15803-110">Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="15803-110">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="15803-111">Aby zdefiniować Entity Framework parametry połączenia</span><span class="sxs-lookup"><span data-stu-id="15803-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="15803-112">Otwórz plik konfiguracji aplikacji projektu (app.config) i Dodaj następujące parametry połączenia:</span><span class="sxs-lookup"><span data-stu-id="15803-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="15803-113">Jeśli projekt nie ma pliku konfiguracji aplikacji, można go dodać, wybierając pozycję **Dodaj nowy element** z menu **projekt** , wybierając kategorię **Ogólne** , wybierając **plik konfiguracji aplikacji**, a następnie klikając przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="15803-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="15803-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="15803-114">See also</span></span>

- <span data-ttu-id="15803-115">[Szybki start](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="15803-115">[Quickstart](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="15803-116">[Instrukcje: Tworzenie nowego pliku. edmx](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="15803-116">[How to: Create a New .edmx File](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="15803-117">[Narzędzia Entity Data Model ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="15803-117">[ADO.NET Entity Data Model  Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
