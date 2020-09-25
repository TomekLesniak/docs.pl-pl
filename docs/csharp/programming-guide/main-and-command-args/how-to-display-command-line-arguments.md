---
title: Jak wyświetlić argumenty wiersza polecenia — Przewodnik programowania w języku C#
description: Dowiedz się, jak wyświetlać argumenty wiersza polecenia. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 717e27c23724e63c03a38b028ef99dc6530b4745
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195483"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="b1ed1-104">Wyświetlanie argumentów wiersza polecenia (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="b1ed1-104">How to display command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="b1ed1-105">Argumenty dostarczone do pliku wykonywalnego w wierszu polecenia są dostępne za pomocą opcjonalnego parametru do `Main` .</span><span class="sxs-lookup"><span data-stu-id="b1ed1-105">Arguments provided to an executable on the command line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="b1ed1-106">Argumenty są podane w postaci tablicy ciągów.</span><span class="sxs-lookup"><span data-stu-id="b1ed1-106">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="b1ed1-107">Każdy element tablicy zawiera jeden argument.</span><span class="sxs-lookup"><span data-stu-id="b1ed1-107">Each element of the array contains one argument.</span></span> <span data-ttu-id="b1ed1-108">Odstęp między argumentami jest usuwany.</span><span class="sxs-lookup"><span data-stu-id="b1ed1-108">White-space between arguments is removed.</span></span> <span data-ttu-id="b1ed1-109">Rozważmy na przykład następujące wywołania wiersza polecenia fikcyjnego pliku wykonywalnego:</span><span class="sxs-lookup"><span data-stu-id="b1ed1-109">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="b1ed1-110">Dane wejściowe w wierszu polecenia</span><span class="sxs-lookup"><span data-stu-id="b1ed1-110">Input on command line</span></span>|<span data-ttu-id="b1ed1-111">Tablica ciągów przeniesiona do głównej</span><span class="sxs-lookup"><span data-stu-id="b1ed1-111">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="b1ed1-112">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="b1ed1-112">**executable.exe a b c**</span></span>|<span data-ttu-id="b1ed1-113">z</span><span class="sxs-lookup"><span data-stu-id="b1ed1-113">"a"</span></span><br /><br /> <span data-ttu-id="b1ed1-114">b</span><span class="sxs-lookup"><span data-stu-id="b1ed1-114">"b"</span></span><br /><br /> <span data-ttu-id="b1ed1-115">s</span><span class="sxs-lookup"><span data-stu-id="b1ed1-115">"c"</span></span>|  
|<span data-ttu-id="b1ed1-116">**executable.exe 1 2**</span><span class="sxs-lookup"><span data-stu-id="b1ed1-116">**executable.exe one two**</span></span>|<span data-ttu-id="b1ed1-117">je</span><span class="sxs-lookup"><span data-stu-id="b1ed1-117">"one"</span></span><br /><br /> <span data-ttu-id="b1ed1-118">tymi</span><span class="sxs-lookup"><span data-stu-id="b1ed1-118">"two"</span></span>|  
|<span data-ttu-id="b1ed1-119">**executable.exe "1 2" trzy**</span><span class="sxs-lookup"><span data-stu-id="b1ed1-119">**executable.exe "one two" three**</span></span>|<span data-ttu-id="b1ed1-120">„one two”</span><span class="sxs-lookup"><span data-stu-id="b1ed1-120">"one two"</span></span><br /><br /> <span data-ttu-id="b1ed1-121">trzecim</span><span class="sxs-lookup"><span data-stu-id="b1ed1-121">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b1ed1-122">W przypadku uruchamiania aplikacji w programie Visual Studio, można określić argumenty wiersza polecenia na [stronie debugowanie, Projektant projektu](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="b1ed1-122">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1ed1-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="b1ed1-123">Example</span></span>  

 <span data-ttu-id="b1ed1-124">Ten przykład wyświetla argumenty wiersza polecenia przekazane do aplikacji wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="b1ed1-124">This example displays the command-line arguments passed to a command-line application.</span></span> <span data-ttu-id="b1ed1-125">Wyświetlane dane wyjściowe dotyczą pierwszego wpisu w powyższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="b1ed1-125">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="b1ed1-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1ed1-126">See also</span></span>

- [<span data-ttu-id="b1ed1-127">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="b1ed1-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b1ed1-128">Kompilacja za pomocą wiersza polecenia przy użyciu csc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ed1-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="b1ed1-129">Main () i argumenty wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="b1ed1-129">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="b1ed1-130">Main() — Zwracane wartości</span><span class="sxs-lookup"><span data-stu-id="b1ed1-130">Main() Return Values</span></span>](./main-return-values.md)
