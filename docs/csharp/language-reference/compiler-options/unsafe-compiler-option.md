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
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89140844"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="46ba4-103">-unsafe (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="46ba4-103">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="46ba4-104">Opcja **niebezpiecznego** kompilatora umożliwia kompilowanie kodu, który używa [niebezpiecznego](../keywords/unsafe.md) słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="46ba4-104">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ba4-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="46ba4-105">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="46ba4-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="46ba4-106">Remarks</span></span>

<span data-ttu-id="46ba4-107">Aby uzyskać więcej informacji na temat niebezpiecznego kodu, zobacz artykuł [niebezpieczny kod i wskaźniki](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="46ba4-107">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="46ba4-108">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="46ba4-108">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="46ba4-109">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="46ba4-109">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="46ba4-110">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="46ba4-110">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="46ba4-111">Zaznacz pole wyboru **Zezwalaj na niebezpieczny kod** .</span><span class="sxs-lookup"><span data-stu-id="46ba4-111">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="46ba4-112">Aby dodać tę opcję w pliku csproj</span><span class="sxs-lookup"><span data-stu-id="46ba4-112">To add this option in a csproj file</span></span>

<span data-ttu-id="46ba4-113">Otwórz plik. csproj projektu i Dodaj następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="46ba4-113">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="46ba4-114">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A> .</span><span class="sxs-lookup"><span data-stu-id="46ba4-114">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ba4-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="46ba4-115">Example</span></span>

<span data-ttu-id="46ba4-116">Kompiluj `in.cs` dla trybu niebezpiecznego:</span><span class="sxs-lookup"><span data-stu-id="46ba4-116">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="46ba4-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="46ba4-117">See also</span></span>

- [<span data-ttu-id="46ba4-118">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="46ba4-118">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="46ba4-119">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="46ba4-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
