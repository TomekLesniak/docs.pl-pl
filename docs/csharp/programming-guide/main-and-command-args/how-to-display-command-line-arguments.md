---
title: Jak wyświetlić argumenty wiersza polecenia — Przewodnik programowania w języku C#
description: Dowiedz się, jak wyświetlać argumenty wiersza polecenia. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 1ac5dc5a5f4e974c9202d2ce23f61071494e1977
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381817"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="ba16f-104">Wyświetlanie argumentów wiersza polecenia (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="ba16f-104">How to display command-line arguments (C# Programming Guide)</span></span>
<span data-ttu-id="ba16f-105">Argumenty dostarczone do pliku wykonywalnego w wierszu polecenia są dostępne za pomocą opcjonalnego parametru do `Main` .</span><span class="sxs-lookup"><span data-stu-id="ba16f-105">Arguments provided to an executable on the command line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="ba16f-106">Argumenty są podane w postaci tablicy ciągów.</span><span class="sxs-lookup"><span data-stu-id="ba16f-106">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="ba16f-107">Każdy element tablicy zawiera jeden argument.</span><span class="sxs-lookup"><span data-stu-id="ba16f-107">Each element of the array contains one argument.</span></span> <span data-ttu-id="ba16f-108">Odstęp między argumentami jest usuwany.</span><span class="sxs-lookup"><span data-stu-id="ba16f-108">White-space between arguments is removed.</span></span> <span data-ttu-id="ba16f-109">Rozważmy na przykład następujące wywołania wiersza polecenia fikcyjnego pliku wykonywalnego:</span><span class="sxs-lookup"><span data-stu-id="ba16f-109">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="ba16f-110">Dane wejściowe w wierszu polecenia</span><span class="sxs-lookup"><span data-stu-id="ba16f-110">Input on command line</span></span>|<span data-ttu-id="ba16f-111">Tablica ciągów przeniesiona do głównej</span><span class="sxs-lookup"><span data-stu-id="ba16f-111">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="ba16f-112">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="ba16f-112">**executable.exe a b c**</span></span>|<span data-ttu-id="ba16f-113">z</span><span class="sxs-lookup"><span data-stu-id="ba16f-113">"a"</span></span><br /><br /> <span data-ttu-id="ba16f-114">b</span><span class="sxs-lookup"><span data-stu-id="ba16f-114">"b"</span></span><br /><br /> <span data-ttu-id="ba16f-115">s</span><span class="sxs-lookup"><span data-stu-id="ba16f-115">"c"</span></span>|  
|<span data-ttu-id="ba16f-116">**executable.exe 1 2**</span><span class="sxs-lookup"><span data-stu-id="ba16f-116">**executable.exe one two**</span></span>|<span data-ttu-id="ba16f-117">je</span><span class="sxs-lookup"><span data-stu-id="ba16f-117">"one"</span></span><br /><br /> <span data-ttu-id="ba16f-118">tymi</span><span class="sxs-lookup"><span data-stu-id="ba16f-118">"two"</span></span>|  
|<span data-ttu-id="ba16f-119">**executable.exe "1 2" trzy**</span><span class="sxs-lookup"><span data-stu-id="ba16f-119">**executable.exe "one two" three**</span></span>|<span data-ttu-id="ba16f-120">„one two”</span><span class="sxs-lookup"><span data-stu-id="ba16f-120">"one two"</span></span><br /><br /> <span data-ttu-id="ba16f-121">trzecim</span><span class="sxs-lookup"><span data-stu-id="ba16f-121">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="ba16f-122">W przypadku uruchamiania aplikacji w programie Visual Studio, można określić argumenty wiersza polecenia na [stronie debugowanie, Projektant projektu](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="ba16f-122">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba16f-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="ba16f-123">Example</span></span>  
 <span data-ttu-id="ba16f-124">Ten przykład wyświetla argumenty wiersza polecenia przekazane do aplikacji wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="ba16f-124">This example displays the command-line arguments passed to a command-line application.</span></span> <span data-ttu-id="ba16f-125">Wyświetlane dane wyjściowe dotyczą pierwszego wpisu w powyższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="ba16f-125">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="ba16f-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ba16f-126">See also</span></span>

- [<span data-ttu-id="ba16f-127">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ba16f-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ba16f-128">Kompilacja za pomocą wiersza polecenia przy użyciu csc.exe</span><span class="sxs-lookup"><span data-stu-id="ba16f-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="ba16f-129">Main () i argumenty wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="ba16f-129">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="ba16f-130">Main() — Zwracane wartości</span><span class="sxs-lookup"><span data-stu-id="ba16f-130">Main() Return Values</span></span>](./main-return-values.md)
