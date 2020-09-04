---
description: -BaseAddress (opcje kompilatora C#)
title: -BaseAddress (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: f79ee449eafd04906dab49700a1af6441d54cece
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89464886"
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="96475-103">-BaseAddress (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="96475-103">-baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="96475-104">Opcja **-BaseAddress** pozwala określić preferowany adres podstawowy, przy użyciu którego ma zostać ZAŁADOWANA Biblioteka DLL.</span><span class="sxs-lookup"><span data-stu-id="96475-104">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="96475-105">Aby uzyskać więcej informacji na temat tego, kiedy i dlaczego należy używać tej opcji, zobacz [dziennik sieci Web Larry Osterman](https://docs.microsoft.com/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span><span class="sxs-lookup"><span data-stu-id="96475-105">For more information about when and why to use this option, see [Larry Osterman's WebLog](https://docs.microsoft.com/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96475-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="96475-106">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="96475-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="96475-107">Arguments</span></span>  
 `address`  
 <span data-ttu-id="96475-108">Adres podstawowy biblioteki DLL.</span><span class="sxs-lookup"><span data-stu-id="96475-108">The base address for the DLL.</span></span> <span data-ttu-id="96475-109">Ten adres można określić jako liczbę dziesiętną, szesnastkową lub ósemkową.</span><span class="sxs-lookup"><span data-stu-id="96475-109">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96475-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="96475-110">Remarks</span></span>  
 <span data-ttu-id="96475-111">Domyślny adres podstawowy dla biblioteki DLL jest ustawiany przez środowisko uruchomieniowe języka wspólnego platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="96475-111">The default base address for a DLL is set by the .NET common language runtime.</span></span>  
  
 <span data-ttu-id="96475-112">Należy pamiętać, że Dolna kolejność wyrazów w tym adresie zostanie zaokrąglona.</span><span class="sxs-lookup"><span data-stu-id="96475-112">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="96475-113">Na przykład, jeśli określisz 0x11110001, zostanie ona zaokrąglona do 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="96475-113">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="96475-114">Aby ukończyć proces podpisywania dla biblioteki DLL, użyj SN.EXE z opcją-R.</span><span class="sxs-lookup"><span data-stu-id="96475-114">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="96475-115">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96475-115">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="96475-116">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="96475-116">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="96475-117">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="96475-117">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="96475-118">Kliknij przycisk **Zaawansowane** .</span><span class="sxs-lookup"><span data-stu-id="96475-118">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="96475-119">Zmodyfikuj właściwość **adresu podstawowego biblioteki DLL** .</span><span class="sxs-lookup"><span data-stu-id="96475-119">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="96475-120">Aby programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A> .</span><span class="sxs-lookup"><span data-stu-id="96475-120">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96475-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="96475-121">See also</span></span>

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [<span data-ttu-id="96475-122">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="96475-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="96475-123">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="96475-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
