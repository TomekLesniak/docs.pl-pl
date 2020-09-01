---
description: -PDB (opcje kompilatora C#)
title: -PDB (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: 0dcafd0fd260488922c74a2330b312e80467e779
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124919"
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="a2e81-103">-PDB (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="a2e81-103">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="a2e81-104">**-PDB —** opcja kompilatora określa nazwę i lokalizację pliku symboli debugowania.</span><span class="sxs-lookup"><span data-stu-id="a2e81-104">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2e81-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a2e81-105">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="a2e81-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="a2e81-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="a2e81-107">Nazwa i lokalizacja pliku symboli debugowania.</span><span class="sxs-lookup"><span data-stu-id="a2e81-107">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2e81-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a2e81-108">Remarks</span></span>  
 <span data-ttu-id="a2e81-109">Jeśli określisz polecenie [-debug (opcje kompilatora C#)](./debug-compiler-option.md), kompilator utworzy plik. pdb w tym samym katalogu, w którym kompilator utworzy plik wyjściowy (. exe lub. dll) z nazwą pliku, która jest taka sama jak nazwa pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="a2e81-109">When you specify [-debug (C# Compiler Options)](./debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="a2e81-110">**-PDB** umożliwia określenie niedomyślnej nazwy pliku i lokalizacji dla pliku. pdb.</span><span class="sxs-lookup"><span data-stu-id="a2e81-110">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="a2e81-111">Nie można ustawić tej opcji kompilatora w środowisku deweloperskim programu Visual Studio, ani programowo zmienić.</span><span class="sxs-lookup"><span data-stu-id="a2e81-111">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2e81-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="a2e81-112">Example</span></span>  
 <span data-ttu-id="a2e81-113">Kompiluj `t.cs` i Utwórz plik. pdb o nazwie TT. pdb:</span><span class="sxs-lookup"><span data-stu-id="a2e81-113">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2e81-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a2e81-114">See also</span></span>

- [<span data-ttu-id="a2e81-115">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="a2e81-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a2e81-116">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="a2e81-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
