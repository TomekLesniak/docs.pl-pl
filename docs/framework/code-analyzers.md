---
title: Analizatory kodu dla .NET Framework
titleSuffix: ''
description: Dowiedz się, jak używać analizatorów w pakiecie .NET Framework analizatorów, aby znajdować i rozwiązywać problemy w kodzie.
author: billwagner
ms.author: wiwagn
ms.date: 10/23/2020
ms.openlocfilehash: 69dfbc9f9645c7f602ffbce46308b241c119fd96
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687904"
---
# <a name="code-analysis"></a>Analiza kodu

Analizatorów kodu można użyć, aby znaleźć potencjalne problemy w .NET Framework kodzie aplikacji. Analizatory wyszukują potencjalne problemy i sugerują dla nich poprawki.

Analizatory kodu oparte na Roslyn działają interaktywnie w programie Visual Studio podczas pisania kodu lub jako część kompilacji elementu konfiguracji. Analizatory należy dodać do projektu tak szybko, jak to możliwe w cyklu programowania. Wkrótce znajdziesz ewentualne potencjalne problemy w kodzie, tym łatwiejsze jest ich naprawa. Analizatory sprawdzają problemy w istniejącym kodzie i ostrzegają o nowych problemach podczas dalszej pracy.

## <a name="install-and-configure-analyzers"></a>Instalowanie i Konfigurowanie analizatorów

Analizator .NET Framework jest dostarczany w pakiecie NuGet [Microsoft. NETFramework. analizators](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) . Ten pakiet udostępnia analizatory charakterystyczne dla .NET Framework interfejsów API, które obejmują analizatory zabezpieczeń. Pakiet jest dostarczany z [pakietem Microsoft. CodeAnalysis. FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers), dlatego w przypadku zainstalowania tego pakietu nie trzeba oddzielnie instalować .NET Framework analizatorów.

Zainstaluj pakiet NuGet na każdym projekcie, w którym mają być uruchamiane analizatory. Tylko jeden Deweloper musi dodać je do projektu. Pakiet analizatora jest zależnością projektu i będzie działać na każdym komputerze dewelopera, gdy ma zaktualizowane rozwiązanie.

Aby zainstalować pakiet, kliknij prawym przyciskiem myszy projekt i wybierz polecenie "Zarządzaj zależnościami". W Eksploratorze NuGet Wyszukaj ciąg "Microsoft. NetFramework. analizatory". Zainstaluj najnowszą stabilną wersję we wszystkich projektach w rozwiązaniu.

## <a name="use-the-analyzers"></a>Korzystanie z analizatorów

Po zainstalowaniu pakietu NuGet Skompiluj rozwiązanie. Analizator zgłosi wszelkie problemy, które znajdują się w bazie kodu. Problemy są raportowane jako ostrzeżenia w oknie Lista błędów programu Visual Studio, jak pokazano na poniższej ilustracji:

![Problemy zgłoszone przez analizatory .NET Framework.](./media/framework-analyzers-2.png)

Podczas pisania kodu zobaczysz zygzaki poniżej dowolnego potencjalnego problemu w kodzie.
Umieść wskaźnik myszy nad dowolnym problemem, aby uzyskać więcej informacji, i zapoznaj się z sugestiami dotyczącymi ewentualnych poprawek, jak pokazano na poniższej ilustracji:

![Interaktywny raport dotyczący problemów znalezionych przez analizatory kodu.](./media/framework-analyzers-1.png)

Aby uzyskać więcej informacji, zobacz [Analiza kodu w programie Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview).

## <a name="types-of-rules"></a>Typy reguł

Analizatory badają kod w rozwiązaniu i ostrzeżenia powierzchni z `CA` prefiksem. Aby uzyskać listę wszystkich możliwych ostrzeżeń, zobacz [reguły jakości kodu](../fundamentals/code-analysis/quality-rules/index.md). Tylko niektóre z tych ostrzeżeń mają zastosowanie do .NET Framework interfejsów API, w tym:

- [CA1058: Typy nie powinny rozszerzać niektórych typów podstawowych](../fundamentals/code-analysis/quality-rules/ca1058.md)

- [CA2153: nie Przechwytuj wyjątków uszkodzonych Stanów](../fundamentals/code-analysis/quality-rules/ca2153.md)

- [CA2229: Zaimplementuj konstruktory serializacji](../fundamentals/code-analysis/quality-rules/ca2229.md)

- [CA2235: Oznacz wszystkie pola nieprzeznaczone do serializacji](../fundamentals/code-analysis/quality-rules/ca2235.md)

- [CA2237: Oznacz typy ISerializable z możliwością serializacji](../fundamentals/code-analysis/quality-rules/ca2237.md)

- [CA3075: niezabezpieczone przetwarzanie DTD w kodzie XML](../fundamentals/code-analysis/quality-rules/ca3075.md)

- [CA5350: nie używaj słabych algorytmów kryptograficznych](../fundamentals/code-analysis/quality-rules/ca5350.md)

- [CA5351 nie używają uszkodzonych algorytmów kryptograficznych](../fundamentals/code-analysis/quality-rules/ca5351.md)

## <a name="see-also"></a>Zobacz także

- [Analiza kodu w programie Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview)
- [Analiza kodu w zestawie SDK platformy .NET](../fundamentals/code-analysis/overview.md)
