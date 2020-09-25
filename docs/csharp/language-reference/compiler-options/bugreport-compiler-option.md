---
description: -bugreport (opcje kompilatora C#)
title: -bugreport (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 2afab44eec0c7bcc9809b458be0348093cb6dd07
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196822"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="f15c3-103">-bugreport (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="f15c3-103">-bugreport (C# Compiler Options)</span></span>

<span data-ttu-id="f15c3-104">Określa, że informacje debugowania należy umieścić w pliku do późniejszej analizy.</span><span class="sxs-lookup"><span data-stu-id="f15c3-104">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f15c3-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f15c3-105">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="f15c3-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="f15c3-106">Arguments</span></span>  

 `file`  
 <span data-ttu-id="f15c3-107">Nazwa pliku, który ma zawierać raport o błędach.</span><span class="sxs-lookup"><span data-stu-id="f15c3-107">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f15c3-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f15c3-108">Remarks</span></span>  

 <span data-ttu-id="f15c3-109">Opcja **-bugreport** określa, że należy umieścić następujące informacje `file` :</span><span class="sxs-lookup"><span data-stu-id="f15c3-109">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="f15c3-110">Kopia wszystkich plików kodu źródłowego w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="f15c3-110">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="f15c3-111">Lista opcji kompilatora używanych w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="f15c3-111">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="f15c3-112">Informacje o wersji dotyczące kompilatora, czasu wykonywania i systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="f15c3-112">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="f15c3-113">Przywoływane zestawy i moduły, zapisane w postaci cyfr szesnastkowych, z wyjątkiem zestawów, które są dostarczane z .NET Framework i zestawem SDK.</span><span class="sxs-lookup"><span data-stu-id="f15c3-113">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
- <span data-ttu-id="f15c3-114">Dane wyjściowe kompilatora, jeśli istnieją.</span><span class="sxs-lookup"><span data-stu-id="f15c3-114">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="f15c3-115">Opis problemu, dla którego zostanie wyświetlony monit.</span><span class="sxs-lookup"><span data-stu-id="f15c3-115">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="f15c3-116">Opis sposobu, w jaki sądzisz, że problem powinien zostać naprawiony, zostanie wyświetlony monit.</span><span class="sxs-lookup"><span data-stu-id="f15c3-116">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="f15c3-117">Jeśli ta opcja jest używana z poleceniem **-errorReport: Prompt** lub **-errorReport: Send**, informacje w pliku będą wysyłane do firmy Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="f15c3-117">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="f15c3-118">Ze względu na to, że kopia wszystkich plików kodu źródłowego zostanie umieszczona w programie `file` , może być konieczne odtworzenie podejrzanej wady kodu w najkrótszym możliwym programie.</span><span class="sxs-lookup"><span data-stu-id="f15c3-118">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="f15c3-119">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="f15c3-119">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="f15c3-120">Zauważ, że zawartość wygenerowanego pliku uwidacznia kod źródłowy, który może spowodować nieumyślne ujawnienie informacji.</span><span class="sxs-lookup"><span data-stu-id="f15c3-120">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f15c3-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f15c3-121">See also</span></span>

- [<span data-ttu-id="f15c3-122">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="f15c3-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f15c3-123">-errorreport (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="f15c3-123">-errorreport (C# Compiler Options)</span></span>](./errorreport-compiler-option.md)
- [<span data-ttu-id="f15c3-124">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="f15c3-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
