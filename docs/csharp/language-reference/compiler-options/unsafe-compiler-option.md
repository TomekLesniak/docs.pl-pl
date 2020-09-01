---
description: -unsafe (opcje kompilatora C#)
title: -unsafe (opcje kompilatora C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 0f6d94dd25a020d96430746c4b5e7aefd0f679da
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140844"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="d7d84-103">-unsafe (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="d7d84-103">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="d7d84-104">Opcja **niebezpiecznego** kompilatora umożliwia kompilowanie kodu, który używa [niebezpiecznego](../keywords/unsafe.md) słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="d7d84-104">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d84-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d7d84-105">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="d7d84-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d7d84-106">Remarks</span></span>

<span data-ttu-id="d7d84-107">Aby uzyskać więcej informacji na temat niebezpiecznego kodu, zobacz artykuł [niebezpieczny kod i wskaźniki](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="d7d84-107">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d7d84-108">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d7d84-108">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="d7d84-109">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="d7d84-109">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="d7d84-110">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="d7d84-110">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="d7d84-111">Zaznacz pole wyboru **Zezwalaj na niebezpieczny kod** .</span><span class="sxs-lookup"><span data-stu-id="d7d84-111">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="d7d84-112">Aby dodać tę opcję w pliku csproj</span><span class="sxs-lookup"><span data-stu-id="d7d84-112">To add this option in a csproj file</span></span>

<span data-ttu-id="d7d84-113">Otwórz plik. csproj projektu i Dodaj następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="d7d84-113">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="d7d84-114">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A> .</span><span class="sxs-lookup"><span data-stu-id="d7d84-114">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d84-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="d7d84-115">Example</span></span>

<span data-ttu-id="d7d84-116">Kompiluj `in.cs` dla trybu niebezpiecznego:</span><span class="sxs-lookup"><span data-stu-id="d7d84-116">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7d84-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d7d84-117">See also</span></span>

- [<span data-ttu-id="d7d84-118">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="d7d84-118">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="d7d84-119">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="d7d84-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
