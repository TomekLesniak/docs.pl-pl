---
ms.openlocfilehash: 424872b25436c7fcbe603639028e813eed6f9b99
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497061"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a>Zestawy skompilowane z wyrażeniem regularnym. CompileToAssembly są rozdzielonymi między 4,0 i 4,5

#### <a name="details"></a>Szczegóły

Jeśli zestaw skompilowanych wyrażeń regularnych jest skompilowany przy użyciu .NET Framework 4,5, ale jest przeznaczony dla .NET Framework 4, próba użycia jednego z wyrażeń regularnych w tym zestawie w systemie z zainstalowanym programem .NET Framework 4 zgłasza wyjątek.

#### <a name="suggestion"></a>Sugestia

Aby obejść ten problem, można wykonać jedną z następujących czynności:<ul><li>Kompiluj zestaw zawierający wyrażenia regularne z .NET Framework 4.</li><li>Użyj interpretowanego wyrażenia regularnego.</li></ul>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)`

-->
