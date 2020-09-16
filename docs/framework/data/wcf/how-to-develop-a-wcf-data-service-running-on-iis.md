---
title: 'Instrukcje: Tworzenie usługi danych WCF działającej na serwerze IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: 75dc18f3ee91ec077ed48c68ec62cb47910d9ddd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543488"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="977cf-102">Instrukcje: Tworzenie usługi danych programu WCF uruchomionej w usługach IIS</span><span class="sxs-lookup"><span data-stu-id="977cf-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="977cf-103">W tym artykule pokazano, jak za pomocą Usługi danych programu WCF utworzyć usługę danych opartą na przykładowej bazie danych Northwind hostowanej przez aplikację sieci Web ASP.NET działającą w usłudze Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="977cf-103">This article shows how to use WCF Data Services to create a data service that's based on the Northwind sample database that's hosted by an ASP.NET Web app running on Internet Information Services (IIS).</span></span> <span data-ttu-id="977cf-104">Aby zapoznać się z przykładem tworzenia tej samej usługi danych Northwind jako aplikacji sieci Web ASP.NET działającej na serwerze deweloperskim ASP.NET, zobacz [Przewodnik Szybki start usługi danych programu WCF](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="977cf-104">For an example of how to create the same Northwind data service as an ASP.NET Web app that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="977cf-105">Aby utworzyć usługę danych Northwind, należy najpierw zainstalować przykładową bazę danych Northwind na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="977cf-105">To create the Northwind data service, first install the Northwind sample database on the local computer.</span></span> <span data-ttu-id="977cf-106">Aby zainstalować bazę danych, uruchom skrypt Transact-SQL z [przykładowych baz danych Northwind i pubs dla Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span><span class="sxs-lookup"><span data-stu-id="977cf-106">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

<span data-ttu-id="977cf-107">W tym artykule pokazano, jak utworzyć usługę danych przy użyciu dostawcy Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="977cf-107">This article shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="977cf-108">Inni dostawcy usług danych są dostępni.</span><span class="sxs-lookup"><span data-stu-id="977cf-108">Other data services providers are available.</span></span> <span data-ttu-id="977cf-109">Aby uzyskać więcej informacji, zobacz [Data Services Providers](data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="977cf-109">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>

<span data-ttu-id="977cf-110">Po utworzeniu usługi należy jawnie zapewnić dostęp do zasobów usługi danych.</span><span class="sxs-lookup"><span data-stu-id="977cf-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="977cf-111">Aby uzyskać więcej informacji, zobacz [jak: Włączanie dostępu do usługi danych](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="977cf-111">For more information, see [How to: Enable Access to the Data Service](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="977cf-112">Tworzenie aplikacji sieci Web ASP.NET działającej w usługach IIS</span><span class="sxs-lookup"><span data-stu-id="977cf-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="977cf-113">W programie Visual Studio w menu **plik** wybierz pozycję **Nowy**  >  **projekt**.</span><span class="sxs-lookup"><span data-stu-id="977cf-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="977cf-114">W oknie dialogowym **Nowy projekt** wybierz **zainstalowaną** > [**Visual C#** lub **Visual Basic**] > kategorii **sieci Web** .</span><span class="sxs-lookup"><span data-stu-id="977cf-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="977cf-115">Wybierz szablon **aplikacji sieci Web ASP.NET** .</span><span class="sxs-lookup"><span data-stu-id="977cf-115">Select the **ASP.NET Web Application** template.</span></span>

4. <span data-ttu-id="977cf-116">Wprowadź `NorthwindService` jako nazwę projektu.</span><span class="sxs-lookup"><span data-stu-id="977cf-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="977cf-117">Kliknij pozycję **OK**.</span><span class="sxs-lookup"><span data-stu-id="977cf-117">Click **OK**.</span></span>

6. <span data-ttu-id="977cf-118">W menu **projekt** wybierz pozycję **Właściwości NorthwindService**.</span><span class="sxs-lookup"><span data-stu-id="977cf-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="977cf-119">Wybierz kartę **Sieć Web** , a następnie wybierz pozycję **Użyj lokalnego serwera sieci Web usług IIS**.</span><span class="sxs-lookup"><span data-stu-id="977cf-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="977cf-120">Kliknij pozycję **Utwórz katalog wirtualny** , a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="977cf-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="977cf-121">W wierszu polecenia z uprawnieniami administratora wykonaj jedno z następujących poleceń (w zależności od systemu operacyjnego):</span><span class="sxs-lookup"><span data-stu-id="977cf-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="977cf-122">Systemy 32-bitowe: </span><span class="sxs-lookup"><span data-stu-id="977cf-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - <span data-ttu-id="977cf-123">Systemy 64-bitowe: </span><span class="sxs-lookup"><span data-stu-id="977cf-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="977cf-124">Upewnij się, że na komputerze zarejestrowano Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="977cf-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="977cf-125">W wierszu polecenia z uprawnieniami administratora wykonaj jedno z następujących poleceń (w zależności od systemu operacyjnego):</span><span class="sxs-lookup"><span data-stu-id="977cf-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="977cf-126">Systemy 32-bitowe: </span><span class="sxs-lookup"><span data-stu-id="977cf-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - <span data-ttu-id="977cf-127">Systemy 64-bitowe: </span><span class="sxs-lookup"><span data-stu-id="977cf-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="977cf-128">Gwarantuje to, że usługi IIS działają prawidłowo po zainstalowaniu programu WCF na komputerze.</span><span class="sxs-lookup"><span data-stu-id="977cf-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="977cf-129">Może być również konieczne ponowne uruchomienie usług IIS.</span><span class="sxs-lookup"><span data-stu-id="977cf-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="977cf-130">Gdy aplikacja ASP.NET jest uruchomiona na IIS7, należy również wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="977cf-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="977cf-131">Otwórz Menedżera usług IIS i przejdź do aplikacji do obsługi w obszarze **Domyślna witryna sieci Web**.</span><span class="sxs-lookup"><span data-stu-id="977cf-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="977cf-132">W obszarze **Widok funkcji**kliknij dwukrotnie pozycję **uwierzytelnianie**.</span><span class="sxs-lookup"><span data-stu-id="977cf-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="977cf-133">Na stronie **uwierzytelnianie** wybierz opcję **uwierzytelnianie anonimowe**.</span><span class="sxs-lookup"><span data-stu-id="977cf-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="977cf-134">W okienku **Akcje** kliknij pozycję **Edytuj** , aby ustawić podmiot zabezpieczeń, pod którym anonimowi użytkownicy będą łączyć się z lokacją.</span><span class="sxs-lookup"><span data-stu-id="977cf-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="977cf-135">W oknie dialogowym **Edytowanie poświadczeń uwierzytelniania anonimowego** wybierz pozycję **tożsamość puli aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="977cf-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="977cf-136">Korzystając z konta usługi sieciowej, należy przyznać anonimowym użytkownikom dostęp do sieci wewnętrznej skojarzonej z tym kontem.</span><span class="sxs-lookup"><span data-stu-id="977cf-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="977cf-137">Za pomocą SQL Server Management Studio, narzędzia sqlcmd.exe lub edytora Transact-SQL w programie Visual Studio wykonaj następujące polecenie języka Transact-SQL względem wystąpienia SQL Server z załączoną bazą danych Northwind:</span><span class="sxs-lookup"><span data-stu-id="977cf-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="977cf-138">Spowoduje to utworzenie nazwy logowania w wystąpieniu SQL Server dla konta systemu Windows używanego do uruchamiania usług IIS.</span><span class="sxs-lookup"><span data-stu-id="977cf-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="977cf-139">Dzięki temu usługi IIS mogą łączyć się z wystąpieniem SQL Server.</span><span class="sxs-lookup"><span data-stu-id="977cf-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="977cf-140">Po dołączeniu bazy danych Northwind wykonaj następujące polecenia języka Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="977cf-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    <span data-ttu-id="977cf-141">Powoduje to przyznanie praw do nowej nazwy logowania, co umożliwia usługom IIS odczytywanie danych i zapisywanie ich w bazie danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="977cf-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="977cf-142">Zdefiniowanie modelu danych</span><span class="sxs-lookup"><span data-stu-id="977cf-142">Define the data model</span></span>

1. <span data-ttu-id="977cf-143">W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy nazwę projektu ASP.NET, a następnie kliknij pozycję **Dodaj**  >  **nowy element**.</span><span class="sxs-lookup"><span data-stu-id="977cf-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="977cf-144">W oknie dialogowym **Dodaj nowy element** wybierz pozycję **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="977cf-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="977cf-145">Wpisz nazwę modelu danych `Northwind.edmx` .</span><span class="sxs-lookup"><span data-stu-id="977cf-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="977cf-146">W Kreatorze Entity Data Model wybierz pozycję **Generuj z bazy danych**, a następnie kliknij przycisk **dalej**.</span><span class="sxs-lookup"><span data-stu-id="977cf-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="977cf-147">Aby połączyć model danych z bazą danych, wykonaj jedną z następujących czynności, a następnie kliknij przycisk **dalej**:</span><span class="sxs-lookup"><span data-stu-id="977cf-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="977cf-148">Jeśli nie masz już skonfigurowanego połączenia z bazą danych, kliknij pozycję **nowe połączenie** i Utwórz nowe połączenie.</span><span class="sxs-lookup"><span data-stu-id="977cf-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="977cf-149">Aby uzyskać więcej informacji, zobacz [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="977cf-149">For more information, see [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="977cf-150">To wystąpienie SQL Server musi mieć dołączoną przykładową bazę danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="977cf-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="977cf-151">\- oraz</span><span class="sxs-lookup"><span data-stu-id="977cf-151">\- or -</span></span>

    - <span data-ttu-id="977cf-152">Jeśli masz już połączenie z bazą danych do łączenia się z bazą danych Northwind, wybierz to połączenie z listy połączeń.</span><span class="sxs-lookup"><span data-stu-id="977cf-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="977cf-153">Na ostatniej stronie kreatora zaznacz pola wyboru dla wszystkich tabel w bazie danych, a następnie wyczyść pola wyboru dla widoków i procedur składowanych.</span><span class="sxs-lookup"><span data-stu-id="977cf-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="977cf-154">Kliknij przycisk **Zakończ** , aby zamknąć kreatora.</span><span class="sxs-lookup"><span data-stu-id="977cf-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="977cf-155">Utworzenie usługi danych</span><span class="sxs-lookup"><span data-stu-id="977cf-155">Create the data service</span></span>

1. <span data-ttu-id="977cf-156">W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy nazwę projektu ASP.NET, a następnie kliknij pozycję **Dodaj**  >  **nowy element**.</span><span class="sxs-lookup"><span data-stu-id="977cf-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="977cf-157">W oknie dialogowym **Dodaj nowy element** wybierz pozycję **Usługa danych WCF**.</span><span class="sxs-lookup"><span data-stu-id="977cf-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![Szablon elementu usługi danych programu WCF w programie Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="977cf-159">Szablon **usługi danych programu WCF** jest dostępny w programie visual Studio 2015, ale nie w programie visual Studio 2017 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="977cf-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="977cf-160">W polu Nazwa usługi wprowadź wartość `Northwind` .</span><span class="sxs-lookup"><span data-stu-id="977cf-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="977cf-161">Program Visual Studio tworzy znaczniki XML i pliki kodu dla nowej usługi.</span><span class="sxs-lookup"><span data-stu-id="977cf-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="977cf-162">Domyślnie zostanie otwarte okno edytora kodu.</span><span class="sxs-lookup"><span data-stu-id="977cf-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="977cf-163">W **Eksplorator rozwiązań**usługa ma nazwę, Northwind i rozszerzenie. svc.cs lub. svc. vb.</span><span class="sxs-lookup"><span data-stu-id="977cf-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="977cf-164">W kodzie usługi danych Zastąp komentarz `/* TODO: put your data source class name here */` w definicji klasy, która definiuje usługę danych z typem, który jest kontenerem jednostek modelu danych, w tym przypadku `NorthwindEntities` .</span><span class="sxs-lookup"><span data-stu-id="977cf-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="977cf-165">Definicja klasy powinna wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="977cf-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="977cf-166">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="977cf-166">See also</span></span>

- [<span data-ttu-id="977cf-167">Udostępnianie danych jako usługi</span><span class="sxs-lookup"><span data-stu-id="977cf-167">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
