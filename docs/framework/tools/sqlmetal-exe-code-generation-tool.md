---
title: SqlMetal.exe (Narzędzie generowania kodu)
description: Poznaj SqlMetal.exe narzędzia generowania kodu. Użyj narzędzia, aby wygenerować kod i mapowanie dla składnika LINQ to SQL platformy .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: 84cad85a7a9fc4b420b57543b7f258607be4ab52
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517051"
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="f81a0-104">SqlMetal.exe (Narzędzie generowania kodu)</span><span class="sxs-lookup"><span data-stu-id="f81a0-104">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="f81a0-105">Narzędzie wiersza polecenia SqlMetal generuje kod i mapowanie dla [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] składnika .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f81a0-105">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the .NET Framework.</span></span> <span data-ttu-id="f81a0-106">Stosując opisane w dalszej części tego tematu opcje, można za pomocą programu SqlMetal wykonać kilka różnych akcji, takich jak:</span><span class="sxs-lookup"><span data-stu-id="f81a0-106">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
- <span data-ttu-id="f81a0-107">Na podstawie bazy danych — generowanie kodu źródłowego i atrybutów mapowania lub pliku mapowania.</span><span class="sxs-lookup"><span data-stu-id="f81a0-107">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
- <span data-ttu-id="f81a0-108">Na podstawie bazy danych — generowanie pliku języka Intermediate Database Markup Language (dbml) na potrzeby dostosowywania.</span><span class="sxs-lookup"><span data-stu-id="f81a0-108">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
- <span data-ttu-id="f81a0-109">Na podstawie pliku dbml — generowanie kodu i atrybutów mapowania lub pliku mapowania.</span><span class="sxs-lookup"><span data-stu-id="f81a0-109">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="f81a0-110">To narzędzie jest instalowane automatycznie z programem Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f81a0-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="f81a0-111">Domyślnie plik znajduje się w `drive` folderze: \Program Files\Microsoft SDKs\Windows\v `n.nn` \Bin.</span><span class="sxs-lookup"><span data-stu-id="f81a0-111">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="f81a0-112">Jeśli program Visual Studio nie zostanie zainstalowany, można również pobrać plik SQLMetal, pobierając [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span><span class="sxs-lookup"><span data-stu-id="f81a0-112">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f81a0-113">Deweloperzy, którzy korzystają z programu Visual Studio, mogą również generować klasy jednostek przy użyciu Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="f81a0-113">Developers who use Visual Studio can also use the Object Relational Designer to generate entity classes.</span></span> <span data-ttu-id="f81a0-114">Podejście z użyciem wiersza polecenia dobrze sprawdza się w przypadku dużych baz danych.</span><span class="sxs-lookup"><span data-stu-id="f81a0-114">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="f81a0-115">Program SqlMetal to narzędzie wiersza polecenia, więc można użyć go w procesie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="f81a0-115">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="f81a0-116">Aby uruchomić narzędzie, użyj wiersz polecenia dla deweloperów dla programu Visual Studio (lub wiersza polecenia programu Visual Studio w systemie Windows 7).</span><span class="sxs-lookup"><span data-stu-id="f81a0-116">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="f81a0-117">Aby uzyskać więcej informacji, zobacz [wiersza polecenia](developer-command-prompt-for-vs.md). W wierszu polecenia wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="f81a0-117">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f81a0-118">Składnia</span><span class="sxs-lookup"><span data-stu-id="f81a0-118">Syntax</span></span>  
  
```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="f81a0-119">Opcje</span><span class="sxs-lookup"><span data-stu-id="f81a0-119">Options</span></span>  
 <span data-ttu-id="f81a0-120">Aby wyświetlić najbardziej aktualną listę opcji, wpisz `sqlmetal /?` w wierszu polecenia z zainstalowanej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="f81a0-120">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="f81a0-121">**Opcje połączenia**</span><span class="sxs-lookup"><span data-stu-id="f81a0-121">**Connection Options**</span></span>  
  
|<span data-ttu-id="f81a0-122">Opcja</span><span class="sxs-lookup"><span data-stu-id="f81a0-122">Option</span></span>|<span data-ttu-id="f81a0-123">Opis</span><span class="sxs-lookup"><span data-stu-id="f81a0-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f81a0-124">\**/Server:\*\*\*\<name>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-124">**/server:** *\<name>*</span></span>|<span data-ttu-id="f81a0-125">Określa nazwę serwera bazy danych.</span><span class="sxs-lookup"><span data-stu-id="f81a0-125">Specifies database server name.</span></span>|  
|<span data-ttu-id="f81a0-126">\**/Database:\*\*\*\<name>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-126">**/database:** *\<name>*</span></span>|<span data-ttu-id="f81a0-127">Określa wykaz baz danych na serwerze.</span><span class="sxs-lookup"><span data-stu-id="f81a0-127">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="f81a0-128">\**/User:\*\*\*\<name>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-128">**/user:** *\<name>*</span></span>|<span data-ttu-id="f81a0-129">Określa identyfikator logowania użytkownika. Wartość domyślna: Użyj uwierzytelniania systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="f81a0-129">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="f81a0-130">\**/Password:\*\*\*\<password>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-130">**/password:** *\<password>*</span></span>|<span data-ttu-id="f81a0-131">Określa hasło logowania.</span><span class="sxs-lookup"><span data-stu-id="f81a0-131">Specifies logon password.</span></span> <span data-ttu-id="f81a0-132">Wartość domyślna: Użyj uwierzytelniania systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="f81a0-132">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="f81a0-133">\**/Conn:\*\*\*\<connection string>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-133">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="f81a0-134">Określa parametry połączenia z bazą danych.</span><span class="sxs-lookup"><span data-stu-id="f81a0-134">Specifies database connection string.</span></span> <span data-ttu-id="f81a0-135">Nie można używać z opcjami **/Server**, **/Database**, **/User**i **/Password** .</span><span class="sxs-lookup"><span data-stu-id="f81a0-135">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="f81a0-136">W parametrach połączenia nie można umieszczać nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="f81a0-136">Do not include the file name in the connection string.</span></span> <span data-ttu-id="f81a0-137">Zamiast tego należy określić nazwę pliku w wierszu polecenia jako plik wejściowy.</span><span class="sxs-lookup"><span data-stu-id="f81a0-137">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="f81a0-138">Na przykład poniższy wiersz określa "c:\northwnd.mdf" jako plik wejściowy: **SQLMetal/Code: "c:\Northwind.cs"/Language: CSharp "c:\northwnd.mdf"**.</span><span class="sxs-lookup"><span data-stu-id="f81a0-138">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="f81a0-139">\**/timeout:\*\*\*\<seconds>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-139">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="f81a0-140">Określa wartość limitu czasu używaną, gdy program SqlMetal uzyskuje dostęp do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="f81a0-140">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="f81a0-141">Wartość domyślna: 0 (czyli brak limitu czasu).</span><span class="sxs-lookup"><span data-stu-id="f81a0-141">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="f81a0-142">**Opcje wyodrębniania**</span><span class="sxs-lookup"><span data-stu-id="f81a0-142">**Extraction options**</span></span>  
  
|<span data-ttu-id="f81a0-143">Opcja</span><span class="sxs-lookup"><span data-stu-id="f81a0-143">Option</span></span>|<span data-ttu-id="f81a0-144">Opis</span><span class="sxs-lookup"><span data-stu-id="f81a0-144">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f81a0-145">**/views**</span><span class="sxs-lookup"><span data-stu-id="f81a0-145">**/views**</span></span>|<span data-ttu-id="f81a0-146">Wyodrębnia widoki bazy danych.</span><span class="sxs-lookup"><span data-stu-id="f81a0-146">Extracts database views.</span></span>|  
|<span data-ttu-id="f81a0-147">**/functions**</span><span class="sxs-lookup"><span data-stu-id="f81a0-147">**/functions**</span></span>|<span data-ttu-id="f81a0-148">Wyodrębnia funkcje bazy danych.</span><span class="sxs-lookup"><span data-stu-id="f81a0-148">Extracts database functions.</span></span>|  
|<span data-ttu-id="f81a0-149">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="f81a0-149">**/sprocs**</span></span>|<span data-ttu-id="f81a0-150">Wyodrębnia procedury składowane.</span><span class="sxs-lookup"><span data-stu-id="f81a0-150">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="f81a0-151">**Opcje wyjściowe**</span><span class="sxs-lookup"><span data-stu-id="f81a0-151">**Output options**</span></span>  
  
|<span data-ttu-id="f81a0-152">Opcja</span><span class="sxs-lookup"><span data-stu-id="f81a0-152">Option</span></span>|<span data-ttu-id="f81a0-153">Opis</span><span class="sxs-lookup"><span data-stu-id="f81a0-153">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f81a0-154">**/DBML** *[: plik]*</span><span class="sxs-lookup"><span data-stu-id="f81a0-154">**/dbml** *[:file]*</span></span>|<span data-ttu-id="f81a0-155">Wysyła dane wyjściowe w postaci pliku dbml.</span><span class="sxs-lookup"><span data-stu-id="f81a0-155">Sends output as .dbml.</span></span> <span data-ttu-id="f81a0-156">Nie można używać z opcją **/map** .</span><span class="sxs-lookup"><span data-stu-id="f81a0-156">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="f81a0-157">**/Code** *[: plik]*</span><span class="sxs-lookup"><span data-stu-id="f81a0-157">**/code** *[:file]*</span></span>|<span data-ttu-id="f81a0-158">Wysyła dane wyjściowe w postaci kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="f81a0-158">Sends output as source code.</span></span> <span data-ttu-id="f81a0-159">Nie można używać z opcją **/DBML** .</span><span class="sxs-lookup"><span data-stu-id="f81a0-159">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="f81a0-160">**/map** *[: plik]*</span><span class="sxs-lookup"><span data-stu-id="f81a0-160">**/map** *[:file]*</span></span>|<span data-ttu-id="f81a0-161">Generuje plik mapowania XML zamiast atrybutów.</span><span class="sxs-lookup"><span data-stu-id="f81a0-161">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="f81a0-162">Nie można używać z opcją **/DBML** .</span><span class="sxs-lookup"><span data-stu-id="f81a0-162">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="f81a0-163">**Różne**</span><span class="sxs-lookup"><span data-stu-id="f81a0-163">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="f81a0-164">Opcja</span><span class="sxs-lookup"><span data-stu-id="f81a0-164">Option</span></span>|<span data-ttu-id="f81a0-165">Opis</span><span class="sxs-lookup"><span data-stu-id="f81a0-165">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f81a0-166">\**/Language:\*\*\*\<language>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-166">**/language:** *\<language>*</span></span>|<span data-ttu-id="f81a0-167">Określa język kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="f81a0-167">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="f81a0-168">Prawidłowy *\<language>* : VB, CSharp.</span><span class="sxs-lookup"><span data-stu-id="f81a0-168">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="f81a0-169">Wartość domyślna: pochodzi z rozszerzeniem nazwy pliku kodu.</span><span class="sxs-lookup"><span data-stu-id="f81a0-169">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="f81a0-170">\**/Namespace:\*\*\*\<name>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-170">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="f81a0-171">Określa przestrzeń nazw wygenerowanego kodu.</span><span class="sxs-lookup"><span data-stu-id="f81a0-171">Specifies namespace of the generated code.</span></span> <span data-ttu-id="f81a0-172">Wartość domyślna: brak przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="f81a0-172">Default value: no namespace.</span></span>|  
|<span data-ttu-id="f81a0-173">\**/Context:\*\*\*\<type>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-173">**/context:** *\<type>*</span></span>|<span data-ttu-id="f81a0-174">Określa nazwę klasy kontekstu danych.</span><span class="sxs-lookup"><span data-stu-id="f81a0-174">Specifies name of data context class.</span></span> <span data-ttu-id="f81a0-175">Wartość domyślna: pochodzi z nazwy bazy danych.</span><span class="sxs-lookup"><span data-stu-id="f81a0-175">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="f81a0-176">\**/entitybase:\*\*\*\<type>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-176">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="f81a0-177">Określa klasę bazową klas obiektów w generowanym kodzie.</span><span class="sxs-lookup"><span data-stu-id="f81a0-177">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="f81a0-178">Wartość domyślna: obiekty nie mają klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="f81a0-178">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="f81a0-179">**/Pluralize**</span><span class="sxs-lookup"><span data-stu-id="f81a0-179">**/pluralize**</span></span>|<span data-ttu-id="f81a0-180">Automatycznie zmienia nazwy klas i składowych na liczbę mnogą lub pojedynczą.</span><span class="sxs-lookup"><span data-stu-id="f81a0-180">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="f81a0-181">Ta opcja jest dostępna tylko w wersji angielskiej (USA).</span><span class="sxs-lookup"><span data-stu-id="f81a0-181">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="f81a0-182">\**/Serialization:\*\*\*\<option>*</span><span class="sxs-lookup"><span data-stu-id="f81a0-182">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="f81a0-183">Generuje klasy, które można serializować.</span><span class="sxs-lookup"><span data-stu-id="f81a0-183">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="f81a0-184">Prawidłowy *\<option>* : brak, jednokierunkowe.</span><span class="sxs-lookup"><span data-stu-id="f81a0-184">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="f81a0-185">Wartość domyślna: None.</span><span class="sxs-lookup"><span data-stu-id="f81a0-185">Default value: None.</span></span><br /><br /> <span data-ttu-id="f81a0-186">Aby uzyskać więcej informacji, zobacz [serializacji](../data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="f81a0-186">For more information, see [Serialization](../data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="f81a0-187">**Plik wejściowy**</span><span class="sxs-lookup"><span data-stu-id="f81a0-187">**Input File**</span></span>  
  
|<span data-ttu-id="f81a0-188">Opcja</span><span class="sxs-lookup"><span data-stu-id="f81a0-188">Option</span></span>|<span data-ttu-id="f81a0-189">Opis</span><span class="sxs-lookup"><span data-stu-id="f81a0-189">Description</span></span>|  
|------------|-----------------|  
|**\<input file>**|<span data-ttu-id="f81a0-190">Określa plik. mdf SQL Server Express, plik SQL Server Compact 3,5. sdf lub plik pośredni. dbml.</span><span class="sxs-lookup"><span data-stu-id="f81a0-190">Specifies a SQL Server Express .mdf file, a SQL Server Compact 3.5 .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f81a0-191">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f81a0-191">Remarks</span></span>  
 <span data-ttu-id="f81a0-192">Działanie programu SqlMetal w rzeczywistości obejmuje wykonanie dwóch kroków:</span><span class="sxs-lookup"><span data-stu-id="f81a0-192">SqlMetal functionality actually involves two steps:</span></span>  
  
- <span data-ttu-id="f81a0-193">Wyodrębnienie metadanych bazy danych do pliku dbml.</span><span class="sxs-lookup"><span data-stu-id="f81a0-193">Extracting the metadata of the database into a .dbml file.</span></span>  
  
- <span data-ttu-id="f81a0-194">Wygenerowanie pliku wyjściowego z kodem.</span><span class="sxs-lookup"><span data-stu-id="f81a0-194">Generating a code output file.</span></span>  
  
     <span data-ttu-id="f81a0-195">Korzystając z odpowiednich opcji wiersza polecenia, można utworzyć kod źródłowy Visual Basic lub C# lub utworzyć plik mapowania XML.</span><span class="sxs-lookup"><span data-stu-id="f81a0-195">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="f81a0-196">Aby wyodrębnić metadane z pliku mdf, należy określić nazwę pliku mdf po wszystkich innych opcjach.</span><span class="sxs-lookup"><span data-stu-id="f81a0-196">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="f81a0-197">Jeśli **/Server** nie jest określony, zakłada się **localhost/SQLExpress** .</span><span class="sxs-lookup"><span data-stu-id="f81a0-197">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="f81a0-198">Microsoft SQL Server 2005 zgłasza wyjątek, jeśli spełnione są co najmniej jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="f81a0-198">Microsoft SQL Server 2005 throws an exception if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="f81a0-199">Program SqlMetal próbuje wyodrębnić procedurę składowaną, którą sam wywołuje.</span><span class="sxs-lookup"><span data-stu-id="f81a0-199">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
- <span data-ttu-id="f81a0-200">Poziom zagnieżdżenia procedury składowanej, funkcji lub widoku przekracza 32.</span><span class="sxs-lookup"><span data-stu-id="f81a0-200">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="f81a0-201">Program SqlMetal przechwytuje ten wyjątek i zgłasza go jako ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="f81a0-201">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="f81a0-202">Aby określić nazwę pliku wejściowego, należy dodać ją do wiersza polecenia jako plik wejściowy.</span><span class="sxs-lookup"><span data-stu-id="f81a0-202">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="f81a0-203">Dołączenie nazwy pliku w parametrach połączenia (przy użyciu opcji **/Conn** ) nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="f81a0-203">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f81a0-204">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f81a0-204">Examples</span></span>  
 <span data-ttu-id="f81a0-205">Generuje plik dbml zawierający wyodrębnione metadane SQL:</span><span class="sxs-lookup"><span data-stu-id="f81a0-205">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="f81a0-206">**SQLMetal/Server:/Database o identyfikatorze northwind/dbml: meta. dbml**</span><span class="sxs-lookup"><span data-stu-id="f81a0-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="f81a0-207">Generuje plik dbml zawierający metadane SQL wyodrębnione z pliku mdf przy użyciu programu SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="f81a0-207">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="f81a0-208">**SQLMetal/dbml: meta. dbml mydbfile. mdf**</span><span class="sxs-lookup"><span data-stu-id="f81a0-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="f81a0-209">Generuje plik dbml zawierający metadane SQL wyodrębnione z programu SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="f81a0-209">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="f81a0-210">**SQLMetal/Server: .\SQLEXPRESS/dbml: meta. dbml/Database: Northwind**</span><span class="sxs-lookup"><span data-stu-id="f81a0-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="f81a0-211">Generuje kod źródłowy na podstawie pliku metadanych dbml:</span><span class="sxs-lookup"><span data-stu-id="f81a0-211">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="f81a0-212">**SQLMetal/Namespace: NWIND/Code: NWIND. cs/Language: CSharp. dbml**</span><span class="sxs-lookup"><span data-stu-id="f81a0-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="f81a0-213">Generuje kod źródłowy bezpośrednio na podstawie metadanych SQL:</span><span class="sxs-lookup"><span data-stu-id="f81a0-213">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="f81a0-214">**SQLMetal/Server: KSW/Database: Northwind/Namespace: NWIND/Code: NWIND. cs/Language: CSharp**</span><span class="sxs-lookup"><span data-stu-id="f81a0-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f81a0-215">W przypadku korzystania z opcji **/pluralize** z przykładową bazą danych Northwind należy zwrócić uwagę na następujące zachowanie.</span><span class="sxs-lookup"><span data-stu-id="f81a0-215">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="f81a0-216">Gdy program SqlMetal tworzy nazwy tabel typu wiersz, nazwy tabel mają liczbę pojedynczą.</span><span class="sxs-lookup"><span data-stu-id="f81a0-216">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="f81a0-217">Gdy udostępnia <xref:System.Data.Linq.DataContext> Właściwości tabel, nazwy tabel są w liczbie mnogiej.</span><span class="sxs-lookup"><span data-stu-id="f81a0-217">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="f81a0-218">Przypadkowo nazwy tabel w przykładowej bazie danych Northwind mają już liczbę mnogą.</span><span class="sxs-lookup"><span data-stu-id="f81a0-218">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="f81a0-219">Dlatego też nie widać działania tej części opcji.</span><span class="sxs-lookup"><span data-stu-id="f81a0-219">Therefore, you do not see that part working.</span></span> <span data-ttu-id="f81a0-220">Popularną praktyką jest nadawanie tabelom w bazie danych nazw w liczbie pojedynczej, ale równie popularną praktyką na platformie .NET jest nadawanie kolekcjom nazw w liczbie mnogiej.</span><span class="sxs-lookup"><span data-stu-id="f81a0-220">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f81a0-221">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f81a0-221">See also</span></span>

- [<span data-ttu-id="f81a0-222">Instrukcje: Generowanie modelu obiektu w języku Visual Basic lub C#</span><span class="sxs-lookup"><span data-stu-id="f81a0-222">How to: Generate the Object Model in Visual Basic or C#</span></span>](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [<span data-ttu-id="f81a0-223">Generowanie kodu w składniku LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f81a0-223">Code Generation in LINQ to SQL</span></span>](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="f81a0-224">Mapowanie zewnętrzne</span><span class="sxs-lookup"><span data-stu-id="f81a0-224">External Mapping</span></span>](../data/adonet/sql/linq/external-mapping.md)
