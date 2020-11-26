---
description: -errorreport (opcje kompilatora C#)
title: -errorreport (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 6238ac392ff99d18d9cc7ea07e23b08ff235c14f
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91173233"
---
# <a name="-errorreport-c-compiler-options"></a><span data-ttu-id="8e73a-103">-errorreport (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="8e73a-103">-errorreport (C# Compiler Options)</span></span>

<span data-ttu-id="8e73a-104">Ta opcja zapewnia wygodny sposób raportowania wewnętrznego błędu kompilatora języka C# do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e73a-104">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="8e73a-105">W systemach Windows Vista i Windows Server 2008 ustawienia raportowania błędów wprowadzone dla programu Visual Studio nie przesłaniają ustawień wprowadzonych za pomocą Raportowanie błędów systemu Windows (raportowanie błędów).</span><span class="sxs-lookup"><span data-stu-id="8e73a-105">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="8e73a-106">Ustawienia raportowanie błędów systemu Windows zawsze mają pierwszeństwo przed ustawieniami raportowania błędów programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8e73a-106">WER settings always take precedence over Visual Studio error reporting settings.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e73a-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="8e73a-107">Syntax</span></span>

```console
-errorreport:{ none | prompt | queue | send }
```

## <a name="arguments"></a><span data-ttu-id="8e73a-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="8e73a-108">Arguments</span></span>

 <span data-ttu-id="8e73a-109">**brak**</span><span class="sxs-lookup"><span data-stu-id="8e73a-109">**none**</span></span>  
 <span data-ttu-id="8e73a-110">Raporty o błędach wewnętrznych kompilatora nie będą zbierane ani wysyłane do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e73a-110">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>

 <span data-ttu-id="8e73a-111">**Monituj** Wyświetlany jest komunikat z prośbą o wysłanie raportu po otrzymaniu wewnętrznego błędu kompilatora.</span><span class="sxs-lookup"><span data-stu-id="8e73a-111">**prompt** Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="8e73a-112">**monit** jest wartością domyślną podczas kompilowania aplikacji w środowisku deweloperskim.</span><span class="sxs-lookup"><span data-stu-id="8e73a-112">**prompt** is the default when you compile an application in the development environment.</span></span>

 <span data-ttu-id="8e73a-113">**Kolejka** Kolejkuje raport o błędach.</span><span class="sxs-lookup"><span data-stu-id="8e73a-113">**queue** Queues the error report.</span></span> <span data-ttu-id="8e73a-114">Po zalogowaniu się przy użyciu poświadczeń administracyjnych można zgłosić błędy od czasu ostatniego zalogowania.</span><span class="sxs-lookup"><span data-stu-id="8e73a-114">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="8e73a-115">Nie zostanie wyświetlony monit o wysłanie raportów pod kątem błędów więcej niż raz na trzy dni.</span><span class="sxs-lookup"><span data-stu-id="8e73a-115">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="8e73a-116">**Kolejka** jest wartością domyślną podczas kompilowania aplikacji w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="8e73a-116">**queue** is the default when you compile an application at the command line.</span></span>

 <span data-ttu-id="8e73a-117">**Wyślij** Automatycznie wysyła raporty wewnętrznych błędów kompilatora do firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e73a-117">**send** Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="8e73a-118">Aby włączyć tę opcję, musisz najpierw wyrazić zgodę na zasady zbierania danych firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e73a-118">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="8e73a-119">Podczas pierwszego określania **errorReport: Send** na komputerze komunikat kompilatora odwołuje się do witryny sieci Web zawierającej zasady zbierania danych firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e73a-119">The first time that you specify **-errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e73a-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8e73a-120">Remarks</span></span>

 <span data-ttu-id="8e73a-121">Wewnętrzny błąd kompilatora (lodem) powstaje, gdy kompilator nie może przetworzyć pliku kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="8e73a-121">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="8e73a-122">W przypadku wystąpienia lodu kompilator nie tworzy pliku wyjściowego ani żadnej przydatnej diagnostyki, której można użyć do naprawienia kodu.</span><span class="sxs-lookup"><span data-stu-id="8e73a-122">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>

 <span data-ttu-id="8e73a-123">W poprzednich wersjach, gdy otrzymasz lód, zachęcamy do skontaktowania się z pomocą techniczną firmy Microsoft w celu zgłoszenia problemu.</span><span class="sxs-lookup"><span data-stu-id="8e73a-123">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="8e73a-124">Za pomocą **-errorreport**, można podać informacje o lodem do zespołu Visual C#.</span><span class="sxs-lookup"><span data-stu-id="8e73a-124">By using **-errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="8e73a-125">Raporty o błędach mogą pomóc w ulepszaniu przyszłych wersji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="8e73a-125">Your error reports can help improve future compiler releases.</span></span>

 <span data-ttu-id="8e73a-126">Możliwość wysyłania raportów zależy od uprawnień komputera i użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8e73a-126">A user's ability to send reports depends on computer and user policy permissions.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="8e73a-127">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8e73a-127">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="8e73a-128">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="8e73a-128">Open the project's **Properties** page.</span></span> <span data-ttu-id="8e73a-129">Aby uzyskać więcej informacji, zobacz [stronę Kompilacja, Projektant projektu (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="8e73a-129">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>

2. <span data-ttu-id="8e73a-130">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="8e73a-130">Click the **Build** property page.</span></span>

3. <span data-ttu-id="8e73a-131">Kliknij przycisk **Zaawansowane** .</span><span class="sxs-lookup"><span data-stu-id="8e73a-131">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="8e73a-132">Zmodyfikuj właściwość **wewnętrznego raportowania błędów kompilatora** .</span><span class="sxs-lookup"><span data-stu-id="8e73a-132">Modify the **Internal Compiler Error Reporting** property.</span></span>

 <span data-ttu-id="8e73a-133">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A> .</span><span class="sxs-lookup"><span data-stu-id="8e73a-133">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e73a-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8e73a-134">See also</span></span>

- [<span data-ttu-id="8e73a-135">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="8e73a-135">C# Compiler Options</span></span>](./index.md)
