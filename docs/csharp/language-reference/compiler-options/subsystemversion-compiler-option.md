---
description: -subsystemversion (opcje kompilatora C#)
title: -subsystemversion (opcje kompilatora C#)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: e8001d8db214123e75fec4e1d1117ef90a9df606
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128598"
---
# <a name="-subsystemversion-c-compiler-options"></a><span data-ttu-id="8b0b4-103">-subsystemversion (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="8b0b4-103">-subsystemversion (C# Compiler Options)</span></span>

<span data-ttu-id="8b0b4-104">Określa minimalną wersję podsystemu, w którym można uruchomić wygenerowany plik wykonywalny, a tym samym określa wersje systemu Windows, w których można uruchomić plik wykonywalny.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-104">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="8b0b4-105">Najczęściej ta opcja zapewnia, że plik wykonywalny może korzystać z określonych funkcji zabezpieczeń, które nie są dostępne w starszych wersjach systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-105">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="8b0b4-106">Aby określić podsystem, użyj opcji kompilatora [-Target](./target-compiler-option.md) .</span><span class="sxs-lookup"><span data-stu-id="8b0b4-106">To specify the subsystem itself, use the [-target](./target-compiler-option.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b0b4-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="8b0b4-107">Syntax</span></span>

```console
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="8b0b4-108">Parametry</span><span class="sxs-lookup"><span data-stu-id="8b0b4-108">Parameters</span></span>

`major.minor`

<span data-ttu-id="8b0b4-109">Minimalna wymagana wersja podsystemu, wyrażona w notacji kropkowej dla wersji głównych i pomocniczych.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-109">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="8b0b4-110">Można na przykład określić, że aplikacja nie może działać w systemie operacyjnym starszym niż Windows 7, jeśli wartość tej opcji zostanie ustawiona na 6,01, jak w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-110">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="8b0b4-111">Należy określić wartości dla `major` i `minor` jako liczby całkowite.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-111">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="8b0b4-112">Zera wiodące w `minor` wersji nie zmieniają wersji, ale końcowe zera to.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-112">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="8b0b4-113">Na przykład 6,1 i 6,01 odnoszą się do tej samej wersji, ale 6,10 odwołuje się do innej wersji.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-113">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="8b0b4-114">Zalecamy wyrażenie wersji pomocniczej jako dwóch cyfr, aby uniknąć pomyłek.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-114">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b0b4-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8b0b4-115">Remarks</span></span>

<span data-ttu-id="8b0b4-116">W poniższej tabeli wymieniono typowe wersje podsystemów systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-116">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="8b0b4-117">Wersja systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8b0b4-117">Windows version</span></span>|<span data-ttu-id="8b0b4-118">Wersja podsystemu</span><span class="sxs-lookup"><span data-stu-id="8b0b4-118">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="8b0b4-119">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="8b0b4-119">Windows 2000</span></span>|<span data-ttu-id="8b0b4-120">5,00</span><span class="sxs-lookup"><span data-stu-id="8b0b4-120">5.00</span></span>|
|<span data-ttu-id="8b0b4-121">Windows XP</span><span class="sxs-lookup"><span data-stu-id="8b0b4-121">Windows XP</span></span>|<span data-ttu-id="8b0b4-122">5,01</span><span class="sxs-lookup"><span data-stu-id="8b0b4-122">5.01</span></span>|
|<span data-ttu-id="8b0b4-123">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="8b0b4-123">Windows Server 2003</span></span>|<span data-ttu-id="8b0b4-124">5,02</span><span class="sxs-lookup"><span data-stu-id="8b0b4-124">5.02</span></span>|
|<span data-ttu-id="8b0b4-125">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="8b0b4-125">Windows Vista</span></span>|<span data-ttu-id="8b0b4-126">6,00</span><span class="sxs-lookup"><span data-stu-id="8b0b4-126">6.00</span></span>|
|<span data-ttu-id="8b0b4-127">Windows 7</span><span class="sxs-lookup"><span data-stu-id="8b0b4-127">Windows 7</span></span>|<span data-ttu-id="8b0b4-128">6,01</span><span class="sxs-lookup"><span data-stu-id="8b0b4-128">6.01</span></span>|
|<span data-ttu-id="8b0b4-129">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="8b0b4-129">Windows Server 2008</span></span>|<span data-ttu-id="8b0b4-130">6,01</span><span class="sxs-lookup"><span data-stu-id="8b0b4-130">6.01</span></span>|
|<span data-ttu-id="8b0b4-131">Windows 8</span><span class="sxs-lookup"><span data-stu-id="8b0b4-131">Windows 8</span></span>|<span data-ttu-id="8b0b4-132">6,02</span><span class="sxs-lookup"><span data-stu-id="8b0b4-132">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="8b0b4-133">Wartości domyślne</span><span class="sxs-lookup"><span data-stu-id="8b0b4-133">Default values</span></span>

<span data-ttu-id="8b0b4-134">Wartość domyślna opcji kompilatora **-subsystemversion** zależy od warunków z poniższej listy:</span><span class="sxs-lookup"><span data-stu-id="8b0b4-134">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="8b0b4-135">Wartość domyślna to 6,02, jeśli ustawiona jest jakakolwiek opcja kompilatora na poniższej liście:</span><span class="sxs-lookup"><span data-stu-id="8b0b4-135">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="8b0b4-136">-target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="8b0b4-136">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)

  - [<span data-ttu-id="8b0b4-137">-target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="8b0b4-137">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)

  - [<span data-ttu-id="8b0b4-138">-Platforma: ARM</span><span class="sxs-lookup"><span data-stu-id="8b0b4-138">-platform:arm</span></span>](./platform-compiler-option.md)

- <span data-ttu-id="8b0b4-139">Wartość domyślna to 6,00, jeśli używasz programu MSBuild, jesteś celem .NET Framework 4,5 i nie ustawisz żadnych opcji kompilatora określonych wcześniej na tej liście.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-139">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="8b0b4-140">Wartość domyślna to 4,00, jeśli żaden z poprzednich warunków nie ma wartości true.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-140">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="8b0b4-141">Ustawienie tej opcji</span><span class="sxs-lookup"><span data-stu-id="8b0b4-141">Setting this option</span></span>

<span data-ttu-id="8b0b4-142">Aby ustawić opcję kompilatora **-subsystemversion** w programie Visual Studio, należy otworzyć plik. csproj i określić wartość `SubsystemVersion` właściwości w kodzie XML programu MSBuild.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-142">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .csproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="8b0b4-143">Nie można ustawić tej opcji w środowisku IDE programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8b0b4-143">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="8b0b4-144">Aby uzyskać więcej informacji, zobacz "wartości domyślne" wcześniej w tym temacie lub [wspólnych właściwościach projektu MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="8b0b4-144">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="8b0b4-145">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8b0b4-145">See also</span></span>

- [<span data-ttu-id="8b0b4-146">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="8b0b4-146">C# Compiler Options</span></span>](./index.md)
