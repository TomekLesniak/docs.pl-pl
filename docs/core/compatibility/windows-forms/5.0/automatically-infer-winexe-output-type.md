---
title: 'Zmiana podziału: wartość OutputType ustawiona na WinExe dla aplikacji WPF i WinForms'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, gdzie wartość OutputType jest automatycznie ustawiana na WinExe dla aplikacji Windows Forms.
ms.date: 09/18/2020
ms.openlocfilehash: 072c5b11c8304eb540e176ce9747930789f28505
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761684"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>OutputType ustawiony na WinExe dla aplikacji WPF i WinForms

`OutputType` jest automatycznie ustawiany na `WinExe` dla Windows Presentation Foundation (WPF) i Windows Forms aplikacji. Gdy `OutputType` jest ustawiona na `WinExe` , okno konsoli nie jest otwierane, gdy aplikacja jest wykonywana.

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET jest używana wartość określona dla `OutputType` pliku projektu. Na przykład:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Począwszy od platformy .NET 5,0, `OutputType` jest automatycznie ustawiany na `WinExe` dla aplikacji WPF i Windows Forms. Na przykład:

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a>Przyczyna zmiany

Zakłada się, że większość użytkowników nie chce, aby okno konsoli było otwierane podczas wykonywania aplikacji WPF lub Windows Forms. Ponadto, gdy [te typy aplikacji używają zestawu .NET SDK](sdk-and-target-framework-change.md) zamiast zestawu Windows Desktop SDK, zostanie ustawiona prawidłowa wartość domyślna. Dodatkowo, gdy zostanie dodana obsługa dla urządzeń z systemami iOS i Android, będzie ona łatwiejsza dla wielu platform, jeśli wszystkie używają tego samego typu danych wyjściowych.

## <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0

## <a name="recommended-action"></a>Zalecana akcja

W Twojej części nie jest wymagana żadna akcja. Jeśli jednak chcesz przywrócić stare zachowanie, ustaw `DisableWinExeOutputInference` Właściwość na `true` w pliku projektu.

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
