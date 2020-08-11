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
# <a name="controlbuilderinterceptor-class"></a>Klasa ControlBuilderInterceptor

`ControlBuilderInterceptor`Klasa umożliwia dostosowanie lub sterowanie procesem kompilacji.

## <a name="syntax"></a>Składnia

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> `ControlBuilderInterceptor`Klasa jest wewnętrzna i nie jest przeznaczona do użycia bezpośrednio w kodzie.
>
> Zgodnie z opisem w sekcji uwagi, istnienie tego typu może być sprawdzane w celu ustalenia, czy jest dostępna obsługa typu interceptora. Firma Microsoft nie obsługuje żadnych innych zastosowań tej klasy w aplikacji produkcyjnej w żadnym przypadku.

## <a name="remarks"></a>Uwagi

W .NET Framework 2,0 i .NET Framework 3,5, Aktualizacja z [sierpnia 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) dodaliśmy obsługę użycia typu interceptora do dostosowywania lub kontrolowania procesu kompilacji. Możesz określić, czy ta obsługa jest obecna przy użyciu programu <xref:System.Type.GetType?displayProperty=nameWithType> , aby sprawdzić istnienie `ControlBuilderInterceptor` typu, jak pokazano w poniższym kodzie.

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

Jeśli zwracana wartość jest inna niż null, jest dostępna obsługa interceptora. Jeśli zwracana wartość to `null` lub wyjątek jest zgłaszany, aktualizacje 2020 sierpnia nie zostały zainstalowane, a obsługa interceptora nie jest obecna.

Jeśli istnieje obsługa przechwycenia, można napisać i zarejestrować typ interceptora, który będzie współdziałać z procesem kompilacji w taki sam sposób, jak <xref:System.Web.Compilation.ControlBuilderInterceptor> w przypadku nowszych wersji .NET Framework. W .NET Framework 2,0 i .NET Framework 3,5, typ interceptora może być dowolną klasą, która spełnia następujące wymagania:

* Ma publiczny Konstruktor bez parametrów.
* Ma publiczne, niestatyczne metody o nazwie `PreControlBuilderInit` i `OnProcessGeneratedCode` mające taki sam podpis i semantykę jak <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> metody i <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> , które istnieją w nowszych wersjach .NET Framework.

Zarejestruj typ interceptora przy użyciu `aspnet:20ControlBuilderInterceptor` klucza w ustawieniach aplikacji ASP.NET ( `<appSettings>` ). To ustawienie aplikacji musi znajdować się na liście plików *web.config* komputera lub aplikacji. Określ typ interceptora przy użyciu nazwy typu kwalifikowanego dla zestawu. Poniższy przykład pokazuje, jak zarejestrować typ interceptora o nazwie `Fabrikam.Interceptor` .

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

Gdy jest obecna obsługa przechwyceń, proces kompilacji współdziała z wymienionym typem w sposób opisany powyżej. Gdy nie ma obsługi przechwycenia, ustawienie aplikacji jest ignorowane i nie ma żadnego efektu.

## <a name="requirements"></a>Wymagania

**Przestrzeń nazw:** System. Web. kompilacja

**Zestaw:** System. Web (w System.Web.dll)

**.NET Framework wersje:** 3,5, 2,0
