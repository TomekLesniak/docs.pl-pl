---
description: -warn (opcje kompilatora C#)
title: -warn (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 55e80d0bd05e2119154210503bb277d743050e18
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139076"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="de71c-103">-warn (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="de71c-103">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="de71c-104">Opcja **-warn** określa poziom ostrzeżeń dla kompilatora, który ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="de71c-104">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de71c-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="de71c-105">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="de71c-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="de71c-106">Arguments</span></span>  
 `option`  
 <span data-ttu-id="de71c-107">Poziom ostrzeżeń, który ma być wyświetlany dla kompilacji: niższe numery zawierają tylko ostrzeżenia o wysokiej ważności; wyższe liczby zawierają więcej ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="de71c-107">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="de71c-108">Wartość musi być równa zero lub dodatnia liczba całkowita:</span><span class="sxs-lookup"><span data-stu-id="de71c-108">The value must be zero or a positive integer:</span></span>

|<span data-ttu-id="de71c-109">Poziom ostrzeżeń</span><span class="sxs-lookup"><span data-stu-id="de71c-109">Warning level</span></span>|<span data-ttu-id="de71c-110">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="de71c-110">Meaning</span></span>|
|-------------------|-------------|
|<span data-ttu-id="de71c-111">0</span><span class="sxs-lookup"><span data-stu-id="de71c-111">0</span></span>|<span data-ttu-id="de71c-112">Wyłącza emisję wszystkich komunikatów ostrzegawczych.</span><span class="sxs-lookup"><span data-stu-id="de71c-112">Turns off emission of all warning messages.</span></span>|
|<span data-ttu-id="de71c-113">1</span><span class="sxs-lookup"><span data-stu-id="de71c-113">1</span></span>|<span data-ttu-id="de71c-114">Wyświetla poważne komunikaty ostrzegawcze.</span><span class="sxs-lookup"><span data-stu-id="de71c-114">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="de71c-115">2</span><span class="sxs-lookup"><span data-stu-id="de71c-115">2</span></span>|<span data-ttu-id="de71c-116">Wyświetla ostrzeżenia poziomu 1 i pewne mniej surowe ostrzeżenia, takie jak ostrzeżenia dotyczące ukrywania elementów członkowskich klasy.</span><span class="sxs-lookup"><span data-stu-id="de71c-116">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="de71c-117">3</span><span class="sxs-lookup"><span data-stu-id="de71c-117">3</span></span>|<span data-ttu-id="de71c-118">Wyświetla ostrzeżenia poziomu 2 oraz pewne mniej surowe ostrzeżenia, takie jak ostrzeżenia dotyczące wyrażeń, które zawsze są oceniane do `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="de71c-118">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="de71c-119">4 (wartość domyślna)</span><span class="sxs-lookup"><span data-stu-id="de71c-119">4 (the default)</span></span>|<span data-ttu-id="de71c-120">Wyświetla wszystkie ostrzeżenia poziomu 3 i ostrzeżenia informacyjne.</span><span class="sxs-lookup"><span data-stu-id="de71c-120">Displays all level 3 warnings plus informational warnings.</span></span>|
|<span data-ttu-id="de71c-121">5</span><span class="sxs-lookup"><span data-stu-id="de71c-121">5</span></span>|<span data-ttu-id="de71c-122">Wyświetla ostrzeżenia poziomu 4 oraz [dodatkowe ostrzeżenia](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) z kompilatora dostarczonego z C# 9,0.</span><span class="sxs-lookup"><span data-stu-id="de71c-122">Displays level 4 warnings plus [additional warnings](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) from the compiler shipped with C# 9.0.</span></span>|
|<span data-ttu-id="de71c-123">Większe niż 5</span><span class="sxs-lookup"><span data-stu-id="de71c-123">Greater than 5</span></span>|<span data-ttu-id="de71c-124">Każda wartość większa niż 5 będzie traktowana jako 5.</span><span class="sxs-lookup"><span data-stu-id="de71c-124">Any value greater than 5 will be treated as 5.</span></span> <span data-ttu-id="de71c-125">Zwykle umieszcza się dowolne duże wartości (na przykład `9999` ), aby zawsze były wyświetlane ostrzeżenia, jeśli kompilator jest aktualizowany przy użyciu nowych poziomów ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="de71c-125">You generally put arbitrary large value (for example, `9999`) to make sure you always have all warnings if the compiler is updated with new warning levels.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="de71c-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="de71c-126">Remarks</span></span>  
 <span data-ttu-id="de71c-127">Aby uzyskać informacje o błędzie lub ostrzeżeniu, można wyszukać kod błędu w indeksie pomocy.</span><span class="sxs-lookup"><span data-stu-id="de71c-127">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="de71c-128">Aby uzyskać informacje dotyczące błędu lub ostrzeżenia, zobacz [Błędy kompilatora języka C#](../compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="de71c-128">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="de71c-129">Użyj opcji [-warnaserror —](./warnaserror-compiler-option.md) , aby traktować wszystkie ostrzeżenia jako błędy.</span><span class="sxs-lookup"><span data-stu-id="de71c-129">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="de71c-130">Użyj [-nowarn](./nowarn-compiler-option.md) , aby wyłączyć niektóre ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="de71c-130">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="de71c-131">**-w** jest krótką formą **-warn**.</span><span class="sxs-lookup"><span data-stu-id="de71c-131">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="de71c-132">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="de71c-132">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="de71c-133">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="de71c-133">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="de71c-134">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="de71c-134">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="de71c-135">Zmodyfikuj właściwość **poziom ostrzeżeń** .</span><span class="sxs-lookup"><span data-stu-id="de71c-135">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="de71c-136">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A> .</span><span class="sxs-lookup"><span data-stu-id="de71c-136">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de71c-137">Przykład</span><span class="sxs-lookup"><span data-stu-id="de71c-137">Example</span></span>  
 <span data-ttu-id="de71c-138">Kompiluj `in.cs` i czy kompilator wyświetla tylko ostrzeżenia poziomu 1:</span><span class="sxs-lookup"><span data-stu-id="de71c-138">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="de71c-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="de71c-139">See also</span></span>

- [<span data-ttu-id="de71c-140">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="de71c-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="de71c-141">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="de71c-141">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
