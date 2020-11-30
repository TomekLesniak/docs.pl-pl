---
title: 'Atrybuty zastrzeżone języka C#: warunkowe, przestarzałe, AttributeUsage'
ms.date: 04/09/2020
description: Te atrybuty są interpretowane przez kompilator, aby wpływać na kod wygenerowany przez kompilator
ms.openlocfilehash: c6d697dd08233ffc88900949998047137ee170a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/29/2020
ms.locfileid: "82021760"
---
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a>Atrybuty zastrzeżone: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute

Te atrybuty mogą być stosowane do elementów w kodzie. Dodają semantykę znaczenia do tych elementów. Kompilator wykorzystuje te semantyki do zmiany danych wyjściowych i zgłaszania ewentualnych pomyłek przez deweloperów korzystających z kodu.

## <a name="conditional-attribute"></a>Atrybut `Conditional`

Ten `Conditional` atrybut wykonuje metodę zależną od identyfikatora przetwarzania wstępnego. `Conditional`Atrybut jest alias dla <xref:System.Diagnostics.ConditionalAttribute> i może być zastosowany do metody lub klasy atrybutu.

W poniższym przykładzie `Conditional` zastosowano metodę, aby włączyć lub wyłączyć wyświetlanie informacji diagnostycznych specyficznych dla programu:

:::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

Jeśli `TRACE_ON` Identyfikator nie jest zdefiniowany, dane wyjściowe śledzenia nie są wyświetlane. Eksploruj samodzielnie w oknie interaktywnym.

Ten `Conditional` atrybut jest często używany z `DEBUG` identyfikatorem, aby włączyć funkcje śledzenia i rejestrowania dla kompilacji debugowania, ale nie w kompilacjach wydania, jak pokazano w następującym przykładzie:

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

Gdy wywoływana jest metoda oznaczona warunkowo, obecność lub brak określonego symbolu przetwarzania wstępnego określa, czy wywołanie jest dołączone czy pominięte. Jeśli symbol jest zdefiniowany, wywołanie jest dołączone; w przeciwnym razie wywołanie zostanie pominięte. Metoda warunkowa musi być metodą w deklaracji klasy lub struktury i musi mieć `void` Typ zwracany. Korzystanie z programu `Conditional` to Oczyszczarka, bardziej elegancki i mniej podatne na błędy niż zawarte w `#if…#endif` blokach.

Jeśli metoda ma wiele `Conditional` atrybutów, wywołanie metody jest dołączane, jeśli co najmniej jeden symbol warunkowy jest zdefiniowany (symbole są logicznie połączone ze sobą przy użyciu operatora OR). W poniższym przykładzie, obecność `A` lub `B` wynik wywołania metody:

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a>Używanie `Conditional` z klasami atrybutów

Ten `Conditional` atrybut może być również stosowany do definicji klasy atrybutu. W poniższym przykładzie atrybut niestandardowy `Documentation` będzie dodawać tylko informacje do metadanych, jeśli `DEBUG` jest zdefiniowany.

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a>Atrybut `Obsolete`

Ten `Obsolete` atrybut oznacza element kodu, który nie jest już zalecany do użycia. Użycie jednostki oznaczonej jako przestarzałe powoduje wygenerowanie ostrzeżenia lub błędu. Ten `Obsolete` atrybut jest atrybutem jednokrotnego użycia i może być stosowany do każdej jednostki, która zezwala na atrybuty. `Obsolete` jest aliasem dla <xref:System.ObsoleteAttribute> .

W poniższym przykładzie `Obsolete` atrybut jest stosowany do klasy `A` i metody `B.OldMethod` . Ponieważ drugi argument konstruktora atrybutu stosowany do `B.OldMethod` jest ustawiony na `true` , ta metoda spowoduje błąd kompilatora, podczas gdy użycie klasy `A` spowoduje po prostu wygenerowanie ostrzeżenia. Jednak wywoływanie `B.NewMethod` nie powoduje żadnych ostrzeżeń ani błędów. Na przykład jeśli używasz go z poprzednimi definicjami, poniższy kod generuje dwie ostrzeżenia i jeden błąd:

:::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

Ciąg dostarczony jako pierwszy argument konstruktora atrybutu będzie wyświetlany jako część ostrzeżenia lub błędu. Generowane są dwa ostrzeżenia dla klasy `A` : jeden dla deklaracji klasy Reference i jeden dla konstruktora klasy. Ten `Obsolete` atrybut może być używany bez argumentów, ale wraz z wyjaśnieniem, co należy użyć zamiast tego jest zalecane.

## <a name="attributeusage-attribute"></a>Atrybut `AttributeUsage`

Ten `AttributeUsage` atrybut określa, w jaki sposób można używać klasy atrybutów niestandardowych. <xref:System.AttributeUsageAttribute> jest atrybutem stosowanym do definicji atrybutów niestandardowych. Ten `AttributeUsage` atrybut umożliwia kontrolowanie:

- Do których elementów programu można zastosować atrybut. O ile nie zostanie to ograniczone, atrybut może być stosowany do dowolnego z następujących elementów programu:
  - zestaw
  - moduł
  - pole
  - event
  - method
  - param
  - property
  - return
  - typ
- Czy atrybut może być stosowany do pojedynczego elementu programu wiele razy.
- Czy atrybuty są dziedziczone przez klasy pochodne.

Ustawienia domyślne wyglądają jak w poniższym przykładzie, jeśli zostały zastosowane jawnie:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

W tym przykładzie `NewAttribute` Klasa może zostać zastosowana do dowolnego obsługiwanego elementu programu. Można go jednak zastosować tylko raz do każdej jednostki. Atrybut jest dziedziczony przez klasy pochodne w przypadku zastosowania do klasy bazowej.

<xref:System.AttributeUsageAttribute.AllowMultiple>Argumenty i <xref:System.AttributeUsageAttribute.Inherited> są opcjonalne, więc Poniższy kod ma ten sam skutek:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

Pierwszy <xref:System.AttributeUsageAttribute> argument musi być co najmniej jednym elementem <xref:System.AttributeTargets> wyliczenia. Z operatorem OR można łączyć wiele typów docelowych, podobnie jak w poniższym przykładzie:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

Począwszy od języka C# 7,3, atrybuty mogą być stosowane do właściwości lub pola zapasowego dla właściwości, która jest implementowana. Ten atrybut ma zastosowanie do właściwości, chyba że określisz `field` specyfikator dla atrybutu. Oba są przedstawione w następującym przykładzie:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

Jeśli <xref:System.AttributeUsageAttribute.AllowMultiple> argument ma wartość `true` , wynikowy atrybut może zostać zastosowany więcej niż raz do pojedynczej jednostki, jak pokazano w następującym przykładzie:

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

W tym przypadku `MultiUseAttribute` może być stosowana wielokrotnie, ponieważ `AllowMultiple` jest ustawiona na `true` . Oba formaty wyświetlane na potrzeby stosowania wielu atrybutów są prawidłowe.

Jeśli <xref:System.AttributeUsageAttribute.Inherited> jest `false` , atrybut nie jest dziedziczony przez klasy pochodne od klasy z atrybutami. Przykład:

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

W tym przypadku `NonInheritedAttribute` nie jest on stosowany do `DClass` dziedziczenia.

## <a name="see-also"></a>Zobacz też

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Atrybuty](../../../standard/attributes/index.md)
- [Odbicie](../../programming-guide/concepts/reflection.md)
