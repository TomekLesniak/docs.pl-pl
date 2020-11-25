---
title: 'Nieprzerwana zmiana: Wbudowana obsługa środowiska WinRT jest usuwana z platformy .NET'
description: Dowiedz się więcej o zmianie nieprzerwaności międzyoperacyjnego w programie .NET 5,0, gdzie Wbudowana obsługa środowiska WinRT została usunięta z platformy .NET.
ms.date: 10/13/2020
ms.openlocfilehash: 61d8e26d06c232a7bfa1891a2159f5232f747b8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761552"
---
# <a name="built-in-support-for-winrt-is-removed-from-net"></a>Wbudowana obsługa środowiska WinRT jest usuwana z platformy .NET

Wbudowana obsługa użycia interfejsów API [środowiska wykonawczego systemu Windows](/uwp/winrt-cref/winrt-type-system) w programie .NET jest usuwana.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

Wcześniej CoreCLR może zużywać [pliki metadanych systemu Windows (WinMD)](/uwp/winrt-cref/winmd-files) do aktywnych i korzystać z typów WinRT. Począwszy od platformy .NET 5,0, CoreCLR nie może już bezpośrednio korzystać z plików WinMD.

Jeśli próbujesz odwołać się do nieobsługiwanego zestawu, uzyskasz <xref:System.IO.FileNotFoundException> . W przypadku aktywowania klasy WinRT uzyskasz <xref:System.PlatformNotSupportedException> .

Ta nieprzerwana zmiana została wprowadzona z następujących powodów:

- Dlatego WinRT można opracowywać i ulepszyć niezależnie od środowiska uruchomieniowego .NET.
- Dla symetrii z systemami międzyoperacyjnymi udostępnianymi dla innych systemów operacyjnych, takich jak iOS i Android.
- W celu skorzystania z innych funkcji platformy .NET, takich jak funkcje języka C#, konsolidacja w języku pośrednim (IL) i kompilacja przed czasem (AOT).
- Aby uprościć bazę kodu środowiska uruchomieniowego platformy .NET.

## <a name="recommended-action"></a>Zalecana akcja

- Usuń odwołania do [pakietu Microsoft. Windows. Sdk. kontrakts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).  Zamiast tego należy określić wersję interfejsów API systemu Windows, do których chcesz uzyskać dostęp za pośrednictwem `TargetFramework` właściwości projektu.  Na przykład:

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- Za pomocą łańcucha narzędzi [/WinRT języka C#](/windows/uwp/csharp-winrt/) można generować lub dostosowywać interfejsy API i typy środowiska WinRT dla programu .NET 5,0 i nowszych wersji.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

### Category

Interop

-->
