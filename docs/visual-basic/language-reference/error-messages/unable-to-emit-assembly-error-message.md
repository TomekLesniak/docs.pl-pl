---
title: 'Nie można wyemitować zestawu: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: c088f273c100b1a7eefcf74047865093f378e970
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161663"
---
# <a name="bc30145-unable-to-emit-assembly-error-message"></a><span data-ttu-id="b99e7-102">BC30145: nie można wyemitować zestawu: \<error message></span><span class="sxs-lookup"><span data-stu-id="b99e7-102">BC30145: Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="b99e7-103">Kompilator Visual Basic wywołuje konsolidator zestawu (*Al.exe*, znany również jako ALink) w celu wygenerowania zestawu z manifestem, a konsolidator raportuje błąd w fazie emisji tworzenia zestawu.</span><span class="sxs-lookup"><span data-stu-id="b99e7-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="b99e7-104">**Identyfikator błędu:** BC30145</span><span class="sxs-lookup"><span data-stu-id="b99e7-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b99e7-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="b99e7-105">To correct this error</span></span>

1. <span data-ttu-id="b99e7-106">Sprawdź cytowany komunikat o błędzie i zapoznaj się z tematem [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) w celu uzyskania dalszych wyjaśnień i porad.</span><span class="sxs-lookup"><span data-stu-id="b99e7-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="b99e7-107">Spróbuj podpisać zestaw ręcznie przy użyciu [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) lub [Sn.exe (narzędzia silnej nazwy)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="b99e7-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="b99e7-108">Jeśli błąd będzie się powtarzać, Zbierz informacje o okolicznościach i powiadom usługi pomocy technicznej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b99e7-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="b99e7-109">Aby ręcznie podpisać zestaw</span><span class="sxs-lookup"><span data-stu-id="b99e7-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="b99e7-110">Użyj [Sn.exe (Narzędzie silnej nazwy)](../../../framework/tools/sn-exe-strong-name-tool.md), aby utworzyć plik pary kluczy publicznych/prywatnych.</span><span class="sxs-lookup"><span data-stu-id="b99e7-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="b99e7-111">Ten plik ma rozszerzenie *. snk* .</span><span class="sxs-lookup"><span data-stu-id="b99e7-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="b99e7-112">Usuń odwołanie COM, które generuje błąd z projektu.</span><span class="sxs-lookup"><span data-stu-id="b99e7-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="b99e7-113">Otwórz [wiersz polecenia dla deweloperów dla programu Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b99e7-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="b99e7-114">W systemie Windows 10 wprowadź **wiersz polecenia programisty** w polu wyszukiwania na pasku zadań.</span><span class="sxs-lookup"><span data-stu-id="b99e7-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="b99e7-115">Następnie wybierz pozycję **wiersz polecenia dla deweloperów dla programu VS 2017** z listy wyników.</span><span class="sxs-lookup"><span data-stu-id="b99e7-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="b99e7-116">Zmień katalog na katalog, w którym chcesz umieścić otokę zestawu.</span><span class="sxs-lookup"><span data-stu-id="b99e7-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="b99e7-117">Wprowadź następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="b99e7-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="b99e7-118">Przykładem rzeczywistego polecenia, które można wprowadzić:</span><span class="sxs-lookup"><span data-stu-id="b99e7-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="b99e7-119">Jeśli ścieżka lub plik zawiera spacje, należy użyć podwójnych cudzysłowów.</span><span class="sxs-lookup"><span data-stu-id="b99e7-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="b99e7-120">W programie Visual Studio Dodaj odwołanie do zestawu .NET do pliku, który właśnie został utworzony.</span><span class="sxs-lookup"><span data-stu-id="b99e7-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="b99e7-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b99e7-121">See also</span></span>

- [<span data-ttu-id="b99e7-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="b99e7-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="b99e7-123">Sn.exe (Narzędzie silnej nazwy)</span><span class="sxs-lookup"><span data-stu-id="b99e7-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="b99e7-124">Instrukcje: Tworzenie pary kluczy Public-Private</span><span class="sxs-lookup"><span data-stu-id="b99e7-124">How to: Create a Public-Private Key Pair</span></span>](../../../standard/assembly/create-public-private-key-pair.md)
- [<span data-ttu-id="b99e7-125">Porozmawiaj z nami</span><span class="sxs-lookup"><span data-stu-id="b99e7-125">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
