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
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a><span data-ttu-id="18370-103">Atrybuty zastrzeżone: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="18370-103">Reserved attributes: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute</span></span>

<span data-ttu-id="18370-104">Te atrybuty mogą być stosowane do elementów w kodzie.</span><span class="sxs-lookup"><span data-stu-id="18370-104">These attributes can be applied to elements in your code.</span></span> <span data-ttu-id="18370-105">Dodają semantykę znaczenia do tych elementów.</span><span class="sxs-lookup"><span data-stu-id="18370-105">They add semantic meaning to those elements.</span></span> <span data-ttu-id="18370-106">Kompilator wykorzystuje te semantyki do zmiany danych wyjściowych i zgłaszania ewentualnych pomyłek przez deweloperów korzystających z kodu.</span><span class="sxs-lookup"><span data-stu-id="18370-106">The compiler uses those semantic meanings to alter its output and report possible mistakes by developers using your code.</span></span>

## <a name="conditional-attribute"></a><span data-ttu-id="18370-107">Atrybut `Conditional`</span><span class="sxs-lookup"><span data-stu-id="18370-107">`Conditional` attribute</span></span>

<span data-ttu-id="18370-108">Ten `Conditional` atrybut wykonuje metodę zależną od identyfikatora przetwarzania wstępnego.</span><span class="sxs-lookup"><span data-stu-id="18370-108">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="18370-109">`Conditional`Atrybut jest alias dla <xref:System.Diagnostics.ConditionalAttribute> i może być zastosowany do metody lub klasy atrybutu.</span><span class="sxs-lookup"><span data-stu-id="18370-109">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>

<span data-ttu-id="18370-110">W poniższym przykładzie `Conditional` zastosowano metodę, aby włączyć lub wyłączyć wyświetlanie informacji diagnostycznych specyficznych dla programu:</span><span class="sxs-lookup"><span data-stu-id="18370-110">In the following example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>

:::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

<span data-ttu-id="18370-111">Jeśli `TRACE_ON` Identyfikator nie jest zdefiniowany, dane wyjściowe śledzenia nie są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="18370-111">If the `TRACE_ON` identifier isn't defined, the trace output isn't displayed.</span></span> <span data-ttu-id="18370-112">Eksploruj samodzielnie w oknie interaktywnym.</span><span class="sxs-lookup"><span data-stu-id="18370-112">Explore for yourself in the interactive window.</span></span>

<span data-ttu-id="18370-113">Ten `Conditional` atrybut jest często używany z `DEBUG` identyfikatorem, aby włączyć funkcje śledzenia i rejestrowania dla kompilacji debugowania, ale nie w kompilacjach wydania, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="18370-113">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

<span data-ttu-id="18370-114">Gdy wywoływana jest metoda oznaczona warunkowo, obecność lub brak określonego symbolu przetwarzania wstępnego określa, czy wywołanie jest dołączone czy pominięte.</span><span class="sxs-lookup"><span data-stu-id="18370-114">When a method marked conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="18370-115">Jeśli symbol jest zdefiniowany, wywołanie jest dołączone; w przeciwnym razie wywołanie zostanie pominięte.</span><span class="sxs-lookup"><span data-stu-id="18370-115">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="18370-116">Metoda warunkowa musi być metodą w deklaracji klasy lub struktury i musi mieć `void` Typ zwracany.</span><span class="sxs-lookup"><span data-stu-id="18370-116">A conditional method must be a method in a class or struct declaration and must have a `void` return type.</span></span> <span data-ttu-id="18370-117">Korzystanie z programu `Conditional` to Oczyszczarka, bardziej elegancki i mniej podatne na błędy niż zawarte w `#if…#endif` blokach.</span><span class="sxs-lookup"><span data-stu-id="18370-117">Using `Conditional` is cleaner, more elegant, and less error-prone than enclosing methods inside `#if…#endif` blocks.</span></span>

<span data-ttu-id="18370-118">Jeśli metoda ma wiele `Conditional` atrybutów, wywołanie metody jest dołączane, jeśli co najmniej jeden symbol warunkowy jest zdefiniowany (symbole są logicznie połączone ze sobą przy użyciu operatora OR).</span><span class="sxs-lookup"><span data-stu-id="18370-118">If a method has multiple `Conditional` attributes, a call to the method is included if at one or more conditional symbols is defined (the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="18370-119">W poniższym przykładzie, obecność `A` lub `B` wynik wywołania metody:</span><span class="sxs-lookup"><span data-stu-id="18370-119">In the following example, the presence of either `A` or `B` results in a method call:</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="18370-120">Używanie `Conditional` z klasami atrybutów</span><span class="sxs-lookup"><span data-stu-id="18370-120">Using `Conditional` with attribute classes</span></span>

<span data-ttu-id="18370-121">Ten `Conditional` atrybut może być również stosowany do definicji klasy atrybutu.</span><span class="sxs-lookup"><span data-stu-id="18370-121">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="18370-122">W poniższym przykładzie atrybut niestandardowy `Documentation` będzie dodawać tylko informacje do metadanych, jeśli `DEBUG` jest zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="18370-122">In the following example, the custom attribute `Documentation` will only add information to the metadata if `DEBUG` is defined.</span></span>

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a><span data-ttu-id="18370-123">Atrybut `Obsolete`</span><span class="sxs-lookup"><span data-stu-id="18370-123">`Obsolete` attribute</span></span>

<span data-ttu-id="18370-124">Ten `Obsolete` atrybut oznacza element kodu, który nie jest już zalecany do użycia.</span><span class="sxs-lookup"><span data-stu-id="18370-124">The `Obsolete` attribute marks a code element as no longer recommended for use.</span></span> <span data-ttu-id="18370-125">Użycie jednostki oznaczonej jako przestarzałe powoduje wygenerowanie ostrzeżenia lub błędu.</span><span class="sxs-lookup"><span data-stu-id="18370-125">Use of an entity marked obsolete generates a warning or an error.</span></span> <span data-ttu-id="18370-126">Ten `Obsolete` atrybut jest atrybutem jednokrotnego użycia i może być stosowany do każdej jednostki, która zezwala na atrybuty.</span><span class="sxs-lookup"><span data-stu-id="18370-126">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="18370-127">`Obsolete` jest aliasem dla <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="18370-127">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>

<span data-ttu-id="18370-128">W poniższym przykładzie `Obsolete` atrybut jest stosowany do klasy `A` i metody `B.OldMethod` .</span><span class="sxs-lookup"><span data-stu-id="18370-128">In the following example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="18370-129">Ponieważ drugi argument konstruktora atrybutu stosowany do `B.OldMethod` jest ustawiony na `true` , ta metoda spowoduje błąd kompilatora, podczas gdy użycie klasy `A` spowoduje po prostu wygenerowanie ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="18370-129">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="18370-130">Jednak wywoływanie `B.NewMethod` nie powoduje żadnych ostrzeżeń ani błędów.</span><span class="sxs-lookup"><span data-stu-id="18370-130">Calling `B.NewMethod`, however, produces no warning or error.</span></span> <span data-ttu-id="18370-131">Na przykład jeśli używasz go z poprzednimi definicjami, poniższy kod generuje dwie ostrzeżenia i jeden błąd:</span><span class="sxs-lookup"><span data-stu-id="18370-131">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>

:::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

<span data-ttu-id="18370-132">Ciąg dostarczony jako pierwszy argument konstruktora atrybutu będzie wyświetlany jako część ostrzeżenia lub błędu.</span><span class="sxs-lookup"><span data-stu-id="18370-132">The string provided as the first argument to the attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="18370-133">Generowane są dwa ostrzeżenia dla klasy `A` : jeden dla deklaracji klasy Reference i jeden dla konstruktora klasy.</span><span class="sxs-lookup"><span data-stu-id="18370-133">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span> <span data-ttu-id="18370-134">Ten `Obsolete` atrybut może być używany bez argumentów, ale wraz z wyjaśnieniem, co należy użyć zamiast tego jest zalecane.</span><span class="sxs-lookup"><span data-stu-id="18370-134">The `Obsolete` attribute can be used without arguments, but including an explanation what to use instead is recommended.</span></span>

## <a name="attributeusage-attribute"></a><span data-ttu-id="18370-135">Atrybut `AttributeUsage`</span><span class="sxs-lookup"><span data-stu-id="18370-135">`AttributeUsage` attribute</span></span>

<span data-ttu-id="18370-136">Ten `AttributeUsage` atrybut określa, w jaki sposób można używać klasy atrybutów niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="18370-136">The `AttributeUsage` attribute determines how a custom attribute class can be used.</span></span> <span data-ttu-id="18370-137"><xref:System.AttributeUsageAttribute> jest atrybutem stosowanym do definicji atrybutów niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="18370-137"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="18370-138">Ten `AttributeUsage` atrybut umożliwia kontrolowanie:</span><span class="sxs-lookup"><span data-stu-id="18370-138">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="18370-139">Do których elementów programu można zastosować atrybut.</span><span class="sxs-lookup"><span data-stu-id="18370-139">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="18370-140">O ile nie zostanie to ograniczone, atrybut może być stosowany do dowolnego z następujących elementów programu:</span><span class="sxs-lookup"><span data-stu-id="18370-140">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="18370-141">zestaw</span><span class="sxs-lookup"><span data-stu-id="18370-141">assembly</span></span>
  - <span data-ttu-id="18370-142">moduł</span><span class="sxs-lookup"><span data-stu-id="18370-142">module</span></span>
  - <span data-ttu-id="18370-143">pole</span><span class="sxs-lookup"><span data-stu-id="18370-143">field</span></span>
  - <span data-ttu-id="18370-144">event</span><span class="sxs-lookup"><span data-stu-id="18370-144">event</span></span>
  - <span data-ttu-id="18370-145">method</span><span class="sxs-lookup"><span data-stu-id="18370-145">method</span></span>
  - <span data-ttu-id="18370-146">param</span><span class="sxs-lookup"><span data-stu-id="18370-146">param</span></span>
  - <span data-ttu-id="18370-147">property</span><span class="sxs-lookup"><span data-stu-id="18370-147">property</span></span>
  - <span data-ttu-id="18370-148">return</span><span class="sxs-lookup"><span data-stu-id="18370-148">return</span></span>
  - <span data-ttu-id="18370-149">typ</span><span class="sxs-lookup"><span data-stu-id="18370-149">type</span></span>
- <span data-ttu-id="18370-150">Czy atrybut może być stosowany do pojedynczego elementu programu wiele razy.</span><span class="sxs-lookup"><span data-stu-id="18370-150">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="18370-151">Czy atrybuty są dziedziczone przez klasy pochodne.</span><span class="sxs-lookup"><span data-stu-id="18370-151">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="18370-152">Ustawienia domyślne wyglądają jak w poniższym przykładzie, jeśli zostały zastosowane jawnie:</span><span class="sxs-lookup"><span data-stu-id="18370-152">The default settings look like the following example when applied explicitly:</span></span>

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

<span data-ttu-id="18370-153">W tym przykładzie `NewAttribute` Klasa może zostać zastosowana do dowolnego obsługiwanego elementu programu.</span><span class="sxs-lookup"><span data-stu-id="18370-153">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="18370-154">Można go jednak zastosować tylko raz do każdej jednostki.</span><span class="sxs-lookup"><span data-stu-id="18370-154">But it can be applied only once to each entity.</span></span> <span data-ttu-id="18370-155">Atrybut jest dziedziczony przez klasy pochodne w przypadku zastosowania do klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="18370-155">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="18370-156"><xref:System.AttributeUsageAttribute.AllowMultiple>Argumenty i <xref:System.AttributeUsageAttribute.Inherited> są opcjonalne, więc Poniższy kod ma ten sam skutek:</span><span class="sxs-lookup"><span data-stu-id="18370-156">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

<span data-ttu-id="18370-157">Pierwszy <xref:System.AttributeUsageAttribute> argument musi być co najmniej jednym elementem <xref:System.AttributeTargets> wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="18370-157">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="18370-158">Z operatorem OR można łączyć wiele typów docelowych, podobnie jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="18370-158">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

<span data-ttu-id="18370-159">Począwszy od języka C# 7,3, atrybuty mogą być stosowane do właściwości lub pola zapasowego dla właściwości, która jest implementowana.</span><span class="sxs-lookup"><span data-stu-id="18370-159">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="18370-160">Ten atrybut ma zastosowanie do właściwości, chyba że określisz `field` specyfikator dla atrybutu.</span><span class="sxs-lookup"><span data-stu-id="18370-160">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="18370-161">Oba są przedstawione w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="18370-161">Both are shown in the following example:</span></span>

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

<span data-ttu-id="18370-162">Jeśli <xref:System.AttributeUsageAttribute.AllowMultiple> argument ma wartość `true` , wynikowy atrybut może zostać zastosowany więcej niż raz do pojedynczej jednostki, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="18370-162">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

<span data-ttu-id="18370-163">W tym przypadku `MultiUseAttribute` może być stosowana wielokrotnie, ponieważ `AllowMultiple` jest ustawiona na `true` .</span><span class="sxs-lookup"><span data-stu-id="18370-163">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="18370-164">Oba formaty wyświetlane na potrzeby stosowania wielu atrybutów są prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="18370-164">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="18370-165">Jeśli <xref:System.AttributeUsageAttribute.Inherited> jest `false` , atrybut nie jest dziedziczony przez klasy pochodne od klasy z atrybutami.</span><span class="sxs-lookup"><span data-stu-id="18370-165">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="18370-166">Przykład:</span><span class="sxs-lookup"><span data-stu-id="18370-166">For example:</span></span>

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

<span data-ttu-id="18370-167">W tym przypadku `NonInheritedAttribute` nie jest on stosowany do `DClass` dziedziczenia.</span><span class="sxs-lookup"><span data-stu-id="18370-167">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="see-also"></a><span data-ttu-id="18370-168">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="18370-168">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="18370-169">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="18370-169">Attributes</span></span>](../../../standard/attributes/index.md)
- [<span data-ttu-id="18370-170">Odbicie</span><span class="sxs-lookup"><span data-stu-id="18370-170">Reflection</span></span>](../../programming-guide/concepts/reflection.md)
