---
ms.openlocfilehash: 7cb146d19486618a4cee9976abe2220ea4b72790
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2020
ms.locfileid: "88203986"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a><span data-ttu-id="a12cc-101">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a12cc-101">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>

<span data-ttu-id="a12cc-102">`Serialize``Deserialize`metody i <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <xref:System.Runtime.Serialization.Formatter> <xref:System.Runtime.Serialization.IFormatter> są obecnie przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="a12cc-102">`Serialize` and `Deserialize` methods on <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter>, and <xref:System.Runtime.Serialization.IFormatter> are now obsolete.</span></span> <span data-ttu-id="a12cc-103">Ponadto <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Serializacja jest zabroniona domyślnie dla aplikacji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a12cc-103">Additionally, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is prohibited by default for ASP.NET apps.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a12cc-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a12cc-104">Change description</span></span>

<span data-ttu-id="a12cc-105">Ze względu na [luki w zabezpieczeniach](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) w programie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> następujące metody są obecnie przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="a12cc-105">Due to [security vulnerabilities](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following methods are now obsolete.</span></span> <span data-ttu-id="a12cc-106">Ponadto w ASP.NET Core 5,0 i nowszych aplikacje będą <xref:System.NotSupportedException> zgłaszać, chyba że aplikacja sieci Web nie ma ponownie włączonej <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="a12cc-106">Additionally, in ASP.NET Core 5.0 and later apps, they will throw a <xref:System.NotSupportedException>, unless the web app has re-enabled <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> functionality.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

<span data-ttu-id="a12cc-107">Te metody są oznaczone jako przestarzałe w ramach wysiłku w celu wyróżnienia użycia <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> w ekosystemie platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="a12cc-107">These methods are marked obsolete as part of an effort to wind down usage of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> within the .NET ecosystem.</span></span>

<span data-ttu-id="a12cc-108">Następujące metody serializacji są również przestarzałe, ale nie mają żadnych zmian w zachowaniu:</span><span class="sxs-lookup"><span data-stu-id="a12cc-108">The following serialization methods are also now obsolete, but have no behavioral changes:</span></span>

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a><span data-ttu-id="a12cc-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a12cc-109">Version introduced</span></span>

<span data-ttu-id="a12cc-110">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="a12cc-110">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a12cc-111">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a12cc-111">Recommended action</span></span>

- <span data-ttu-id="a12cc-112">Przestań używać <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> w kodzie.</span><span class="sxs-lookup"><span data-stu-id="a12cc-112">Stop using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in your code.</span></span> <span data-ttu-id="a12cc-113">Zamiast tego należy rozważyć użycie <xref:System.Text.Json.JsonSerializer> lub <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="a12cc-113">Instead, consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="a12cc-114">Aby uzyskać więcej informacji, zobacz [Przewodnik po zabezpieczeniach BinaryFormatter](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="a12cc-114">For more information, see [BinaryFormatter security guide](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span></span>

- <span data-ttu-id="a12cc-115">Można tymczasowo pominąć ostrzeżenie w <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> czasie kompilacji, czyli `SYSLIB0011` .</span><span class="sxs-lookup"><span data-stu-id="a12cc-115">You can temporarily suppress the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> compile-time warning, which is `SYSLIB0011`.</span></span> <span data-ttu-id="a12cc-116">Zalecamy gruntowną ocenę kodu przed wybraniem tej opcji.</span><span class="sxs-lookup"><span data-stu-id="a12cc-116">We recommend that you thoroughly assess your code for risks before choosing this option.</span></span> <span data-ttu-id="a12cc-117">Najprostszym sposobem, aby pominąć ostrzeżenia, jest obcinanie poszczególnych lokacji wywołań do `#pragma` dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="a12cc-117">The easiest way to suppress the warnings is to surround the individual call site with `#pragma` directives.</span></span>

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

  <span data-ttu-id="a12cc-118">Możesz również pominąć ostrzeżenie w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="a12cc-118">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  <span data-ttu-id="a12cc-119">W przypadku pominięcia ostrzeżenia w pliku projektu ostrzeżenie zostanie pominięte dla wszystkich plików kodu w projekcie.</span><span class="sxs-lookup"><span data-stu-id="a12cc-119">If you suppress the warning in the project file, the warning is suppressed for all code files in the project.</span></span> <span data-ttu-id="a12cc-120">Pomijanie SYSLIB0011 nie pomija ostrzeżeń spowodowanych przez użycie innych przestarzałych interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="a12cc-120">Suppressing SYSLIB0011 does not suppress warnings caused by using other obsolete APIs.</span></span>

- <span data-ttu-id="a12cc-121">Aby nadal korzystać <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> z aplikacji ASP.NET, możesz włączyć ją ponownie w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="a12cc-121">To continue using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in ASP.NET apps, you can re-enable it in the project file.</span></span> <span data-ttu-id="a12cc-122">Jednak zdecydowanie nie jest to zalecane.</span><span class="sxs-lookup"><span data-stu-id="a12cc-122">However, it's strongly recommended not to do this.</span></span> <span data-ttu-id="a12cc-123">Aby uzyskać więcej informacji, zobacz [Przewodnik po zabezpieczeniach BinaryFormatter](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="a12cc-123">For more information, see [BinaryFormatter security guide](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span></span>

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

<span data-ttu-id="a12cc-124">Aby uzyskać więcej informacji na temat zalecanych akcji, zobacz [Rozwiązywanie problemów z BinaryFormatter obsoletion i wyłączanie](https://aka.ms/binaryformatter).</span><span class="sxs-lookup"><span data-stu-id="a12cc-124">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

#### <a name="category"></a><span data-ttu-id="a12cc-125">Kategoria</span><span class="sxs-lookup"><span data-stu-id="a12cc-125">Category</span></span>

- <span data-ttu-id="a12cc-126">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="a12cc-126">Core .NET libraries</span></span>
- <span data-ttu-id="a12cc-127">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a12cc-127">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a12cc-128">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a12cc-128">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
