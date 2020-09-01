---
description: Opcje kompilatora C#
title: Opcje kompilatora C#
ms.date: 08/28/2020
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: 502bd83ae52be9ae2f914847bb6bf7c7f2a0c411
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271818"
---
# <a name="c-compiler-options"></a><span data-ttu-id="0ba4f-103">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="0ba4f-103">C# Compiler Options</span></span>

<span data-ttu-id="0ba4f-104">Kompilator tworzy pliki wykonywalne (. exe), biblioteki dołączane dynamicznie (dll) lub moduły kodu (. module).</span><span class="sxs-lookup"><span data-stu-id="0ba4f-104">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="0ba4f-105">Każda opcja kompilatora jest dostępna w dwóch formach: **-Option** i **Option**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-105">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="0ba4f-106">W dokumentacji jest wyświetlany tylko formularz **-opcja** .</span><span class="sxs-lookup"><span data-stu-id="0ba4f-106">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="0ba4f-107">W programie Visual Studio opcje kompilatora są ustawiane w pliku *web.config* .</span><span class="sxs-lookup"><span data-stu-id="0ba4f-107">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="0ba4f-108">Aby uzyskać więcej informacji, zobacz [ \<compiler> element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="0ba4f-108">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0ba4f-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="0ba4f-109">In this section</span></span>

- <span data-ttu-id="0ba4f-110">[Kompilowanie wiersza polecenia przy użyciu csc.exe](command-line-building-with-csc-exe.md) Informacje na temat tworzenia aplikacji Visual C# z poziomu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-110">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="0ba4f-111">[Jak ustawić zmienne środowiskowe dla wiersza polecenia programu Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Zawiera kroki umożliwiające uruchomienie *VsDevCmd.bat* w celu włączenia kompilacji w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-111">[How to set environment variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *VsDevCmd.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="0ba4f-112">[Opcje kompilatora C# na liście według kategorii](listed-by-category.md) Kategorii listę opcji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-112">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="0ba4f-113">[Opcje kompilatora C# w porządku alfabetycznym](listed-alphabetically.md) Alfabetyczna lista opcji kompilatora.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-113">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="0ba4f-114">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="0ba4f-114">Related sections</span></span>

- <span data-ttu-id="0ba4f-115">[Strona kompilacja, Projektant projektu](/visualstudio/ide/reference/build-page-project-designer-csharp) Ustawianie właściwości, które określają, jak projekt jest kompilowany, skompilowany i debugowany.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-115">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="0ba4f-116">Zawiera informacje o niestandardowych krokach kompilacji w projektach Visual C#.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-116">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="0ba4f-117">[Domyślne i niestandardowe kompilacje](/visualstudio/ide/compiling-and-building-in-visual-studio) Informacje o typach i konfiguracjach kompilacji.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-117">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="0ba4f-118">[Przygotowywanie kompilacji i zarządzanie nimi](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedury kompilowania w środowisku deweloperskim programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-118">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
