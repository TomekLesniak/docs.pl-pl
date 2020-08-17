---
title: -publicsign (opcje kompilatora C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 2655e0216a412053e052ab2ec2fcc8c68ea4f968
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268052"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="6f7e7-102">-publicsign (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="6f7e7-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="6f7e7-103">Ta opcja powoduje, że kompilator zastosuje klucz publiczny, ale w rzeczywistości nie podpisze zestawu.</span><span class="sxs-lookup"><span data-stu-id="6f7e7-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="6f7e7-104">Opcja **-publicsign** ustawia również bit w zestawie, który informuje środowisko uruchomieniowe, że plik jest rzeczywiście podpisany.</span><span class="sxs-lookup"><span data-stu-id="6f7e7-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f7e7-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="6f7e7-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="6f7e7-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="6f7e7-106">Arguments</span></span>

<span data-ttu-id="6f7e7-107">Brak.</span><span class="sxs-lookup"><span data-stu-id="6f7e7-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f7e7-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6f7e7-108">Remarks</span></span>

<span data-ttu-id="6f7e7-109">Opcja **-publicsign** wymaga użycia elementu [-KeyFile](keyfile-compiler-option.md) lub [-containerer](keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6f7e7-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="6f7e7-110">Opcje **KeyFile** lub **containerer** określają klucz publiczny.</span><span class="sxs-lookup"><span data-stu-id="6f7e7-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="6f7e7-111">Opcje **-publicsign** i **-delaysign** wykluczają się wzajemnie.</span><span class="sxs-lookup"><span data-stu-id="6f7e7-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="6f7e7-112">Czasami nazywane "fałszywym znakiem" lub "OSS Sign", podpisywanie publiczne obejmuje klucz publiczny w zestawie danych wyjściowych i ustawia flagę "podpisane", ale w rzeczywistości nie podpisuje zestawu przy użyciu klucza prywatnego.</span><span class="sxs-lookup"><span data-stu-id="6f7e7-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="6f7e7-113">Jest to przydatne w przypadku projektów open source, w których osoby chcą tworzyć zestawy, które są zgodne z opublikowanymi "w pełni podpisanymi", ale nie mają dostępu do klucza prywatnego używanego do podpisywania zestawów.</span><span class="sxs-lookup"><span data-stu-id="6f7e7-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="6f7e7-114">Ponieważ niemal żaden konsument nie musi sprawdzić, czy zestaw jest w pełni podpisany, te publicznie skompilowane zestawy są dostępne w prawie każdym scenariuszu, w którym zostanie użyty całkowicie podpisany.</span><span class="sxs-lookup"><span data-stu-id="6f7e7-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a><span data-ttu-id="6f7e7-115">Aby ustawić tę opcję kompilatora w pliku csproj</span><span class="sxs-lookup"><span data-stu-id="6f7e7-115">To set this compiler option in a csproj file</span></span>

<span data-ttu-id="6f7e7-116">Otwórz plik. csproj projektu i Dodaj następujący element:</span><span class="sxs-lookup"><span data-stu-id="6f7e7-116">Open the .csproj file for a project, and add the following element:</span></span>

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a><span data-ttu-id="6f7e7-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6f7e7-117">See also</span></span>

- [<span data-ttu-id="6f7e7-118">Kompilator języka C# — opcja delaysign</span><span class="sxs-lookup"><span data-stu-id="6f7e7-118">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="6f7e7-119">Kompilator języka C# — opcja keyfile</span><span class="sxs-lookup"><span data-stu-id="6f7e7-119">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="6f7e7-120">Kompilator języka C# — opcja kontenera</span><span class="sxs-lookup"><span data-stu-id="6f7e7-120">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="6f7e7-121">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="6f7e7-121">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="6f7e7-122">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="6f7e7-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
