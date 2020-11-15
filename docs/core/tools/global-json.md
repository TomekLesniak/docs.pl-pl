---
title: global.json — omówienie
description: Dowiedz się, w jaki sposób używać global.jsw pliku, aby ustawić wersję zestawu .NET SDK podczas uruchamiania poleceń interfejsu wiersza polecenia platformy .NET.
ms.topic: how-to
ms.date: 05/01/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 02a0ab478a23f7df55a8cc2e872e480b311304fe
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634002"
---
# <a name="globaljson-overview"></a><span data-ttu-id="fb142-103">global.json — omówienie</span><span class="sxs-lookup"><span data-stu-id="fb142-103">global.json overview</span></span>

<span data-ttu-id="fb142-104">**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,0 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="fb142-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="fb142-105">*global.jsw* pliku umożliwia określenie, która wersja zestawu SDK platformy .NET jest używana podczas uruchamiania poleceń interfejsu wiersza polecenia platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="fb142-105">The *global.json* file allows you to define which .NET SDK version is used when you run .NET CLI commands.</span></span> <span data-ttu-id="fb142-106">Wybór zestawu .NET SDK jest niezależny od określania środowiska uruchomieniowego projektu.</span><span class="sxs-lookup"><span data-stu-id="fb142-106">Selecting the .NET SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="fb142-107">Wersja zestawu .NET SDK wskazuje, które wersje interfejsu wiersza polecenia platformy .NET są używane.</span><span class="sxs-lookup"><span data-stu-id="fb142-107">The .NET SDK version indicates which versions of the .NET CLI is used.</span></span>

<span data-ttu-id="fb142-108">Ogólnie rzecz biorąc, chcesz użyć najnowszej wersji narzędzi zestawu SDK, więc nie jest wymagane *global.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="fb142-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="fb142-109">W niektórych zaawansowanych scenariuszach możesz chcieć kontrolować wersję narzędzi zestawu SDK, a w tym artykule wyjaśniono, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="fb142-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="fb142-110">Aby uzyskać więcej informacji na temat określania środowiska uruchomieniowego, zobacz [platforme docelowe](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="fb142-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="fb142-111">Zestaw .NET SDK szuka *global.js* w pliku w bieżącym katalogu roboczym (który nie jest taki sam jak katalog projektu) lub jeden z jego katalogów nadrzędnych.</span><span class="sxs-lookup"><span data-stu-id="fb142-111">The .NET SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="fb142-112">global.jsw schemacie</span><span class="sxs-lookup"><span data-stu-id="fb142-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="fb142-113">sdk</span><span class="sxs-lookup"><span data-stu-id="fb142-113">sdk</span></span>

<span data-ttu-id="fb142-114">Wprowadź `object`</span><span class="sxs-lookup"><span data-stu-id="fb142-114">Type: `object`</span></span>

<span data-ttu-id="fb142-115">Określa informacje o zestawie SDK platformy .NET do wybrania.</span><span class="sxs-lookup"><span data-stu-id="fb142-115">Specifies information about the .NET SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="fb142-116">Wersja</span><span class="sxs-lookup"><span data-stu-id="fb142-116">version</span></span>

- <span data-ttu-id="fb142-117">Wprowadź `string`</span><span class="sxs-lookup"><span data-stu-id="fb142-117">Type: `string`</span></span>

- <span data-ttu-id="fb142-118">Dostępne od: .NET Core 1,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="fb142-119">Wersja zestawu SDK platformy .NET do użycia.</span><span class="sxs-lookup"><span data-stu-id="fb142-119">The version of the .NET SDK to use.</span></span>

<span data-ttu-id="fb142-120">To pole:</span><span class="sxs-lookup"><span data-stu-id="fb142-120">This field:</span></span>

- <span data-ttu-id="fb142-121">Nie ma obsługi symboli wieloznacznych, czyli należy określić pełny numer wersji.</span><span class="sxs-lookup"><span data-stu-id="fb142-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="fb142-122">Nie obsługuje zakresów wersji.</span><span class="sxs-lookup"><span data-stu-id="fb142-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="fb142-123">allowPrerelease</span><span class="sxs-lookup"><span data-stu-id="fb142-123">allowPrerelease</span></span>

- <span data-ttu-id="fb142-124">Wprowadź `boolean`</span><span class="sxs-lookup"><span data-stu-id="fb142-124">Type: `boolean`</span></span>

- <span data-ttu-id="fb142-125">Dostępne od: .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="fb142-126">Wskazuje, czy program rozpoznawania SDK powinien wziąć pod uwagę wersje wstępne podczas wybierania wersji zestawu SDK do użycia.</span><span class="sxs-lookup"><span data-stu-id="fb142-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="fb142-127">Jeśli ta wartość nie zostanie jawnie ustawiona, wartość domyślna zależy od tego, czy korzystasz z programu Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="fb142-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="fb142-128">Jeśli **nie** Jesteś w programie Visual Studio, wartość domyślna to `true` .</span><span class="sxs-lookup"><span data-stu-id="fb142-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="fb142-129">Jeśli używasz programu Visual Studio, zostanie użyty żądany stan wersji wstępnej.</span><span class="sxs-lookup"><span data-stu-id="fb142-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="fb142-130">Oznacza to, że jeśli korzystasz z wersji zapoznawczej programu Visual Studio lub ustawisz opcję Użyj podglądu opcji **zestaw .NET Core SDK** (w obszarze **Narzędzia**  >  **Opcje**  >  **środowiska** w  >  **wersji zapoznawczej** ), wartość domyślna to `true` ; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="fb142-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features** ), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="fb142-131">Przeniesienia</span><span class="sxs-lookup"><span data-stu-id="fb142-131">rollForward</span></span>

- <span data-ttu-id="fb142-132">Wprowadź `string`</span><span class="sxs-lookup"><span data-stu-id="fb142-132">Type: `string`</span></span>

- <span data-ttu-id="fb142-133">Dostępne od: .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="fb142-134">Zasady przyciągania do przodu, które mają być używane podczas wybierania wersji zestawu SDK, jako rezerwy w przypadku braku określonej wersji zestawu SDK lub jako dyrektywy do korzystania z nowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="fb142-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="fb142-135">Należy określić [wersję](#version) o `rollForward` wartości, chyba że jest ona ustawiana na `latestMajor` .</span><span class="sxs-lookup"><span data-stu-id="fb142-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>
<span data-ttu-id="fb142-136">Domyślne zachowanie funkcji przeszukiwania do przodu jest określane przez [reguły dopasowywania](#matching-rules).</span><span class="sxs-lookup"><span data-stu-id="fb142-136">The default roll forward behavior is determined by the [matching rules](#matching-rules).</span></span>

<span data-ttu-id="fb142-137">Aby zrozumieć dostępne zasady i ich zachowanie, należy wziąć pod uwagę następujące definicje wersji zestawu SDK w formacie `x.y.znn` :</span><span class="sxs-lookup"><span data-stu-id="fb142-137">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="fb142-138">`x` jest wersją główną.</span><span class="sxs-lookup"><span data-stu-id="fb142-138">`x` is the major version.</span></span>
- <span data-ttu-id="fb142-139">`y` jest wersją pomocniczą.</span><span class="sxs-lookup"><span data-stu-id="fb142-139">`y` is the minor version.</span></span>
- <span data-ttu-id="fb142-140">`z` jest paskiem funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-140">`z` is the feature band.</span></span>
- <span data-ttu-id="fb142-141">`nn` jest wersją poprawki.</span><span class="sxs-lookup"><span data-stu-id="fb142-141">`nn` is the patch version.</span></span>

<span data-ttu-id="fb142-142">W poniższej tabeli przedstawiono możliwe wartości `rollForward` klucza:</span><span class="sxs-lookup"><span data-stu-id="fb142-142">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="fb142-143">Wartość</span><span class="sxs-lookup"><span data-stu-id="fb142-143">Value</span></span>         | <span data-ttu-id="fb142-144">Zachowanie</span><span class="sxs-lookup"><span data-stu-id="fb142-144">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="fb142-145">Używa określonej wersji.</span><span class="sxs-lookup"><span data-stu-id="fb142-145">Uses the specified version.</span></span> <br> <span data-ttu-id="fb142-146">Jeśli nie zostanie znaleziony, przenosi do przodu do najnowszego poziomu poprawki.</span><span class="sxs-lookup"><span data-stu-id="fb142-146">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="fb142-147">Jeśli nie zostanie znaleziony, kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="fb142-147">If not found, fails.</span></span> <br><br> <span data-ttu-id="fb142-148">Ta wartość to starsze zachowanie z wcześniejszych wersji zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-148">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="fb142-149">Używa najnowszego poziomu poprawek dla określonych głównych, pomocniczych i grup funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-149">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="fb142-150">Jeśli nie zostanie znaleziony, przenosi dalej do kolejnej wyższej grupy funkcji w ramach tego samego elementu głównego/pomocniczego i używa najnowszego poziomu poprawek dla tej grupy funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-150">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="fb142-151">Jeśli nie zostanie znaleziony, kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="fb142-151">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="fb142-152">Używa najnowszego poziomu poprawek dla określonych głównych, pomocniczych i grup funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-152">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="fb142-153">Jeśli nie zostanie znaleziony, przenosi dalej do kolejnej wyższej grupy funkcji w tej samej wersji głównej/pomocniczej i używa najnowszego poziomu poprawek dla tej grupy funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-153">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="fb142-154">Jeśli nie zostanie znaleziony, przenosi dalej do następnego wyższego elementu pomocniczego i grupy funkcji w ramach tego samego elementu głównego i używa najnowszego poziomu poprawek dla tej grupy funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-154">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="fb142-155">Jeśli nie zostanie znaleziony, kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="fb142-155">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="fb142-156">Używa najnowszego poziomu poprawek dla określonych głównych, pomocniczych i grup funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-156">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="fb142-157">Jeśli nie zostanie znaleziony, przenosi dalej do kolejnej wyższej grupy funkcji w tej samej wersji głównej/pomocniczej i używa najnowszego poziomu poprawek dla tej grupy funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-157">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="fb142-158">Jeśli nie zostanie znaleziony, przenosi dalej do następnego wyższego elementu pomocniczego i grupy funkcji w ramach tego samego elementu głównego i używa najnowszego poziomu poprawek dla tej grupy funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-158">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="fb142-159">Jeśli nie zostanie znaleziony, przenosi dalej do następnej wyższej, pomocniczej i funkcjonalnej grupy i używa najnowszego poziomu poprawek dla tej grupy funkcji.</span><span class="sxs-lookup"><span data-stu-id="fb142-159">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="fb142-160">Jeśli nie zostanie znaleziony, kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="fb142-160">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="fb142-161">Używa najnowszego zainstalowanego poziomu poprawek, który jest zgodny z żądanym głównym, pomocniczym i grupą funkcji z poziomem poprawek, który jest większy lub równy określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="fb142-161">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="fb142-162">Jeśli nie zostanie znaleziony, kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="fb142-162">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="fb142-163">Używa najwyższej zainstalowanej grupy funkcji i poziomu poprawek, które pasują do żądanego elementu głównego i pomocniczego z pasmem funkcji i poziomem poprawek, który jest większy lub równy określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="fb142-163">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band and patch level that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="fb142-164">Jeśli nie zostanie znaleziony, kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="fb142-164">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="fb142-165">Używa najwyższej zainstalowanej pomocniczej, pasma funkcji i poziomu poprawek, który jest zgodny z żądanym elementem głównym z pomocniczą, pasmem funkcji i poziomem poprawek, który jest większy lub równy określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="fb142-165">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor, feature band, and patch level that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="fb142-166">Jeśli nie zostanie znaleziony, kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="fb142-166">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="fb142-167">Używa najwyższego zainstalowanego zestawu .NET SDK z wersją, która jest większa lub równa określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="fb142-167">Uses the highest installed .NET SDK with a version that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="fb142-168">Jeśli nie zostanie znaleziona, kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="fb142-168">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="fb142-169">Nie jest rzutowany do przodu.</span><span class="sxs-lookup"><span data-stu-id="fb142-169">Doesn't roll forward.</span></span> <span data-ttu-id="fb142-170">Dokładne dopasowanie jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="fb142-170">Exact match required.</span></span> |

### <a name="msbuild-sdks"></a><span data-ttu-id="fb142-171">MSBuild — zestawy SDK</span><span class="sxs-lookup"><span data-stu-id="fb142-171">msbuild-sdks</span></span>

<span data-ttu-id="fb142-172">Wprowadź `object`</span><span class="sxs-lookup"><span data-stu-id="fb142-172">Type: `object`</span></span>

<span data-ttu-id="fb142-173">Pozwala kontrolować wersję zestawu SDK projektu w jednym miejscu, a nie w każdym projekcie.</span><span class="sxs-lookup"><span data-stu-id="fb142-173">Lets you control the project SDK version in one place rather than in each individual project.</span></span> <span data-ttu-id="fb142-174">Aby uzyskać więcej informacji, zobacz [jak są rozpoznawane zestawy SDK projektu](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span><span class="sxs-lookup"><span data-stu-id="fb142-174">For more information, see [How project SDKs are resolved](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span></span>

## <a name="examples"></a><span data-ttu-id="fb142-175">Przykłady</span><span class="sxs-lookup"><span data-stu-id="fb142-175">Examples</span></span>

<span data-ttu-id="fb142-176">Poniższy przykład pokazuje, jak nie używać wersji wstępnych:</span><span class="sxs-lookup"><span data-stu-id="fb142-176">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="fb142-177">Poniższy przykład pokazuje, jak używać zainstalowanej najwyższej wersji, która jest większa lub równa określonej wersji.</span><span class="sxs-lookup"><span data-stu-id="fb142-177">The following example shows how to use the highest version installed that is greater or equal than the specified version.</span></span> <span data-ttu-id="fb142-178">W pokazanym kodzie JSON nie jest dozwolony żaden zestaw SDK wcześniejszy niż 2.2.200 i umożliwia 2.2.200 lub dowolną nowszą wersję, w tym 3.0.xxx i 3.1.xxx.</span><span class="sxs-lookup"><span data-stu-id="fb142-178">The JSON shown disallows any SDK version earlier than 2.2.200 and allows 2.2.200 or any later version, including 3.0.xxx and 3.1.xxx.</span></span>

```json
{
  "sdk": {
    "version": "2.2.200",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="fb142-179">Poniższy przykład pokazuje, jak używać dokładnej wersji:</span><span class="sxs-lookup"><span data-stu-id="fb142-179">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="fb142-180">Poniższy przykład pokazuje, jak używać najnowszej wersji i zainstalowanej wersji poprawki dla określonej głównej i pomocniczej.</span><span class="sxs-lookup"><span data-stu-id="fb142-180">The following example shows how to use the latest feature band and patch version installed of a specific major and minor version.</span></span> <span data-ttu-id="fb142-181">W pokazanym kodzie JSON nie jest dozwolony żaden zestaw SDK wcześniejszy niż 3.1.102 i umożliwia 3.1.102 lub dowolną nowszą wersję 3.1.xxx, taką jak 3.1.103 lub 3.1.200.</span><span class="sxs-lookup"><span data-stu-id="fb142-181">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.xxx version, such as 3.1.103 or 3.1.200.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestFeature"
  }
}
```

<span data-ttu-id="fb142-182">Poniższy przykład pokazuje, jak używać najnowszej wersji poprawki zainstalowanej w określonej wersji.</span><span class="sxs-lookup"><span data-stu-id="fb142-182">The following example shows how to use the highest patch version installed of a specific version.</span></span> <span data-ttu-id="fb142-183">W pokazanym kodzie JSON nie jest dozwolony żaden zestaw SDK wcześniejszy niż 3.1.102 i umożliwia 3.1.102 lub jakąkolwiek nowszą wersję 3.1.1 XX, taką jak 3.1.103 lub 3.1.199.</span><span class="sxs-lookup"><span data-stu-id="fb142-183">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.1xx version, such as 3.1.103 or 3.1.199.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-cli"></a><span data-ttu-id="fb142-184">global.jsw interfejsie wiersza polecenia platformy .NET i</span><span class="sxs-lookup"><span data-stu-id="fb142-184">global.json and the .NET CLI</span></span>

<span data-ttu-id="fb142-185">Warto wiedzieć, które wersje zestawu SDK są zainstalowane na maszynie, aby ustawić je w *global.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="fb142-185">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="fb142-186">Aby uzyskać więcej informacji o tym, jak to zrobić, zobacz [Jak sprawdzić, czy program .NET jest już zainstalowany](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span><span class="sxs-lookup"><span data-stu-id="fb142-186">For more information on how to do that, see [How to check that .NET is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="fb142-187">Aby zainstalować dodatkowe wersje zestawu SDK platformy .NET na maszynie, odwiedź stronę [pobieranie platformy .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .</span><span class="sxs-lookup"><span data-stu-id="fb142-187">To install additional .NET SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="fb142-188">Możesz utworzyć nowy *global.jsw* pliku w bieżącym katalogu, wykonując polecenie [dotnet New](dotnet-new.md) , podobne do poniższego przykładu:</span><span class="sxs-lookup"><span data-stu-id="fb142-188">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="fb142-189">Reguły dopasowania</span><span class="sxs-lookup"><span data-stu-id="fb142-189">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="fb142-190">Reguły dopasowywania podlegają `dotnet.exe` punktowi wejścia, który jest wspólny dla wszystkich zainstalowanych środowiska uruchomieniowego platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="fb142-190">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET installed runtimes.</span></span> <span data-ttu-id="fb142-191">Reguły dopasowania dla najnowszej zainstalowanej wersji środowiska uruchomieniowego .NET są używane, gdy istnieje wiele środowisk uruchomieniowych zainstalowanych obok siebie lub w przypadku korzystania z *global.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="fb142-191">The matching rules for the latest installed version of the .NET Runtime are used when you have multiple runtimes installed side-by-side or if or you're using a *global.json* file.</span></span>

## <a name="net-core-3x"></a>[<span data-ttu-id="fb142-192">.NET Core 3. x</span><span class="sxs-lookup"><span data-stu-id="fb142-192">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="fb142-193">Począwszy od platformy .NET Core 3,0, stosowane są następujące reguły podczas określania, która wersja zestawu SDK ma być używana:</span><span class="sxs-lookup"><span data-stu-id="fb142-193">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="fb142-194">Jeśli nie zostanie znaleziony *global.jsw* pliku lub funkcja *global.json* nie określi wersji zestawu SDK ani `allowPrerelease` wartości, zostanie użyta najwyższa zainstalowana wersja zestawu SDK (odpowiednik ustawienia `rollForward` do `latestMajor` ).</span><span class="sxs-lookup"><span data-stu-id="fb142-194">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="fb142-195">Czy wersje wstępne zestawu SDK są brane pod uwagę, zależy od tego, jak `dotnet` są wywoływane.</span><span class="sxs-lookup"><span data-stu-id="fb142-195">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="fb142-196">Jeśli **nie** Jesteś w programie Visual Studio, są brane pod uwagę wersje wstępne.</span><span class="sxs-lookup"><span data-stu-id="fb142-196">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="fb142-197">Jeśli używasz programu Visual Studio, zostanie użyty żądany stan wersji wstępnej.</span><span class="sxs-lookup"><span data-stu-id="fb142-197">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="fb142-198">Oznacza to, że jeśli korzystasz z wersji zapoznawczej programu Visual Studio lub ustawisz opcję Użyj podglądu opcji **zestaw .NET Core SDK** (w obszarze **Narzędzia**  >  **Opcje**  >  **środowiska** w  >  **wersji zapoznawczej** ), są uwzględniane wersje wstępne. w przeciwnym razie są brane pod uwagę tylko wersje wydań.</span><span class="sxs-lookup"><span data-stu-id="fb142-198">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features** ), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="fb142-199">Jeśli zostanie znaleziony *global.jsw* pliku, który nie określa wersji zestawu SDK, ale określa `allowPrerelease` wartość, używana jest najwyższa zainstalowana wersja zestawu SDK (odpowiednik ustawienia `rollForward` do `latestMajor` ).</span><span class="sxs-lookup"><span data-stu-id="fb142-199">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="fb142-200">Czy Najnowsza wersja zestawu SDK może być wykorzystana lub wersja wstępna zależy od wartości `allowPrerelease` .</span><span class="sxs-lookup"><span data-stu-id="fb142-200">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="fb142-201">`true` wskazuje wersje wstępne są brane pod uwagę; `false` wskazuje, że są brane pod uwagę tylko wersje wydań.</span><span class="sxs-lookup"><span data-stu-id="fb142-201">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="fb142-202">Jeśli *global.jsw* pliku zostanie znaleziony i określi wersję zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="fb142-202">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="fb142-203">Jeśli `rollForward` wartość nie jest ustawiona, zostanie użyta `latestPatch` jako `rollForward` zasady domyślne.</span><span class="sxs-lookup"><span data-stu-id="fb142-203">If no `rollForward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="fb142-204">W przeciwnym razie Sprawdź każdą wartość i ich zachowanie w sekcji [przeniesienia](#rollforward) .</span><span class="sxs-lookup"><span data-stu-id="fb142-204">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="fb142-205">Określa, czy wersje wstępne są brane pod uwagę, co jest zachowaniem domyślnym, gdy `allowPrerelease` nie jest ustawione, w sekcji [allowPrerelease](#allowprerelease) .</span><span class="sxs-lookup"><span data-stu-id="fb142-205">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2x"></a>[<span data-ttu-id="fb142-206">.NET Core 2. x</span><span class="sxs-lookup"><span data-stu-id="fb142-206">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="fb142-207">W przypadku zestawu SDK platformy .NET Core 2. x następujące reguły są stosowane podczas określania, która wersja zestawu SDK ma być używana:</span><span class="sxs-lookup"><span data-stu-id="fb142-207">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="fb142-208">Jeśli nie zostanie znaleziony *global.jsw* pliku lub *global.json* nie określi wersji zestawu SDK, zostanie użyta Najnowsza zainstalowana wersja zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-208">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="fb142-209">Najnowsza wersja zestawu SDK może być wydaniem lub w wersji wstępnej — najwyższa wersja usługi WINS.</span><span class="sxs-lookup"><span data-stu-id="fb142-209">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="fb142-210">Jeśli *global.json* określa wersję zestawu SDK:</span><span class="sxs-lookup"><span data-stu-id="fb142-210">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="fb142-211">Jeśli określona wersja zestawu SDK zostanie znaleziona na komputerze, używana jest dokładna wersja.</span><span class="sxs-lookup"><span data-stu-id="fb142-211">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="fb142-212">Jeśli na maszynie nie można znaleźć określonej wersji zestawu SDK, zostanie użyta Najnowsza zainstalowana **wersja poprawki** zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-212">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="fb142-213">Najnowsza zainstalowana **wersja poprawki** zestawu SDK może być wydaniem lub w wersji wstępnej — najwyższa wersja usługi WINS.</span><span class="sxs-lookup"><span data-stu-id="fb142-213">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="fb142-214">W przypadku programu .NET Core 2,1 lub nowszego **wersje poprawek** niższe niż określona **wersja poprawki** są ignorowane w wyborze zestawu SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-214">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="fb142-215">Jeśli nie można znaleźć określonej wersji zestawu SDK i odpowiedniej **wersji poprawki** zestawu SDK, zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="fb142-215">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="fb142-216">Wersja zestawu SDK składa się z następujących części:</span><span class="sxs-lookup"><span data-stu-id="fb142-216">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="fb142-217">**Wersja funkcji** zestaw .NET Core SDK jest reprezentowana przez pierwszą cyfrę ( `x` ) w ostatniej części cyfry ( `xyz` ) dla wersji zestawu SDK 2.1.100 i wyższych.</span><span class="sxs-lookup"><span data-stu-id="fb142-217">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="fb142-218">Ogólnie rzecz biorąc zestaw .NET Core SDK ma szybszy cykl wydawniczy niż .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fb142-218">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="fb142-219">**Wersja poprawki** jest definiowana przez ostatnie dwie cyfry ( `yz` ) w ostatniej części cyfry ( `xyz` ) dla wersji zestawu SDK 2.1.100 i wyższych.</span><span class="sxs-lookup"><span data-stu-id="fb142-219">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="fb142-220">Na przykład jeśli określisz `2.1.300` jako wersję zestawu SDK, wybór zestawu SDK znajdzie się do, `2.1.399` ale `2.1.400` nie jest traktowany jako wersja poprawki dla programu `2.1.300` .</span><span class="sxs-lookup"><span data-stu-id="fb142-220">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="fb142-221">Wersje zestaw .NET Core SDK `2.1.100` za pomocą `2.1.201` zostały wydane podczas przejścia między schematami numerów wersji i nie obsługują poprawnie `xyz` notacji.</span><span class="sxs-lookup"><span data-stu-id="fb142-221">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="fb142-222">Zdecydowanie zalecamy, aby określić te wersje w *global.js* pliku, aby upewnić się, że określone wersje znajdują się na komputerach docelowych.</span><span class="sxs-lookup"><span data-stu-id="fb142-222">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshoot-build-warnings"></a><span data-ttu-id="fb142-223">Rozwiązywanie problemów z ostrzeżeniami kompilacji</span><span class="sxs-lookup"><span data-stu-id="fb142-223">Troubleshoot build warnings</span></span>

* <span data-ttu-id="fb142-224">Poniższe ostrzeżenie wskazuje, że projekt został skompilowany przy użyciu wstępnej wersji zestaw .NET Core SDK:</span><span class="sxs-lookup"><span data-stu-id="fb142-224">The following warning indicates that your project was compiled using a prerelease version of the .NET Core SDK:</span></span>

  > <span data-ttu-id="fb142-225">Pracujesz z wersją zapoznawczą zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-225">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="fb142-226">Wersję zestawu SDK można zdefiniować za pomocą global.jsw pliku w bieżącym projekcie.</span><span class="sxs-lookup"><span data-stu-id="fb142-226">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="fb142-227">Więcej o <https://go.microsoft.com/fwlink/?linkid=869452> .</span><span class="sxs-lookup"><span data-stu-id="fb142-227">More at <https://go.microsoft.com/fwlink/?linkid=869452>.</span></span>

  <span data-ttu-id="fb142-228">Wersje zestaw .NET Core SDK mają historię i zobowiązanie o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="fb142-228">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="fb142-229">Jeśli jednak nie chcesz używać wersji wstępnej, Sprawdź różne strategie, których można użyć z zestawem SDK .NET Core 3,0 lub nowszą wersją w sekcji [allowPrerelease](#allowprerelease) .</span><span class="sxs-lookup"><span data-stu-id="fb142-229">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="fb142-230">W przypadku maszyn, na których nigdy nie zainstalowano środowiska uruchomieniowego .NET Core 3,0 lub nowszego lub zestawu SDK, należy utworzyć *global.jsw* pliku i określić dokładną wersję, która ma być używana.</span><span class="sxs-lookup"><span data-stu-id="fb142-230">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

* <span data-ttu-id="fb142-231">Poniższe ostrzeżenie wskazuje, że projekt jest ukierunkowany na EF Core 1,0 lub 1,1, co nie jest zgodne z zestawem SDK .NET Core 2,1 i nowszymi wersjami:</span><span class="sxs-lookup"><span data-stu-id="fb142-231">The following warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions:</span></span>

  > <span data-ttu-id="fb142-232">Projekt startowy "{startupProject}" wskazuje platformę ". NETCoreApp "wersja" {targetFrameworkVersion} ".</span><span class="sxs-lookup"><span data-stu-id="fb142-232">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="fb142-233">Ta wersja narzędzi wiersza polecenia Entity Framework Core .NET obsługuje tylko wersję 2,0 lub nowszą.</span><span class="sxs-lookup"><span data-stu-id="fb142-233">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="fb142-234">Aby uzyskać informacje na temat używania starszych wersji narzędzi, zobacz <https://go.microsoft.com/fwlink/?linkid=871254> .</span><span class="sxs-lookup"><span data-stu-id="fb142-234">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254>.</span></span>

  <span data-ttu-id="fb142-235">Począwszy od zestawu SDK programu .NET Core 2,1 (wersja 2.1.300), `dotnet ef` polecenie znajduje się w zestawie SDK.</span><span class="sxs-lookup"><span data-stu-id="fb142-235">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="fb142-236">Aby skompilować projekt, zainstaluj na komputerze zestaw SDK programu .NET Core 2,0 (wersja 2.1.201) lub wcześniejszy i zdefiniuj żądaną wersję zestawu SDK przy użyciu *global.js* pliku.</span><span class="sxs-lookup"><span data-stu-id="fb142-236">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) or earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="fb142-237">Aby uzyskać więcej informacji na temat tego `dotnet ef` polecenia, zobacz [EF Core narzędzia wiersza polecenia programu .NET](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="fb142-237">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb142-238">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fb142-238">See also</span></span>

- [<span data-ttu-id="fb142-239">Jak są rozwiązywane zestawy SDK projektu</span><span class="sxs-lookup"><span data-stu-id="fb142-239">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
