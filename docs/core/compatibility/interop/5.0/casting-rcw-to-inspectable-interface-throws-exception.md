---
title: 'Istotna zmiana: Rzutowanie OTOKi do `InterfaceIsIInspectable` zgłaszania wyjątku'
description: Dowiedz się więcej o zmianie nieprzerwaności międzyoperacyjności w programie .NET 5,0, gdzie rzutowanie OTOKi na `InterfaceIsIInspectable` interfejs zgłasza PlatformNotSupportedException.
ms.date: 09/13/2020
ms.openlocfilehash: 7c0f37057aebcc41d0c00d949b921ec3a4bdf012
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761548"
---
# <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a><span data-ttu-id="cdfea-103">Rzutowanie OTOKi z `InterfaceIsIInspectable` interfejsem zgłasza PlatformNotSupportedException</span><span class="sxs-lookup"><span data-stu-id="cdfea-103">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>

<span data-ttu-id="cdfea-104">Rzutowanie otoki (OTOKa) środowiska uruchomieniowego na interfejs oznaczony jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> teraz zgłasza <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="cdfea-104">Casting a runtime callable wrapper (RCW) to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> now throws a <xref:System.PlatformNotSupportedException>.</span></span> <span data-ttu-id="cdfea-105">Ta zmiana jest zgodna z [usunięciem obsługi WinRT z platformy .NET](built-in-support-for-winrt-removed.md).</span><span class="sxs-lookup"><span data-stu-id="cdfea-105">This change is a follow up to the [removal of WinRT support from .NET](built-in-support-for-winrt-removed.md).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="cdfea-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="cdfea-106">Version introduced</span></span>

<span data-ttu-id="cdfea-107">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="cdfea-107">5.0 RC2</span></span>

## <a name="change-description"></a><span data-ttu-id="cdfea-108">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="cdfea-108">Change description</span></span>

<span data-ttu-id="cdfea-109">W wersjach .NET wcześniejszych niż .NET 5,0 Preview 6, Rzutowanie OTOKi z interfejsem oznaczonym jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="cdfea-109">In .NET versions prior to .NET 5.0 preview 6, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> works as expected.</span></span> <span data-ttu-id="cdfea-110">W przypadku wersji zapoznawczej programu .NET 5,0 w wersji zapoznawczej 6-8 i RC1 można pomyślnie rzutować otokę RCW na <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interfejs.</span><span class="sxs-lookup"><span data-stu-id="cdfea-110">In .NET 5.0 previews 6-8 and RC1, you can successfully cast an RCW to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface.</span></span> <span data-ttu-id="cdfea-111">Jednak użytkownik może uzyskać naruszenia zasad dostępu podczas wykonywania metod w interfejsie, ponieważ podstawowa pomoc techniczna w środowisku uruchomieniowym [została usunięta w programie .net 5,0 w wersji zapoznawczej 6](built-in-support-for-winrt-removed.md).</span><span class="sxs-lookup"><span data-stu-id="cdfea-111">However, you might get access violations when you execute methods on the interface, because the underlying support in the runtime [was removed in .NET 5.0 preview 6](built-in-support-for-winrt-removed.md).</span></span>

<span data-ttu-id="cdfea-112">W programie .NET 5,0 RC2 i nowszych wersjach, Rzutowanie OTOKi na interfejs oznaczony jako throw <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> a <xref:System.PlatformNotSupportedException> w czasie rzutowania.</span><span class="sxs-lookup"><span data-stu-id="cdfea-112">In .NET 5.0 RC2 and later versions, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> throws a <xref:System.PlatformNotSupportedException> at cast time.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="cdfea-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="cdfea-113">Reason for change</span></span>

<span data-ttu-id="cdfea-114">Pomoc techniczna <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> została [usunięta w poprzedniej wersji zapoznawczej programu .NET 5,0](built-in-support-for-winrt-removed.md).</span><span class="sxs-lookup"><span data-stu-id="cdfea-114">The support for <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> was [removed in a previous .NET 5.0 preview](built-in-support-for-winrt-removed.md).</span></span> <span data-ttu-id="cdfea-115">Jednak rzutowanie na <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interfejs było przypadkowo przeszukiwane.</span><span class="sxs-lookup"><span data-stu-id="cdfea-115">However, casting to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface was accidentally overlooked.</span></span> <span data-ttu-id="cdfea-116">Ponieważ podstawowa pomoc techniczna w środowisku uruchomieniowym już nie istnieje, wyrzucanie <xref:System.PlatformNotSupportedException> ścieżki umożliwia bezpieczne niepowodzenie.</span><span class="sxs-lookup"><span data-stu-id="cdfea-116">Since the underlying support in the runtime no longer exists, throwing a <xref:System.PlatformNotSupportedException> enables a graceful failure path.</span></span> <span data-ttu-id="cdfea-117">Zgłaszanie wyjątku sprawia również, że ta funkcja nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="cdfea-117">Throwing an exception also makes it more discoverable that this feature is no longer supported.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="cdfea-118">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="cdfea-118">Recommended action</span></span>

- <span data-ttu-id="cdfea-119">Jeśli możesz zdefiniować interfejs w pliku metadanych środowiska uruchomieniowego systemu Windows (WinMD), zamiast tego użyj narzędzia C#/WinRT.</span><span class="sxs-lookup"><span data-stu-id="cdfea-119">If you can define the interface in a Windows runtime metadata (WinMD) file, use the C#/WinRT tool instead.</span></span>

- <span data-ttu-id="cdfea-120">W przeciwnym razie Oznacz interfejs jako <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> zamiast <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> i Dodaj trzy fikcyjne wpisy na początku interfejsu dla <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> metod.</span><span class="sxs-lookup"><span data-stu-id="cdfea-120">Otherwise, mark the interface as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> instead of <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, and add three dummy entries to the start of the interface for the <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> methods.</span></span> <span data-ttu-id="cdfea-121">Poniższy fragment kodu przedstawia przykład.</span><span class="sxs-lookup"><span data-stu-id="cdfea-121">The following code snippet shows an example.</span></span>

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

## <a name="affected-apis"></a><span data-ttu-id="cdfea-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="cdfea-122">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

### Category

Interop

-->
