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
ms.openlocfilehash: 4c812314ed9c1abcd7d2f34b2281140175621312
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125959"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="31a8d-103">-CodePage (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="31a8d-103">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="31a8d-104">Ta opcja określa, która strona kodowa ma być używana podczas kompilacji, jeśli wymagana Strona nie jest bieżącą domyślną stroną kodową systemu.</span><span class="sxs-lookup"><span data-stu-id="31a8d-104">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31a8d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="31a8d-105">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="31a8d-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="31a8d-106">Arguments</span></span>  
 `id`  
 <span data-ttu-id="31a8d-107">Identyfikator strony kodowej, który ma być używany dla wszystkich plików kodu źródłowego w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="31a8d-107">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31a8d-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="31a8d-108">Remarks</span></span>  
 <span data-ttu-id="31a8d-109">Kompilator spróbuje najpierw zinterpretować wszystkie pliki źródłowe jako UTF-8.</span><span class="sxs-lookup"><span data-stu-id="31a8d-109">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="31a8d-110">Jeśli pliki kodu źródłowego są w kodowaniu innym niż UTF-8 i są używane znaki inne niż 7-bitowe znaki ASCII, użyj opcji **-CodePage** , aby określić, która strona kodowa powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="31a8d-110">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="31a8d-111">**-CodePage** stosuje się do wszystkich plików kodu źródłowego w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="31a8d-111">**-codepage** applies to all source code files in your compilation.</span></span>  

 <span data-ttu-id="31a8d-112">Zobacz [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) , aby uzyskać informacje na temat sposobu znajdowania, które strony kodowe są obsługiwane w systemie.</span><span class="sxs-lookup"><span data-stu-id="31a8d-112">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="31a8d-113">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="31a8d-113">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a8d-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="31a8d-114">See also</span></span>

- [<span data-ttu-id="31a8d-115">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="31a8d-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="31a8d-116">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="31a8d-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
