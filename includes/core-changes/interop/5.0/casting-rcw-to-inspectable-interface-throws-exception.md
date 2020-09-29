---
ms.openlocfilehash: 8693c1fdef5fa194b16127d4f1dd87e23ad68f2d
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438050"
---
### <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a>Rzutowanie OTOKi z `InterfaceIsIInspectable` interfejsem zgłasza PlatformNotSupportedException

Rzutowanie otoki (OTOKa) środowiska uruchomieniowego na interfejs oznaczony jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> teraz zgłasza <xref:System.PlatformNotSupportedException> . Ta zmiana jest zgodna z [usunięciem obsługi WinRT z platformy .NET](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC2

#### <a name="change-description"></a>Zmień opis

W wersjach .NET wcześniejszych niż .NET 5,0 Preview 6, Rzutowanie OTOKi z interfejsem oznaczonym jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> działa zgodnie z oczekiwaniami. W przypadku wersji zapoznawczej programu .NET 5,0 w wersji zapoznawczej 6-8 i RC1 można pomyślnie rzutować otokę RCW na <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interfejs. Jednak użytkownik może uzyskać naruszenia zasad dostępu podczas wykonywania metod w interfejsie, ponieważ podstawowa pomoc techniczna w środowisku uruchomieniowym [została usunięta w programie .net 5,0 w wersji zapoznawczej 6](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).

W programie .NET 5,0 RC2 i nowszych wersjach, Rzutowanie OTOKi na interfejs oznaczony jako throw <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> a <xref:System.PlatformNotSupportedException> w czasie rzutowania.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Pomoc techniczna <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> została [usunięta w poprzedniej wersji zapoznawczej programu .NET 5,0](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net). Jednak rzutowanie na <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interfejs było przypadkowo przeszukiwane. Ponieważ podstawowa pomoc techniczna w środowisku uruchomieniowym już nie istnieje, wyrzucanie <xref:System.PlatformNotSupportedException> ścieżki umożliwia bezpieczne niepowodzenie. Zgłaszanie wyjątku sprawia również, że ta funkcja nie jest już obsługiwana.

#### <a name="recommended-action"></a>Zalecana akcja

- Jeśli możesz zdefiniować interfejs w pliku metadanych środowiska uruchomieniowego systemu Windows (WinMD), zamiast tego użyj narzędzia C#/WinRT.

- W przeciwnym razie Oznacz interfejs jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> zamiast <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> i Dodaj trzy fikcyjne wpisy na początku interfejsu dla <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> metod. Poniższy fragment kodu przedstawia przykład.

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

#### <a name="category"></a>Kategoria

Interop

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

-->
