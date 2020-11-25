---
title: Opcje przycinania
description: Dowiedz się, jak kontrolować przycinanie aplikacji samodzielnych.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: e36aca3aadb6968f73a439ca985dc410d1bc88d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704659"
---
# <a name="trimming-options"></a><span data-ttu-id="68d67-103">Opcje przycinania</span><span class="sxs-lookup"><span data-stu-id="68d67-103">Trimming options</span></span>

<span data-ttu-id="68d67-104">Następujące właściwości i elementy programu MSBuild mają wpływ na zachowanie [przyciętych wdrożeń samodzielnych](trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="68d67-104">The following MSBuild properties and items influence the behavior of [trimmed self-contained deployments](trim-self-contained.md).</span></span> <span data-ttu-id="68d67-105">Niektóre z tych opcji `ILLink` , czyli nazwa narzędzia bazowego implementującego przycinanie.</span><span class="sxs-lookup"><span data-stu-id="68d67-105">Some of the options mention `ILLink`, which is the name of the underlying tool that implements trimming.</span></span> <span data-ttu-id="68d67-106">Więcej informacji o podstawowym narzędziu można znaleźć w [dokumentacji konsolidatora](https://github.com/mono/linker/tree/master/docs).</span><span class="sxs-lookup"><span data-stu-id="68d67-106">More information about the underlying tool can be found at the [Linker documentation](https://github.com/mono/linker/tree/master/docs).</span></span>

## <a name="enable-trimming"></a><span data-ttu-id="68d67-107">Włącz przycinanie</span><span class="sxs-lookup"><span data-stu-id="68d67-107">Enable trimming</span></span>

- `<PublishTrimmed>true</PublishTrimmed>`

   <span data-ttu-id="68d67-108">Włącz przycinanie podczas publikowania z domyślnymi ustawieniami zdefiniowanymi przez zestaw SDK.</span><span class="sxs-lookup"><span data-stu-id="68d67-108">Enable trimming during publish, with the default settings defined by the SDK.</span></span>

<span data-ttu-id="68d67-109">W przypadku korzystania z programu `Microsoft.NET.Sdk` Ta wartość spowoduje przycinanie zestawów struktury z pakietu środowiska uruchomieniowego netcoreapp.</span><span class="sxs-lookup"><span data-stu-id="68d67-109">When using `Microsoft.NET.Sdk`, this will perform assembly-level trimming of the framework assemblies from the netcoreapp runtime pack.</span></span> <span data-ttu-id="68d67-110">Kod aplikacji i biblioteki niestruktury nie są przycinane.</span><span class="sxs-lookup"><span data-stu-id="68d67-110">Application code and non-framework libraries are not trimmed.</span></span> <span data-ttu-id="68d67-111">Inne zestawy SDK mogą definiować różne ustawienia domyślne.</span><span class="sxs-lookup"><span data-stu-id="68d67-111">Other SDKs may define different defaults.</span></span>

## <a name="trimming-granularity"></a><span data-ttu-id="68d67-112">Stopień szczegółowości przycinania</span><span class="sxs-lookup"><span data-stu-id="68d67-112">Trimming granularity</span></span>

<span data-ttu-id="68d67-113">Następujące ustawienia stopnia szczegółowości kontrolują sposób agresywnego nieużywanej IL jest odrzucany.</span><span class="sxs-lookup"><span data-stu-id="68d67-113">The following granularity settings control how aggressively unused IL is discarded.</span></span> <span data-ttu-id="68d67-114">Można ją ustawić jako właściwość lub jako metadane w [pojedynczym zestawie](#trimmed-assemblies).</span><span class="sxs-lookup"><span data-stu-id="68d67-114">This can be set as a property, or as metadata on an [individual assembly](#trimmed-assemblies).</span></span>

- `<TrimMode>copyused</TrimMode>`

   <span data-ttu-id="68d67-115">Włącz przycinanie na poziomie zestawu, co spowoduje zachowanie całego zestawu, jeśli jakakolwiek jego część jest używana (w sposób statyczny).</span><span class="sxs-lookup"><span data-stu-id="68d67-115">Enable assembly-level trimming, which will keep an entire assembly if any part of it is used (in a statically understood way).</span></span>

- `<TrimMode>link</TrimMode>`

    <span data-ttu-id="68d67-116">Włącz przycinanie na poziomie elementu członkowskiego, co spowoduje usunięcie nieużywanych elementów członkowskich z typów.</span><span class="sxs-lookup"><span data-stu-id="68d67-116">Enable member-level trimming, which removes unused members from types.</span></span>

<span data-ttu-id="68d67-117">Zestawy z `<IsTrimmable>true</IsTrimmable>` metadanymi, ale żadne jawne nie `TrimMode` będą używać globalnego `TrimMode` .</span><span class="sxs-lookup"><span data-stu-id="68d67-117">Assemblies with `<IsTrimmable>true</IsTrimmable>` metadata but no explicit `TrimMode` will use the global `TrimMode`.</span></span> <span data-ttu-id="68d67-118">Wartość domyślna `TrimMode` `Microsoft.NET.Sdk` to `copyused` .</span><span class="sxs-lookup"><span data-stu-id="68d67-118">The default `TrimMode` for `Microsoft.NET.Sdk` is `copyused`.</span></span>

## <a name="trimmed-assemblies"></a><span data-ttu-id="68d67-119">Przycięte zestawy</span><span class="sxs-lookup"><span data-stu-id="68d67-119">Trimmed assemblies</span></span>

<span data-ttu-id="68d67-120">Podczas publikowania przyciętej aplikacji zestaw SDK oblicza `ItemGroup` wywoływany `ManagedAssemblyToLink` , który reprezentuje zestaw plików do przetworzenia do przycinania.</span><span class="sxs-lookup"><span data-stu-id="68d67-120">When publishing a trimmed app, the SDK computes an `ItemGroup` called `ManagedAssemblyToLink` that represents the set of files to be processed for trimming.</span></span> <span data-ttu-id="68d67-121">`ManagedAssemblyToLink` może zawierać metadane kontrolujące zachowanie przycinania na zestaw.</span><span class="sxs-lookup"><span data-stu-id="68d67-121">`ManagedAssemblyToLink` may have metadata that controls the trimming behavior per assembly.</span></span> <span data-ttu-id="68d67-122">Aby ustawić te metadane, Utwórz obiekt docelowy, który jest uruchamiany przed wbudowanym `PrepareForILLink` elementem docelowym.</span><span class="sxs-lookup"><span data-stu-id="68d67-122">To set this metadata, create a target that runs before the built-in `PrepareForILLink` target.</span></span> <span data-ttu-id="68d67-123">Poniższy przykład pokazuje, jak włączyć przycinanie `MyAssembly` .</span><span class="sxs-lookup"><span data-stu-id="68d67-123">The following example shows how to enable trimming of `MyAssembly`.</span></span>

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

<span data-ttu-id="68d67-124">Nie należy dodawać ani usuwać elementów do/z `ManagedAssemblyToLink` , ponieważ zestaw SDK oblicza ten zestaw podczas publikowania i oczekuje, że nie jest zmieniany.</span><span class="sxs-lookup"><span data-stu-id="68d67-124">Do not add or remove items to/from `ManagedAssemblyToLink`, because the SDK computes this set during publish and expects it not to change.</span></span> <span data-ttu-id="68d67-125">Obsługiwane metadane to:</span><span class="sxs-lookup"><span data-stu-id="68d67-125">The supported metadata is:</span></span>

- `<IsTrimmable>true</IsTrimmable>`

  <span data-ttu-id="68d67-126">Określ, czy dany zestaw jest przycięty.</span><span class="sxs-lookup"><span data-stu-id="68d67-126">Control whether the given assembly is trimmed.</span></span>

- <span data-ttu-id="68d67-127">`<TrimMode>copyused</TrimMode>` lub `<TrimMode>link</TrimMode>`</span><span class="sxs-lookup"><span data-stu-id="68d67-127">`<TrimMode>copyused</TrimMode>` or `<TrimMode>link</TrimMode>`</span></span>

  <span data-ttu-id="68d67-128">Kontroluj [stopień szczegółowości przycinania](#trimming-granularity) tego zestawu.</span><span class="sxs-lookup"><span data-stu-id="68d67-128">Control the [trimming granularity](#trimming-granularity) of this assembly.</span></span> <span data-ttu-id="68d67-129">Ma to pierwszeństwo przed globalnym `TrimMode` .</span><span class="sxs-lookup"><span data-stu-id="68d67-129">This takes precedence over the global `TrimMode`.</span></span> <span data-ttu-id="68d67-130">Ustawienie `TrimMode` dla zestawu oznacza `<IsTrimmable>true</IsTrimmable>` .</span><span class="sxs-lookup"><span data-stu-id="68d67-130">Setting `TrimMode` on an assembly implies `<IsTrimmable>true</IsTrimmable>`.</span></span>

## <a name="root-assemblies"></a><span data-ttu-id="68d67-131">Główne zestawy</span><span class="sxs-lookup"><span data-stu-id="68d67-131">Root assemblies</span></span>

<span data-ttu-id="68d67-132">Wszystkie zestawy, które nie `<IsTrimmable>true</IsTrimmable>` są uznawane za elementy główne do analizy, co oznacza, że zostaną zachowane wszystkie niezgodne ze statycznymi zależnościami.</span><span class="sxs-lookup"><span data-stu-id="68d67-132">All assemblies that do not have `<IsTrimmable>true</IsTrimmable>` are considered roots for the analysis, which means that they and all of their statically understood dependencies will be kept.</span></span> <span data-ttu-id="68d67-133">Dodatkowe zestawy mogą być "odblokowane" według nazwy (bez `.dll` rozszerzenia):</span><span class="sxs-lookup"><span data-stu-id="68d67-133">Additional assemblies may be "rooted" by name (without the `.dll` extension):</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a><span data-ttu-id="68d67-134">Główne deskryptory</span><span class="sxs-lookup"><span data-stu-id="68d67-134">Root descriptors</span></span>

<span data-ttu-id="68d67-135">Innym sposobem określenia elementów głównych do analizy jest użycie pliku XML, który używa [formatu deskryptora](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format)konsolidatora.</span><span class="sxs-lookup"><span data-stu-id="68d67-135">Another way to specify roots for analysis is using an XML file that uses the linker [descriptor format](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format).</span></span> <span data-ttu-id="68d67-136">Pozwala to na główne elementy członkowskie, a nie cały zestaw.</span><span class="sxs-lookup"><span data-stu-id="68d67-136">This lets you root specific members instead of a whole assembly.</span></span>

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

<span data-ttu-id="68d67-137">Na przykład `MyRoots.xml` może być elementem głównym konkretnej metody, do której dostęp jest uzyskiwany dynamicznie przez aplikację:</span><span class="sxs-lookup"><span data-stu-id="68d67-137">For example, `MyRoots.xml` might root a specific method that is dynamically accessed by the application:</span></span>

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a><span data-ttu-id="68d67-138">Ostrzeżenia analizy</span><span class="sxs-lookup"><span data-stu-id="68d67-138">Analysis warnings</span></span>

<span data-ttu-id="68d67-139">Przycinanie spowoduje usunięcie IL, która nie jest statycznie osiągalna.</span><span class="sxs-lookup"><span data-stu-id="68d67-139">Trimming will remove IL that is not statically reachable.</span></span> <span data-ttu-id="68d67-140">Aplikacje korzystające z odbicia lub innych wzorców tworzących zależności dynamiczne mogą być uszkodzone przez przycinanie.</span><span class="sxs-lookup"><span data-stu-id="68d67-140">Apps that use reflection or other patterns that create dynamic dependencies may be broken by trimming.</span></span> <span data-ttu-id="68d67-141">Aby ostrzec o takich wzorcach:</span><span class="sxs-lookup"><span data-stu-id="68d67-141">To warn about such patterns:</span></span>

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    <span data-ttu-id="68d67-142">Włącz ostrzeżenia analizy przycinania.</span><span class="sxs-lookup"><span data-stu-id="68d67-142">Enable trim analysis warnings.</span></span>

<span data-ttu-id="68d67-143">Będzie to obejmować ostrzeżenia dotyczące całej aplikacji, w tym własny kod, kod biblioteki i kod struktury.</span><span class="sxs-lookup"><span data-stu-id="68d67-143">This will include warnings about the entire app, including your own code, library code, and framework code.</span></span>

## <a name="warning-versions"></a><span data-ttu-id="68d67-144">Wersje ostrzeżeń</span><span class="sxs-lookup"><span data-stu-id="68d67-144">Warning versions</span></span>

<span data-ttu-id="68d67-145">Analiza przycinania uwzględnia [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) Właściwość, która kontroluje wersję ostrzeżeń analizy w zestawie SDK.</span><span class="sxs-lookup"><span data-stu-id="68d67-145">Trim analysis respects the [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) property that controls the version of analysis warnings across the SDK.</span></span> <span data-ttu-id="68d67-146">Istnieje inna właściwość, która kontroluje wersje ostrzeżeń analizy przycinania niezależnie (podobnie jak `WarningLevel` w przypadku kompilatora):</span><span class="sxs-lookup"><span data-stu-id="68d67-146">There is another property that controls the version of trim analysis warnings independently (similar to `WarningLevel` for the compiler):</span></span>

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    <span data-ttu-id="68d67-147">Emituj tylko ostrzeżenia o danym poziomie lub niższym.</span><span class="sxs-lookup"><span data-stu-id="68d67-147">Emit only warnings of the given level or lower.</span></span> <span data-ttu-id="68d67-148">Może to `9999` obejmować wszystkie wersje ostrzegawcze.</span><span class="sxs-lookup"><span data-stu-id="68d67-148">This can be `9999` to include all warning versions.</span></span>

## <a name="suppressing-warnings"></a><span data-ttu-id="68d67-149">Pomijanie ostrzeżeń</span><span class="sxs-lookup"><span data-stu-id="68d67-149">Suppressing warnings</span></span>

<span data-ttu-id="68d67-150">Poszczególne [kody ostrzeżeń](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) można pominąć przy użyciu zwykłych właściwości programu MSBuild przestrzeganych przez łańcucha narzędzi, w tym `NoWarn` , `WarningsAsErrors` , `WarningsNotAsErrors` , i `TreatWarningsAsErrors` .</span><span class="sxs-lookup"><span data-stu-id="68d67-150">Individual [warning codes](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) can be suppressed using the usual MSBuild properties respected by the toolchain, including `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors`, and `TreatWarningsAsErrors`.</span></span> <span data-ttu-id="68d67-151">Istnieje dodatkowa opcja, która kontroluje zachowanie ILLink ostrzegania o błędach w sposób niezależny:</span><span class="sxs-lookup"><span data-stu-id="68d67-151">There is an additional option that controls the ILLink warn-as-error behavior independently:</span></span>

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    <span data-ttu-id="68d67-152">Nie Traktuj ostrzeżeń ILLink jako błędów.</span><span class="sxs-lookup"><span data-stu-id="68d67-152">Don't treat ILLink warnings as errors.</span></span> <span data-ttu-id="68d67-153">Może to być przydatne, aby uniknąć wyłączania ostrzeżeń analizy przycinania do błędów podczas traktowania ostrzeżeń kompilatora jako błędów globalnie.</span><span class="sxs-lookup"><span data-stu-id="68d67-153">This may be useful to avoid turning trim analysis warnings into errors when treating compiler warnings as errors globally.</span></span>

## <a name="removing-symbols"></a><span data-ttu-id="68d67-154">Usuwanie symboli</span><span class="sxs-lookup"><span data-stu-id="68d67-154">Removing symbols</span></span>

<span data-ttu-id="68d67-155">Symbole są zwykle przycięte w celu dopasowania do przyciętych zestawów.</span><span class="sxs-lookup"><span data-stu-id="68d67-155">Symbols will normally be trimmed to match the trimmed assemblies.</span></span> <span data-ttu-id="68d67-156">Można również usunąć wszystkie symbole:</span><span class="sxs-lookup"><span data-stu-id="68d67-156">You can also remove all symbols:</span></span>

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    <span data-ttu-id="68d67-157">Usuń symbole z przyciętej aplikacji, w tym osadzone plików PDB i oddzielne pliki PDB.</span><span class="sxs-lookup"><span data-stu-id="68d67-157">Remove symbols from the trimmed application, including embedded PDBs and separate PDB files.</span></span> <span data-ttu-id="68d67-158">Dotyczy to zarówno kodu aplikacji, jak i wszelkich zależności, które są dołączone do symboli.</span><span class="sxs-lookup"><span data-stu-id="68d67-158">This applies to both the application code and any dependencies that come with symbols.</span></span>

<span data-ttu-id="68d67-159">Zestaw SDK umożliwia także wyłączenie obsługi debugera przy użyciu właściwości `DebuggerSupport` .</span><span class="sxs-lookup"><span data-stu-id="68d67-159">The SDK also makes it possible to disable debugger support using the property `DebuggerSupport`.</span></span> <span data-ttu-id="68d67-160">Gdy obsługa debugera jest wyłączona, przycinanie spowoduje automatyczne usunięcie symboli ( `TrimmerRemoveSymbols` wartość domyślna to true).</span><span class="sxs-lookup"><span data-stu-id="68d67-160">When debugger support is disabled, trimming will remove symbols automatically (`TrimmerRemoveSymbols` will default to true).</span></span>

## <a name="trimming-framework-library-features"></a><span data-ttu-id="68d67-161">Przycinanie funkcji biblioteki Framework</span><span class="sxs-lookup"><span data-stu-id="68d67-161">Trimming framework library features</span></span>

<span data-ttu-id="68d67-162">Kilka obszarów funkcji bibliotek struktury zawiera dyrektywy konsolidatora, które umożliwiają usunięcie kodu dla wyłączonych funkcji.</span><span class="sxs-lookup"><span data-stu-id="68d67-162">Several feature areas of the framework libraries come with linker directives that make it possible to remove the code for disabled features.</span></span>

- `<DebuggerSupport>false</DebuggerSupport>`

    <span data-ttu-id="68d67-163">Usuń kod, który umożliwia lepsze środowisko debugowania.</span><span class="sxs-lookup"><span data-stu-id="68d67-163">Remove code that enables better debugging experiences.</span></span> <span data-ttu-id="68d67-164">Spowoduje to również [usunięcie symboli](#removing-symbols).</span><span class="sxs-lookup"><span data-stu-id="68d67-164">This will also [remove symbols](#removing-symbols).</span></span>

- `<EnableUnsafeBinaryFormatterSerialization>false</EnableUnsafeBinaryFormatterSerialization>`

    <span data-ttu-id="68d67-165">Usuń obsługę serializacji BinaryFormatter.</span><span class="sxs-lookup"><span data-stu-id="68d67-165">Remove BinaryFormatter serialization support.</span></span> <span data-ttu-id="68d67-166">Aby uzyskać więcej informacji, zobacz [BinaryFormatter metody serializacji są przestarzałe](../compatibility/core-libraries/5.0/binaryformatter-serialization-obsolete.md).</span><span class="sxs-lookup"><span data-stu-id="68d67-166">For more information, see [BinaryFormatter serialization methods are obsolete](../compatibility/core-libraries/5.0/binaryformatter-serialization-obsolete.md).</span></span>

- `<EnableUnsafeUTF7Encoding>false</EnableUnsafeUTF7Encoding>`

    <span data-ttu-id="68d67-167">Usuń niezabezpieczony kod kodowania UTF-7.</span><span class="sxs-lookup"><span data-stu-id="68d67-167">Remove insecure UTF-7 encoding code.</span></span> <span data-ttu-id="68d67-168">Aby uzyskać więcej informacji, zobacz [ścieżki kodu UTF-7 są przestarzałe](../compatibility/core-libraries/5.0/utf-7-code-paths-obsolete.md).</span><span class="sxs-lookup"><span data-stu-id="68d67-168">For more information, see [UTF-7 code paths are obsolete](../compatibility/core-libraries/5.0/utf-7-code-paths-obsolete.md).</span></span>

- `<EventSourceSupport>false</EventSourceSupport>`

    <span data-ttu-id="68d67-169">Usuń kod lub logikę powiązaną z usługą EventSource.</span><span class="sxs-lookup"><span data-stu-id="68d67-169">Remove EventSource related code or logic.</span></span>

- `<HttpActivityPropagationSupport>false</HttpActivityPropagationSupport>`

    <span data-ttu-id="68d67-170">Usuń kod związany z obsługą diagnostyki dla systemu .NET. http.</span><span class="sxs-lookup"><span data-stu-id="68d67-170">Remove code related to diagnostics support for System.Net.Http.</span></span>

- `<InvariantGlobalization>true</InvariantGlobalization>`

    <span data-ttu-id="68d67-171">Usuń kod i dane dotyczące globalizacji.</span><span class="sxs-lookup"><span data-stu-id="68d67-171">Remove globalization specific code and data.</span></span> <span data-ttu-id="68d67-172">Aby uzyskać więcej informacji, zobacz [tryb niezmienny](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="68d67-172">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

- `<UseSystemResourceKeys>true</UseSystemResourceKeys>`

    <span data-ttu-id="68d67-173">Komunikaty o wyjątkach dla `System.*` zestawów.</span><span class="sxs-lookup"><span data-stu-id="68d67-173">Strip exception messages for `System.*` assemblies.</span></span> <span data-ttu-id="68d67-174">Gdy wyjątek jest zgłaszany z `System.*` zestawu, komunikat będzie uproszczony identyfikator zasobu zamiast pełnego komunikatu.</span><span class="sxs-lookup"><span data-stu-id="68d67-174">When an exception is thrown from a `System.*` assembly, the message will be a simplified resource ID instead of the full message.</span></span>

 <span data-ttu-id="68d67-175">Te właściwości spowodują, że pokrewny kod zostanie przycięty i spowoduje również wyłączenie funkcji za pośrednictwem pliku [runtimeconfig](../run-time-config/index.md) .</span><span class="sxs-lookup"><span data-stu-id="68d67-175">These properties will cause the related code to be trimmed and will also disable features via the [runtimeconfig](../run-time-config/index.md) file.</span></span> <span data-ttu-id="68d67-176">Aby uzyskać więcej informacji na temat tych właściwości, w tym odpowiednich opcji runtimeconfig, zobacz [przełączniki funkcji](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md).</span><span class="sxs-lookup"><span data-stu-id="68d67-176">For more information about these properties, including the corresponding runtimeconfig options, see [feature switches](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md).</span></span> <span data-ttu-id="68d67-177">Niektóre zestawy SDK mogą mieć wartości domyślne dla tych właściwości.</span><span class="sxs-lookup"><span data-stu-id="68d67-177">Some SDKs may have default values for these properties.</span></span>
