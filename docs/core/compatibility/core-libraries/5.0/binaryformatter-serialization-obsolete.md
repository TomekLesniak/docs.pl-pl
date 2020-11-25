---
title: 'Istotna zmiana: metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w podstawowych bibliotekach .NET, w których metody serializacji i deserializacji w BinaryFormatter, programie formatującego i IFormatter są przestarzałe.
ms.date: 11/01/2020
ms.openlocfilehash: 5807a7d4e6beab26b9848b803922396dd893075b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761527"
---
# <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a><span data-ttu-id="bf3f9-103">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bf3f9-103">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>

<span data-ttu-id="bf3f9-104">`Serialize` i `Deserialize` metody w <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> , <xref:System.Runtime.Serialization.Formatter> , i <xref:System.Runtime.Serialization.IFormatter> są obecnie przestarzałe jako ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-104">`Serialize` and `Deserialize` methods on <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter>, and <xref:System.Runtime.Serialization.IFormatter> are now obsolete as warning.</span></span> <span data-ttu-id="bf3f9-105">Ponadto <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Serializacja jest zabroniona domyślnie dla aplikacji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-105">Additionally, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is prohibited by default for ASP.NET apps.</span></span>

## <a name="change-description"></a><span data-ttu-id="bf3f9-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="bf3f9-106">Change description</span></span>

<span data-ttu-id="bf3f9-107">Ze względu na [luki w zabezpieczeniach](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) w programie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> następujące metody są obecnie przestarzałe i generują ostrzeżenie w czasie kompilacji o identyfikatorze `SYSLIB0011` .</span><span class="sxs-lookup"><span data-stu-id="bf3f9-107">Due to [security vulnerabilities](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following methods are now obsolete and produce a compile-time warning with ID `SYSLIB0011`.</span></span> <span data-ttu-id="bf3f9-108">Ponadto w ASP.NET Core 5,0 i nowszych aplikacje będą <xref:System.NotSupportedException> zgłaszać, chyba że aplikacja sieci Web nie ma ponownie włączonej <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-108">Additionally, in ASP.NET Core 5.0 and later apps, they will throw a <xref:System.NotSupportedException>, unless the web app has re-enabled <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> functionality.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

<span data-ttu-id="bf3f9-109">Następujące metody serializacji są również przestarzałe i generują ostrzeżenie `SYSLIB0011` , ale nie mają żadnych zmian w zachowaniu:</span><span class="sxs-lookup"><span data-stu-id="bf3f9-109">The following serialization methods are also obsolete and produce warning `SYSLIB0011`, but have no behavioral changes:</span></span>

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="version-introduced"></a><span data-ttu-id="bf3f9-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="bf3f9-110">Version introduced</span></span>

<span data-ttu-id="bf3f9-111">5,0</span><span class="sxs-lookup"><span data-stu-id="bf3f9-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="bf3f9-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="bf3f9-112">Reason for change</span></span>

<span data-ttu-id="bf3f9-113">Te metody są oznaczone jako przestarzałe w ramach wysiłku w celu wyróżnienia użycia <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> w ekosystemie platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-113">These methods are marked obsolete as part of an effort to wind down usage of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> within the .NET ecosystem.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="bf3f9-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="bf3f9-114">Recommended action</span></span>

- <span data-ttu-id="bf3f9-115">Przestań używać <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> w kodzie.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-115">Stop using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in your code.</span></span> <span data-ttu-id="bf3f9-116">Zamiast tego należy rozważyć użycie <xref:System.Text.Json.JsonSerializer> lub <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="bf3f9-116">Instead, consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="bf3f9-117">Aby uzyskać więcej informacji, zobacz [Przewodnik po zabezpieczeniach BinaryFormatter](../../../../standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="bf3f9-117">For more information, see [BinaryFormatter security guide](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

- <span data-ttu-id="bf3f9-118">Można tymczasowo pominąć ostrzeżenie w <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> czasie kompilacji, czyli `SYSLIB0011` .</span><span class="sxs-lookup"><span data-stu-id="bf3f9-118">You can temporarily suppress the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> compile-time warning, which is `SYSLIB0011`.</span></span> <span data-ttu-id="bf3f9-119">Zalecamy gruntowną ocenę kodu przed wybraniem tej opcji.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-119">We recommend that you thoroughly assess your code for risks before choosing this option.</span></span> <span data-ttu-id="bf3f9-120">Najprostszym sposobem, aby pominąć ostrzeżenia, jest obcinanie poszczególnych lokacji wywołań do `#pragma` dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-120">The easiest way to suppress the warnings is to surround the individual call site with `#pragma` directives.</span></span>

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  <span data-ttu-id="bf3f9-121">Możesz również pominąć ostrzeżenie w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-121">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  <span data-ttu-id="bf3f9-122">W przypadku pominięcia ostrzeżenia w pliku projektu ostrzeżenie zostanie pominięte dla wszystkich plików kodu w projekcie.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-122">If you suppress the warning in the project file, the warning is suppressed for all code files in the project.</span></span> <span data-ttu-id="bf3f9-123">Pomijanie `SYSLIB0011` nie pomija ostrzeżeń spowodowanych przez użycie innych przestarzałych interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-123">Suppressing `SYSLIB0011` does not suppress warnings caused by using other obsolete APIs.</span></span>

- <span data-ttu-id="bf3f9-124">Aby nadal korzystać <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> z aplikacji ASP.NET, możesz włączyć ją ponownie w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-124">To continue using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in ASP.NET apps, you can re-enable it in the project file.</span></span> <span data-ttu-id="bf3f9-125">Jednak zdecydowanie nie jest to zalecane.</span><span class="sxs-lookup"><span data-stu-id="bf3f9-125">However, it's strongly recommended not to do this.</span></span> <span data-ttu-id="bf3f9-126">Aby uzyskać więcej informacji, zobacz [Przewodnik po zabezpieczeniach BinaryFormatter](../../../../standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="bf3f9-126">For more information, see [BinaryFormatter security guide](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

<span data-ttu-id="bf3f9-127">Aby uzyskać więcej informacji na temat zalecanych akcji, zobacz [Rozwiązywanie problemów z BinaryFormatter obsoletion i wyłączanie](https://aka.ms/binaryformatter).</span><span class="sxs-lookup"><span data-stu-id="bf3f9-127">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="bf3f9-128">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="bf3f9-128">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET Core

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
