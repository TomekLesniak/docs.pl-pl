---
ms.openlocfilehash: 424872b25436c7fcbe603639028e813eed6f9b99
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497061"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="49c10-101">Zestawy skompilowane z wyrażeniem regularnym. CompileToAssembly są rozdzielonymi między 4,0 i 4,5</span><span class="sxs-lookup"><span data-stu-id="49c10-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="49c10-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="49c10-102">Details</span></span>

<span data-ttu-id="49c10-103">Jeśli zestaw skompilowanych wyrażeń regularnych jest skompilowany przy użyciu .NET Framework 4,5, ale jest przeznaczony dla .NET Framework 4, próba użycia jednego z wyrażeń regularnych w tym zestawie w systemie z zainstalowanym programem .NET Framework 4 zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="49c10-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="49c10-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="49c10-104">Suggestion</span></span>

<span data-ttu-id="49c10-105">Aby obejść ten problem, można wykonać jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="49c10-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="49c10-106">Kompiluj zestaw zawierający wyrażenia regularne z .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="49c10-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="49c10-107">Użyj interpretowanego wyrażenia regularnego.</span><span class="sxs-lookup"><span data-stu-id="49c10-107">Use an interpreted regular expression.</span></span></li></ul>

| <span data-ttu-id="49c10-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="49c10-108">Name</span></span>    | <span data-ttu-id="49c10-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="49c10-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="49c10-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="49c10-110">Scope</span></span>   |<span data-ttu-id="49c10-111">Mały</span><span class="sxs-lookup"><span data-stu-id="49c10-111">Minor</span></span>|
|<span data-ttu-id="49c10-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="49c10-112">Version</span></span>|<span data-ttu-id="49c10-113">4.5</span><span class="sxs-lookup"><span data-stu-id="49c10-113">4.5</span></span>|
|<span data-ttu-id="49c10-114">Typ</span><span class="sxs-lookup"><span data-stu-id="49c10-114">Type</span></span>|<span data-ttu-id="49c10-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="49c10-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="49c10-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="49c10-116">Affected APIs</span></span>

- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)`

-->
