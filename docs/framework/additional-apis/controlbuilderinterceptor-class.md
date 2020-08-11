---
title: Klasa ControlBuilderInterceptor
ms.date: 08/11/2020
api_name:
- System.Web.Compilation.ControlBuilderInterceptor
api_location:
- System.Web.dll
api_type:
- Assembly
topic_type:
- apiref
ms.openlocfilehash: 312d977f832d262b1bebc6638280b67b133babdf
ms.sourcegitcommit: 70d6a7e4f7187cbfa332f0f8be76566f7828cfcd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88084398"
---
# <a name="controlbuilderinterceptor-class"></a><span data-ttu-id="6c989-102">Klasa ControlBuilderInterceptor</span><span class="sxs-lookup"><span data-stu-id="6c989-102">ControlBuilderInterceptor class</span></span>

<span data-ttu-id="6c989-103">`ControlBuilderInterceptor`Klasa umożliwia dostosowanie lub sterowanie procesem kompilacji.</span><span class="sxs-lookup"><span data-stu-id="6c989-103">The `ControlBuilderInterceptor` class allows the compilation process to be customized or controlled.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c989-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6c989-104">Syntax</span></span>

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> <span data-ttu-id="6c989-105">`ControlBuilderInterceptor`Klasa jest wewnętrzna i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="6c989-105">The `ControlBuilderInterceptor` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6c989-106">Zgodnie z opisem w sekcji uwagi, istnienie tego typu może być sprawdzane w celu ustalenia, czy jest dostępna obsługa typu interceptora.</span><span class="sxs-lookup"><span data-stu-id="6c989-106">As described in the Remarks section, the existence of this type can be checked to determine whether interceptor type support is present.</span></span> <span data-ttu-id="6c989-107">Firma Microsoft nie obsługuje żadnych innych zastosowań tej klasy w aplikacji produkcyjnej w żadnym przypadku.</span><span class="sxs-lookup"><span data-stu-id="6c989-107">Microsoft does not support any other use of this class in a production application under any circumstance.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c989-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6c989-108">Remarks</span></span>

<span data-ttu-id="6c989-109">W .NET Framework 2,0 i .NET Framework 3,5, Aktualizacja z [sierpnia 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) dodaliśmy obsługę użycia typu interceptora do dostosowywania lub kontrolowania procesu kompilacji.</span><span class="sxs-lookup"><span data-stu-id="6c989-109">In .NET Framework 2.0 and .NET Framework 3.5, the [August 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) updates added support for using an interceptor type to customize or control the compilation process.</span></span> <span data-ttu-id="6c989-110">Możesz określić, czy ta obsługa jest obecna przy użyciu programu <xref:System.Type.GetType?displayProperty=nameWithType> , aby sprawdzić istnienie `ControlBuilderInterceptor` typu, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="6c989-110">You can determine whether this support is present by using <xref:System.Type.GetType?displayProperty=nameWithType> to check the existence of the `ControlBuilderInterceptor` type, as demonstrated in the following code.</span></span>

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

<span data-ttu-id="6c989-111">Jeśli zwracana wartość jest inna niż null, jest dostępna obsługa interceptora.</span><span class="sxs-lookup"><span data-stu-id="6c989-111">If the return value is non-null, then interceptor support is present.</span></span> <span data-ttu-id="6c989-112">Jeśli zwracana wartość to `null` lub wyjątek jest zgłaszany, aktualizacje 2020 sierpnia nie zostały zainstalowane, a obsługa interceptora nie jest obecna.</span><span class="sxs-lookup"><span data-stu-id="6c989-112">If the return value is `null`, or if an exception is thrown, then the August 2020 updates have not been installed, and interceptor support is absent.</span></span>

<span data-ttu-id="6c989-113">Jeśli istnieje obsługa przechwycenia, można napisać i zarejestrować typ interceptora, który będzie współdziałać z procesem kompilacji w taki sam sposób, jak <xref:System.Web.Compilation.ControlBuilderInterceptor> w przypadku nowszych wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6c989-113">If interceptor support is present, you can write and register an interceptor type that will interact with the compilation process in exactly the same way that <xref:System.Web.Compilation.ControlBuilderInterceptor> does on later versions of .NET Framework.</span></span> <span data-ttu-id="6c989-114">W .NET Framework 2,0 i .NET Framework 3,5, typ interceptora może być dowolną klasą, która spełnia następujące wymagania:</span><span class="sxs-lookup"><span data-stu-id="6c989-114">In .NET Framework 2.0 and .NET Framework 3.5, the interceptor type can be any class that meets the following requirements:</span></span>

* <span data-ttu-id="6c989-115">Ma publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="6c989-115">Has a public, parameterless constructor.</span></span>
* <span data-ttu-id="6c989-116">Ma publiczne, niestatyczne metody o nazwie `PreControlBuilderInit` i `OnProcessGeneratedCode` mające taki sam podpis i semantykę jak <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> metody i <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> , które istnieją w nowszych wersjach .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6c989-116">Has public, non-static methods named `PreControlBuilderInit` and `OnProcessGeneratedCode` that have the same signature and semantics as the <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> and <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> methods, which exist in later versions of .NET Framework.</span></span>

<span data-ttu-id="6c989-117">Zarejestruj typ interceptora przy użyciu `aspnet:20ControlBuilderInterceptor` klucza w ustawieniach aplikacji ASP.NET ( `<appSettings>` ).</span><span class="sxs-lookup"><span data-stu-id="6c989-117">Register the interceptor type by using the `aspnet:20ControlBuilderInterceptor` key in ASP.NET application settings (`<appSettings>`).</span></span> <span data-ttu-id="6c989-118">To ustawienie aplikacji musi znajdować się na liście plików *web.config* komputera lub aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6c989-118">This application setting must be listed in your computer or application *web.config* file.</span></span> <span data-ttu-id="6c989-119">Określ typ interceptora przy użyciu nazwy typu kwalifikowanego dla zestawu.</span><span class="sxs-lookup"><span data-stu-id="6c989-119">Specify the interceptor type by using its assembly-qualified type name.</span></span> <span data-ttu-id="6c989-120">Poniższy przykład pokazuje, jak zarejestrować typ interceptora o nazwie `Fabrikam.Interceptor` .</span><span class="sxs-lookup"><span data-stu-id="6c989-120">The following example shows how to register an interceptor type named `Fabrikam.Interceptor`.</span></span>

```xml
<configuration>
  ...
  <appSettings>
    ...
    <add key="aspnet:20ControlBuilderInterceptor"
         value="Fabrikam.Interceptor, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
  </appSettings>
</configuration>

To retrieve the assembly-qualified name of a type, use the <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> property, as demonstrated in the following code.

```csharp
string assemblyQualifiedName = typeof(Fabrikam.Interceptor).AssemblyQualifiedName;
```

<span data-ttu-id="6c989-121">Gdy jest obecna obsługa przechwyceń, proces kompilacji współdziała z wymienionym typem w sposób opisany powyżej.</span><span class="sxs-lookup"><span data-stu-id="6c989-121">When interceptor support is present, the compilation process interacts with the listed type in the manner described above.</span></span> <span data-ttu-id="6c989-122">Gdy nie ma obsługi przechwycenia, ustawienie aplikacji jest ignorowane i nie ma żadnego efektu.</span><span class="sxs-lookup"><span data-stu-id="6c989-122">When interceptor support is absent, the application setting is ignored and has no effect.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c989-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6c989-123">Requirements</span></span>

<span data-ttu-id="6c989-124">**Przestrzeń nazw:** System. Web. kompilacja</span><span class="sxs-lookup"><span data-stu-id="6c989-124">**Namespace:** System.Web.Compilation</span></span>

<span data-ttu-id="6c989-125">**Zestaw:** System. Web (w System.Web.dll)</span><span class="sxs-lookup"><span data-stu-id="6c989-125">**Assembly:** System.Web (in System.Web.dll)</span></span>

<span data-ttu-id="6c989-126">**.NET Framework wersje:** 3,5, 2,0</span><span class="sxs-lookup"><span data-stu-id="6c989-126">**.NET Framework versions:** 3.5, 2.0</span></span>
