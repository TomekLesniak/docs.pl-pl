---
description: -CodePage (opcje kompilatora C#)
title: -CodePage (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: eda4ce5604beb25ae2d72ac94fbbe7dde9695820
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196809"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="a2130-103">-CodePage (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="a2130-103">-codepage (C# Compiler Options)</span></span>

<span data-ttu-id="a2130-104">Ta opcja określa, która strona kodowa ma być używana podczas kompilacji, jeśli wymagana Strona nie jest bieżącą domyślną stroną kodową systemu.</span><span class="sxs-lookup"><span data-stu-id="a2130-104">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2130-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a2130-105">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="a2130-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="a2130-106">Arguments</span></span>  

 `id`  
 <span data-ttu-id="a2130-107">Identyfikator strony kodowej, który ma być używany dla wszystkich plików kodu źródłowego w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="a2130-107">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2130-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a2130-108">Remarks</span></span>  

 <span data-ttu-id="a2130-109">Kompilator spróbuje najpierw zinterpretować wszystkie pliki źródłowe jako UTF-8.</span><span class="sxs-lookup"><span data-stu-id="a2130-109">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="a2130-110">Jeśli pliki kodu źródłowego są w kodowaniu innym niż UTF-8 i są używane znaki inne niż 7-bitowe znaki ASCII, użyj opcji **-CodePage** , aby określić, która strona kodowa powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="a2130-110">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="a2130-111">**-CodePage** stosuje się do wszystkich plików kodu źródłowego w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="a2130-111">**-codepage** applies to all source code files in your compilation.</span></span>  

 <span data-ttu-id="a2130-112">Zobacz [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) , aby uzyskać informacje na temat sposobu znajdowania, które strony kodowe są obsługiwane w systemie.</span><span class="sxs-lookup"><span data-stu-id="a2130-112">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="a2130-113">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="a2130-113">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2130-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a2130-114">See also</span></span>

- [<span data-ttu-id="a2130-115">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="a2130-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a2130-116">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="a2130-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
