---
description: -publicsign (opcje kompilatora C#)
title: -publicsign (opcje kompilatora C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 525912c7f50aa6b51e602be7b9258f1f5907daac
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124815"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="e2bad-103">-publicsign (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="e2bad-103">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="e2bad-104">Ta opcja powoduje, że kompilator zastosuje klucz publiczny, ale w rzeczywistości nie podpisze zestawu.</span><span class="sxs-lookup"><span data-stu-id="e2bad-104">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="e2bad-105">Opcja **-publicsign** ustawia również bit w zestawie, który informuje środowisko uruchomieniowe, że plik jest rzeczywiście podpisany.</span><span class="sxs-lookup"><span data-stu-id="e2bad-105">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="e2bad-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="e2bad-106">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="e2bad-107">Argumenty</span><span class="sxs-lookup"><span data-stu-id="e2bad-107">Arguments</span></span>

<span data-ttu-id="e2bad-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="e2bad-108">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2bad-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e2bad-109">Remarks</span></span>

<span data-ttu-id="e2bad-110">Opcja **-publicsign** wymaga użycia elementu [-KeyFile](keyfile-compiler-option.md) lub [-containerer](keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e2bad-110">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="e2bad-111">Opcje **KeyFile** lub **containerer** określają klucz publiczny.</span><span class="sxs-lookup"><span data-stu-id="e2bad-111">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="e2bad-112">Opcje **-publicsign** i **-delaysign** wykluczają się wzajemnie.</span><span class="sxs-lookup"><span data-stu-id="e2bad-112">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="e2bad-113">Czasami nazywane "fałszywym znakiem" lub "OSS Sign", podpisywanie publiczne obejmuje klucz publiczny w zestawie danych wyjściowych i ustawia flagę "podpisane", ale w rzeczywistości nie podpisuje zestawu przy użyciu klucza prywatnego.</span><span class="sxs-lookup"><span data-stu-id="e2bad-113">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="e2bad-114">Jest to przydatne w przypadku projektów open source, w których osoby chcą tworzyć zestawy, które są zgodne z opublikowanymi "w pełni podpisanymi", ale nie mają dostępu do klucza prywatnego używanego do podpisywania zestawów.</span><span class="sxs-lookup"><span data-stu-id="e2bad-114">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="e2bad-115">Ponieważ niemal żaden konsument nie musi sprawdzić, czy zestaw jest w pełni podpisany, te publicznie skompilowane zestawy są dostępne w prawie każdym scenariuszu, w którym zostanie użyty całkowicie podpisany.</span><span class="sxs-lookup"><span data-stu-id="e2bad-115">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a><span data-ttu-id="e2bad-116">Aby ustawić tę opcję kompilatora w pliku csproj</span><span class="sxs-lookup"><span data-stu-id="e2bad-116">To set this compiler option in a csproj file</span></span>

<span data-ttu-id="e2bad-117">Otwórz plik. csproj projektu i Dodaj następujący element:</span><span class="sxs-lookup"><span data-stu-id="e2bad-117">Open the .csproj file for a project, and add the following element:</span></span>

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a><span data-ttu-id="e2bad-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e2bad-118">See also</span></span>

- [<span data-ttu-id="e2bad-119">Kompilator języka C# — opcja delaysign</span><span class="sxs-lookup"><span data-stu-id="e2bad-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="e2bad-120">Kompilator języka C# — opcja keyfile</span><span class="sxs-lookup"><span data-stu-id="e2bad-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="e2bad-121">Kompilator języka C# — opcja kontenera</span><span class="sxs-lookup"><span data-stu-id="e2bad-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="e2bad-122">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="e2bad-122">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="e2bad-123">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="e2bad-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
