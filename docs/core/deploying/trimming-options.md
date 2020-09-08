---
title: Opcje przycinania
description: Dowiedz się, jak kontrolować przycinanie aplikacji samodzielnych.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 89bd195a97c2f1bbbba9199fea51c917c4e4836b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515835"
---
# <a name="trimming-options"></a>Opcje przycinania

Następujące właściwości i elementy programu MSBuild mają wpływ na zachowanie [przyciętych wdrożeń samodzielnych](trim-self-contained.md). Niektóre z tych opcji `ILLink` , czyli nazwa narzędzia bazowego implementującego przycinanie. Więcej informacji o podstawowym narzędziu można znaleźć w [dokumentacji konsolidatora](https://github.com/mono/linker/tree/master/docs).

## <a name="enable-trimming"></a>Włącz przycinanie

- `<PublishTrimmed>true</PublishTrimmed>`

   Włącz przycinanie podczas publikowania z domyślnymi ustawieniami zdefiniowanymi przez zestaw SDK.

W przypadku korzystania z programu `Microsoft.NET.Sdk` Ta wartość spowoduje przycinanie zestawów struktury z pakietu środowiska uruchomieniowego netcoreapp. Kod aplikacji i biblioteki niestruktury nie są przycinane. Inne zestawy SDK mogą definiować różne ustawienia domyślne.

## <a name="trimming-granularity"></a>Stopień szczegółowości przycinania

Następujące ustawienia stopnia szczegółowości kontrolują sposób agresywnego nieużywanej IL jest odrzucany. Można ją ustawić jako właściwość lub jako metadane w [pojedynczym zestawie](#trimmed-assemblies).

- `<TrimMode>copyused</TrimMode>`

   Włącz przycinanie na poziomie zestawu, co spowoduje zachowanie całego zestawu, jeśli jakakolwiek jego część jest używana (w sposób statyczny).

- `<TrimMode>link</TrimMode>`

    Włącz przycinanie na poziomie elementu członkowskiego, co spowoduje usunięcie nieużywanych elementów członkowskich z typów.

Zestawy z `<IsTrimmable>true</IsTrimmable>` metadanymi, ale żadne jawne nie `TrimMode` będą używać globalnego `TrimMode` . Wartość domyślna `TrimMode` `Microsoft.NET.Sdk` to `copyused` .

## <a name="trimmed-assemblies"></a>Przycięte zestawy

Podczas publikowania przyciętej aplikacji zestaw SDK oblicza `ItemGroup` wywoływany `ManagedAssemblyToLink` , który reprezentuje zestaw plików do przetworzenia do przycinania. `ManagedAssemblyToLink` może zawierać metadane kontrolujące zachowanie przycinania na zestaw. Aby ustawić te metadane, Utwórz obiekt docelowy, który jest uruchamiany przed wbudowanym `PrepareForILLink` elementem docelowym. Poniższy przykład pokazuje, jak włączyć przycinanie `MyAssembly` .

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

Nie należy dodawać ani usuwać elementów do/z `ManagedAssemblyToLink` , ponieważ zestaw SDK oblicza ten zestaw podczas publikowania i oczekuje, że nie jest zmieniany. Obsługiwane metadane to:

- `<IsTrimmable>true</IsTrimmable>`

  Określ, czy dany zestaw jest przycięty.

- `<TrimMode>copyused</TrimMode>` lub `<TrimMode>link</TrimMode>`

  Kontroluj [stopień szczegółowości przycinania](#trimming-granularity) tego zestawu. Ma to pierwszeństwo przed globalnym `TrimMode` . Ustawienie `TrimMode` dla zestawu oznacza `<IsTrimmable>true</IsTrimmable>` .

## <a name="root-assemblies"></a>Główne zestawy

Wszystkie zestawy, które nie `<IsTrimmable>true</IsTrimmable>` są uznawane za elementy główne do analizy, co oznacza, że zostaną zachowane wszystkie niezgodne ze statycznymi zależnościami. Dodatkowe zestawy mogą być "odblokowane" według nazwy (bez `.dll` rozszerzenia):

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a>Główne deskryptory

Innym sposobem określenia elementów głównych do analizy jest użycie pliku XML, który używa [formatu deskryptora](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format)konsolidatora. Pozwala to na główne elementy członkowskie, a nie cały zestaw.

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

Na przykład `MyRoots.xml` może być elementem głównym konkretnej metody, do której dostęp jest uzyskiwany dynamicznie przez aplikację:

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a>Ostrzeżenia analizy

Przycinanie spowoduje usunięcie IL, która nie jest statycznie osiągalna. Aplikacje korzystające z odbicia lub innych wzorców tworzących zależności dynamiczne mogą być uszkodzone przez przycinanie. Aby ostrzec o takich wzorcach:

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    Włącz ostrzeżenia analizy przycinania.

Będzie to obejmować ostrzeżenia dotyczące całej aplikacji, w tym własny kod, kod biblioteki i kod struktury.

## <a name="warning-versions"></a>Wersje ostrzeżeń

Analiza przycinania uwzględnia [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) Właściwość, która kontroluje wersję ostrzeżeń analizy w zestawie SDK. Istnieje inna właściwość, która kontroluje wersje ostrzeżeń analizy przycinania niezależnie (podobnie jak `WarningLevel` w przypadku kompilatora):

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    Emituj tylko ostrzeżenia o danym poziomie lub niższym. Może to `9999` obejmować wszystkie wersje ostrzegawcze.

## <a name="suppressing-warnings"></a>Pomijanie ostrzeżeń

Poszczególne [kody ostrzeżeń](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) można pominąć przy użyciu zwykłych właściwości programu MSBuild przestrzeganych przez łańcucha narzędzi, w tym `NoWarn` , `WarningsAsErrors` , `WarningsNotAsErrors` , i `TreatWarningsAsErrors` . Istnieje dodatkowa opcja, która kontroluje zachowanie ILLink ostrzegania o błędach w sposób niezależny:

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    Nie Traktuj ostrzeżeń ILLink jako błędów. Może to być przydatne, aby uniknąć wyłączania ostrzeżeń analizy przycinania do błędów podczas traktowania ostrzeżeń kompilatora jako błędów globalnie.

## <a name="removing-symbols"></a>Usuwanie symboli

Symbole są zwykle przycięte w celu dopasowania do przyciętych zestawów. Można również usunąć wszystkie symbole:

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    Usuń symbole z przyciętej aplikacji, w tym osadzone plików PDB i oddzielne pliki PDB. Dotyczy to zarówno kodu aplikacji, jak i wszelkich zależności, które są dołączone do symboli.

Zestaw SDK umożliwia także wyłączenie obsługi debugera przy użyciu właściwości `DebuggerSupport` . Gdy obsługa debugera jest wyłączona, przycinanie spowoduje automatyczne usunięcie symboli ( `TrimmerRemoveSymbols` wartość domyślna to true).

## <a name="trimming-framework-library-features"></a>Przycinanie funkcji biblioteki Framework

Kilka obszarów funkcji bibliotek struktury zawiera dyrektywy konsolidatora, które umożliwiają usunięcie kodu dla wyłączonych funkcji.

- `<DebuggerSupport>false</DebuggerSupport>`

    Usuń kod, który umożliwia lepsze środowisko debugowania. Spowoduje to również [usunięcie symboli](#removing-symbols).

- `<EnableUnsafeBinaryFormatterSerialization>false</EnableUnsafeBinaryFormatterSerialization>`

    Usuń obsługę serializacji BinaryFormatter. Aby uzyskać więcej informacji, zobacz [BinaryFormatter metody serializacji są przestarzałe](../compatibility/corefx.md#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps).

- `<EnableUnsafeUTF7Encoding>false</EnableUnsafeUTF7Encoding>`

    Usuń niezabezpieczony kod kodowania UTF-7. Aby uzyskać więcej informacji, zobacz [ścieżki kodu UTF-7 są przestarzałe](../compatibility/corefx.md#utf-7-code-paths-are-obsolete).

- `<EventSourceSupport>false</EventSourceSupport>`

    Usuń kod lub logikę powiązaną z usługą EventSource.

- `<HttpActivityPropagationSupport>false</HttpActivityPropagationSupport>`

    Usuń kod związany z obsługą diagnostyki dla systemu .NET. http.

- `<InvariantGlobalization>true</InvariantGlobalization>`

    Usuń kod i dane dotyczące globalizacji. Aby uzyskać więcej informacji, zobacz [tryb niezmienny](../run-time-config/globalization.md#invariant-mode).

- `<UseSystemResourceKeys>true</UseSystemResourceKeys>`

    Komunikaty o wyjątkach dla `System.*` zestawów. Gdy wyjątek jest zgłaszany z `System.*` zestawu, komunikat będzie uproszczony identyfikator zasobu zamiast pełnego komunikatu.

 Te właściwości spowodują, że pokrewny kod zostanie przycięty i spowoduje również wyłączenie funkcji za pośrednictwem pliku [runtimeconfig](../run-time-config/index.md) . Aby uzyskać więcej informacji na temat tych właściwości, w tym odpowiednich opcji runtimeconfig, zobacz [przełączniki funkcji](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md). Niektóre zestawy SDK mogą mieć wartości domyślne dla tych właściwości.
