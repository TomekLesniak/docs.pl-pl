---
ms.openlocfilehash: 8693c1fdef5fa194b16127d4f1dd87e23ad68f2d
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438050"
---
### <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a><span data-ttu-id="2c40d-101">Rzutowanie OTOKi z `InterfaceIsIInspectable` interfejsem zgłasza PlatformNotSupportedException</span><span class="sxs-lookup"><span data-stu-id="2c40d-101">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>

<span data-ttu-id="2c40d-102">Rzutowanie otoki (OTOKa) środowiska uruchomieniowego na interfejs oznaczony jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> teraz zgłasza <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="2c40d-102">Casting a runtime callable wrapper (RCW) to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> now throws a <xref:System.PlatformNotSupportedException>.</span></span> <span data-ttu-id="2c40d-103">Ta zmiana jest zgodna z [usunięciem obsługi WinRT z platformy .NET](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span><span class="sxs-lookup"><span data-stu-id="2c40d-103">This change is a follow up to the [removal of WinRT support from .NET](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2c40d-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="2c40d-104">Version introduced</span></span>

<span data-ttu-id="2c40d-105">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="2c40d-105">5.0 RC2</span></span>

#### <a name="change-description"></a><span data-ttu-id="2c40d-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="2c40d-106">Change description</span></span>

<span data-ttu-id="2c40d-107">W wersjach .NET wcześniejszych niż .NET 5,0 Preview 6, Rzutowanie OTOKi z interfejsem oznaczonym jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="2c40d-107">In .NET versions prior to .NET 5.0 preview 6, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> works as expected.</span></span> <span data-ttu-id="2c40d-108">W przypadku wersji zapoznawczej programu .NET 5,0 w wersji zapoznawczej 6-8 i RC1 można pomyślnie rzutować otokę RCW na <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interfejs.</span><span class="sxs-lookup"><span data-stu-id="2c40d-108">In .NET 5.0 previews 6-8 and RC1, you can successfully cast an RCW to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface.</span></span> <span data-ttu-id="2c40d-109">Jednak użytkownik może uzyskać naruszenia zasad dostępu podczas wykonywania metod w interfejsie, ponieważ podstawowa pomoc techniczna w środowisku uruchomieniowym [została usunięta w programie .net 5,0 w wersji zapoznawczej 6](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span><span class="sxs-lookup"><span data-stu-id="2c40d-109">However, you might get access violations when you execute methods on the interface, because the underlying support in the runtime [was removed in .NET 5.0 preview 6](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span>

<span data-ttu-id="2c40d-110">W programie .NET 5,0 RC2 i nowszych wersjach, Rzutowanie OTOKi na interfejs oznaczony jako throw <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> a <xref:System.PlatformNotSupportedException> w czasie rzutowania.</span><span class="sxs-lookup"><span data-stu-id="2c40d-110">In .NET 5.0 RC2 and later versions, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> throws a <xref:System.PlatformNotSupportedException> at cast time.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2c40d-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="2c40d-111">Reason for change</span></span>

<span data-ttu-id="2c40d-112">Pomoc techniczna <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> została [usunięta w poprzedniej wersji zapoznawczej programu .NET 5,0](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span><span class="sxs-lookup"><span data-stu-id="2c40d-112">The support for <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> was [removed in a previous .NET 5.0 preview](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span> <span data-ttu-id="2c40d-113">Jednak rzutowanie na <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interfejs było przypadkowo przeszukiwane.</span><span class="sxs-lookup"><span data-stu-id="2c40d-113">However, casting to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface was accidentally overlooked.</span></span> <span data-ttu-id="2c40d-114">Ponieważ podstawowa pomoc techniczna w środowisku uruchomieniowym już nie istnieje, wyrzucanie <xref:System.PlatformNotSupportedException> ścieżki umożliwia bezpieczne niepowodzenie.</span><span class="sxs-lookup"><span data-stu-id="2c40d-114">Since the underlying support in the runtime no longer exists, throwing a <xref:System.PlatformNotSupportedException> enables a graceful failure path.</span></span> <span data-ttu-id="2c40d-115">Zgłaszanie wyjątku sprawia również, że ta funkcja nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="2c40d-115">Throwing an exception also makes it more discoverable that this feature is no longer supported.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2c40d-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="2c40d-116">Recommended action</span></span>

- <span data-ttu-id="2c40d-117">Jeśli możesz zdefiniować interfejs w pliku metadanych środowiska uruchomieniowego systemu Windows (WinMD), zamiast tego użyj narzędzia C#/WinRT.</span><span class="sxs-lookup"><span data-stu-id="2c40d-117">If you can define the interface in a Windows runtime metadata (WinMD) file, use the C#/WinRT tool instead.</span></span>

- <span data-ttu-id="2c40d-118">W przeciwnym razie Oznacz interfejs jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> zamiast <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> i Dodaj trzy fikcyjne wpisy na początku interfejsu dla <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> metod.</span><span class="sxs-lookup"><span data-stu-id="2c40d-118">Otherwise, mark the interface as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> instead of <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, and add three dummy entries to the start of the interface for the <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> methods.</span></span> <span data-ttu-id="2c40d-119">Poniższy fragment kodu przedstawia przykład.</span><span class="sxs-lookup"><span data-stu-id="2c40d-119">The following code snippet shows an example.</span></span>

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

#### <a name="category"></a><span data-ttu-id="2c40d-120">Kategoria</span><span class="sxs-lookup"><span data-stu-id="2c40d-120">Category</span></span>

<span data-ttu-id="2c40d-121">Interop</span><span class="sxs-lookup"><span data-stu-id="2c40d-121">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2c40d-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2c40d-122">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

-->
