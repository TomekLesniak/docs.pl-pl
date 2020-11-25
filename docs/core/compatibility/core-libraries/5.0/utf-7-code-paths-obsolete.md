---
title: 'Istotna zmiana: ścieżki kodu UTF-7 są przestarzałe'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których konstruktory UTF7 i UTF7Encoding są przestarzałe.
ms.date: 11/01/2020
ms.openlocfilehash: d58305f59a30cdf31a525c3789bd6497201c50ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761403"
---
# <a name="utf-7-code-paths-are-obsolete"></a><span data-ttu-id="58390-103">Ścieżki kodu UTF-7 są przestarzałe</span><span class="sxs-lookup"><span data-stu-id="58390-103">UTF-7 code paths are obsolete</span></span>

<span data-ttu-id="58390-104">Kodowanie UTF-7 nie jest już używane między aplikacjami, a wiele specyfikacji już [zabroni jego użycia](https://security.stackexchange.com/a/68609/3573) w wymianie.</span><span class="sxs-lookup"><span data-stu-id="58390-104">The UTF-7 encoding is no longer in wide use among applications, and many specs now [forbid its use](https://security.stackexchange.com/a/68609/3573) in interchange.</span></span> <span data-ttu-id="58390-105">Jest to również sporadycznie [używane jako wektor ataku](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) w aplikacjach, które nie przewidziano do napotkania danych zakodowanych w formacie UTF-7.</span><span class="sxs-lookup"><span data-stu-id="58390-105">It's also occasionally [used as an attack vector](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) in applications that don't anticipate encountering UTF-7-encoded data.</span></span> <span data-ttu-id="58390-106">Firma Microsoft ostrzega przed użyciem, <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> ponieważ nie zapewnia wykrywania błędów.</span><span class="sxs-lookup"><span data-stu-id="58390-106">Microsoft warns against use of <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> because it doesn't provide error detection.</span></span>

<span data-ttu-id="58390-107">W związku z tym <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> Właściwość i <xref:System.Text.UTF7Encoding.%23ctor%2A> konstruktory są obecnie przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="58390-107">Consequently, the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property and <xref:System.Text.UTF7Encoding.%23ctor%2A> constructors are now obsolete.</span></span> <span data-ttu-id="58390-108">Ponadto <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> nie można już określić `UTF-7` .</span><span class="sxs-lookup"><span data-stu-id="58390-108">Additionally, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> and <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> no longer allow you to specify `UTF-7`.</span></span>

## <a name="change-description"></a><span data-ttu-id="58390-109">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="58390-109">Change description</span></span>

<span data-ttu-id="58390-110">Wcześniej można było utworzyć wystąpienie kodowania UTF-7 za pomocą <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="58390-110">Previously, you could create an instance of the UTF-7 encoding by using the <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> APIs.</span></span> <span data-ttu-id="58390-111">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="58390-111">For example:</span></span>

```csharp
Encoding enc1 = Encoding.GetEncoding("utf-7"); // By name.
Encoding enc2 = Encoding.GetEncoding(65000); // By code page.
```

<span data-ttu-id="58390-112">Ponadto wystąpienie, które reprezentuje kodowanie UTF-7, zostało wyliczone przez <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> metodę, która wylicza wszystkie <xref:System.Text.Encoding> wystąpienia zarejestrowane w systemie.</span><span class="sxs-lookup"><span data-stu-id="58390-112">Additionally, an instance that represents the UTF-7 encoding was enumerated by the <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> method, which enumerates all the <xref:System.Text.Encoding> instances registered on the system.</span></span>

<span data-ttu-id="58390-113">Począwszy od platformy .NET 5,0, <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> Właściwość i <xref:System.Text.UTF7Encoding.%23ctor%2A> konstruktory są przestarzałe i generują ostrzeżenia `SYSLIB0001` (lub w wersjach zapoznawczych `MSLIB0001` ).</span><span class="sxs-lookup"><span data-stu-id="58390-113">Starting in .NET 5.0, the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property and <xref:System.Text.UTF7Encoding.%23ctor%2A> constructors are obsolete and produce warning `SYSLIB0001` (or `MSLIB0001` in preview versions).</span></span> <span data-ttu-id="58390-114">Aby jednak zmniejszyć liczbę ostrzeżeń odbieranych przez wywołujących podczas korzystania z <xref:System.Text.UTF7Encoding> klasy, <xref:System.Text.UTF7Encoding> sam typ nie jest oznaczony jako przestarzały.</span><span class="sxs-lookup"><span data-stu-id="58390-114">However, to reduce the number of warnings that callers receive when using the <xref:System.Text.UTF7Encoding> class, the <xref:System.Text.UTF7Encoding> type itself is not marked obsolete.</span></span>

```csharp
// The next line generates warning SYSLIB0001.
UTF7Encoding enc = new UTF7Encoding();
// The next line does not generate a warning.
byte[] bytes = enc.GetBytes("Hello world!");
```

<span data-ttu-id="58390-115">Ponadto <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> metody traktują nazwę kodowania `utf-7` i stronę kodową `65000` jako `unknown` .</span><span class="sxs-lookup"><span data-stu-id="58390-115">Additionally, the <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> methods treat the encoding name `utf-7` and the code page `65000` as `unknown`.</span></span> <span data-ttu-id="58390-116">Traktując kodowanie jako `unknown` powodujące metodę, aby zgłosić <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="58390-116">Treating the encoding as `unknown` causes the method to throw an <xref:System.ArgumentException>.</span></span>

```csharp
// Throws ArgumentException, same as calling Encoding.GetEncoding("unknown").
Encoding enc = Encoding.GetEncoding("utf-7");
```

<span data-ttu-id="58390-117">Na koniec <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> Metoda nie zawiera kodowania UTF-7 w <xref:System.Text.EncodingInfo> zwracanej tablicy.</span><span class="sxs-lookup"><span data-stu-id="58390-117">Finally, the <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> method doesn't include the UTF-7 encoding in the <xref:System.Text.EncodingInfo> array that it returns.</span></span> <span data-ttu-id="58390-118">Kodowanie jest wykluczone, ponieważ nie można utworzyć jego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="58390-118">The encoding is excluded because it cannot be instantiated.</span></span>

```csharp
foreach (EncodingInfo encInfo in Encoding.GetEncodings())
{
    // The next line would throw if GetEncodings included UTF-7.
    Encoding enc = Encoding.GetEncoding(encInfo.Name);
}
```

## <a name="reason-for-change"></a><span data-ttu-id="58390-119">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="58390-119">Reason for change</span></span>

<span data-ttu-id="58390-120">Wiele aplikacji wywołuje `Encoding.GetEncoding("encoding-name")` wartość nazwy kodowania, która jest dostarczana przez niezaufane źródło.</span><span class="sxs-lookup"><span data-stu-id="58390-120">Many applications call `Encoding.GetEncoding("encoding-name")` with an encoding name value that's provided by an untrusted source.</span></span> <span data-ttu-id="58390-121">Na przykład klient sieci Web lub serwer może pobrać `charset` część `Content-Type` nagłówka i przekazać wartość bezpośrednio do programu `Encoding.GetEncoding` bez sprawdzania poprawności.</span><span class="sxs-lookup"><span data-stu-id="58390-121">For example, a web client or server might take the `charset` portion of the `Content-Type` header and pass the value directly to `Encoding.GetEncoding` without validating it.</span></span> <span data-ttu-id="58390-122">Może to umożliwić określenie złośliwego punktu końcowego `Content-Type: ...; charset=utf-7` , co może spowodować niezachowanie aplikacji odbiorczej.</span><span class="sxs-lookup"><span data-stu-id="58390-122">This could allow a malicious endpoint to specify `Content-Type: ...; charset=utf-7`, which could cause the receiving application to misbehave.</span></span>

<span data-ttu-id="58390-123">Ponadto wyłączenie ścieżek kodu UTF-7 pozwala zoptymalizować kompilatory, takie jak te używane przez Blazor, aby usunąć te ścieżki kodu w całości z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="58390-123">Additionally, disabling UTF-7 code paths allows optimizing compilers, such as those used by Blazor, to remove these code paths entirely from the resulting application.</span></span> <span data-ttu-id="58390-124">W związku z tym skompilowane aplikacje działają wydajniej i zajmuje mniej miejsca na dysku.</span><span class="sxs-lookup"><span data-stu-id="58390-124">As a result, the compiled applications run more efficiently and take less disk space.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="58390-125">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="58390-125">Version introduced</span></span>

<span data-ttu-id="58390-126">5,0</span><span class="sxs-lookup"><span data-stu-id="58390-126">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="58390-127">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="58390-127">Recommended action</span></span>

<span data-ttu-id="58390-128">W większości przypadków nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="58390-128">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="58390-129">Jednak w przypadku aplikacji, które wcześniej aktywowali ścieżki kodu związane z kodowaniem UTF-7, należy wziąć pod uwagę poniższe wskazówki.</span><span class="sxs-lookup"><span data-stu-id="58390-129">However, for apps that have previously activated UTF-7-related code paths, consider the guidance that follows.</span></span>

- <span data-ttu-id="58390-130">Jeśli aplikacja wywołuje <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> nieznane nazwy kodowania dostarczone przez niezaufane Źródło:</span><span class="sxs-lookup"><span data-stu-id="58390-130">If your app calls <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> with unknown encoding names provided by an untrusted source:</span></span>

  <span data-ttu-id="58390-131">Zamiast tego należy porównać nazwy kodowania z konfigurowalną listą dozwolonych.</span><span class="sxs-lookup"><span data-stu-id="58390-131">Instead, compare the encoding names against a configurable allow list.</span></span> <span data-ttu-id="58390-132">Lista dozwolonych konfigurowalnych powinna zawierać co najmniej wartość "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="58390-132">The configurable allow list should at minimum include the industry-standard "utf-8".</span></span> <span data-ttu-id="58390-133">W zależności od klientów i wymagań prawnych może być również konieczne zezwolenie na kodowanie specyficzne dla regionu, takie jak "GB18030".</span><span class="sxs-lookup"><span data-stu-id="58390-133">Depending on your clients and regulatory requirements, you may also need to allow region-specific encodings, such as "GB18030".</span></span>

  <span data-ttu-id="58390-134">Jeśli lista dozwolonych nie zostanie wdrożona, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> program zwróci wszystkie <xref:System.Text.Encoding> wbudowane w system lub zarejestrowane za pośrednictwem niestandardowej <xref:System.Text.EncodingProvider> .</span><span class="sxs-lookup"><span data-stu-id="58390-134">If you don't implement an allow list, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> will return any <xref:System.Text.Encoding> that's built into the system or that's registered via a custom <xref:System.Text.EncodingProvider>.</span></span> <span data-ttu-id="58390-135">Przeprowadź inspekcję wymagań usługi, aby sprawdzić, czy jest to odpowiednie zachowanie.</span><span class="sxs-lookup"><span data-stu-id="58390-135">Audit your service's requirements to validate that this is the desired behavior.</span></span> <span data-ttu-id="58390-136">Kodowanie UTF-7 nadal jest domyślnie wyłączone, chyba że aplikacja ponownie włączy przełącznik zgodności wymieniony w dalszej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="58390-136">UTF-7 continues to be disabled by default unless your application re-enables the compatibility switch mentioned later in this article.</span></span>

- <span data-ttu-id="58390-137">W przypadku korzystania z programu <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> lub <xref:System.Text.UTF7Encoding> w ramach własnego protokołu lub formatu pliku:</span><span class="sxs-lookup"><span data-stu-id="58390-137">If you're using <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding> within your own protocol or file format:</span></span>

  <span data-ttu-id="58390-138">Przełącz się do korzystania z <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> lub <xref:System.Text.UTF8Encoding> .</span><span class="sxs-lookup"><span data-stu-id="58390-138">Switch to using <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> or <xref:System.Text.UTF8Encoding>.</span></span> <span data-ttu-id="58390-139">UTF-8 jest standardem branżowym i jest szeroko obsługiwany w różnych językach, systemach operacyjnych i w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="58390-139">UTF-8 is an industry standard and is widely supported across languages, operating systems, and runtimes.</span></span> <span data-ttu-id="58390-140">Użycie UTF-8 ułatwia przyszłą konserwację kodu i sprawia, że jest to bardziej obsługiwane w pozostałej części ekosystemu.</span><span class="sxs-lookup"><span data-stu-id="58390-140">Using UTF-8 eases future maintenance of your code and makes it more interoperable with the rest of the ecosystem.</span></span>

- <span data-ttu-id="58390-141">Jeśli porównujesz <xref:System.Text.Encoding> wystąpienie z <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="58390-141">If you're comparing an <xref:System.Text.Encoding> instance against <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span></span>

  <span data-ttu-id="58390-142">Zamiast tego należy rozważyć przeprowadzenie sprawdzenia względem dobrze znanej strony kodowej UTF-7, która jest `65000` .</span><span class="sxs-lookup"><span data-stu-id="58390-142">Instead, consider performing a check against the well-known UTF-7 code page, which is `65000`.</span></span> <span data-ttu-id="58390-143">Porównując względem strony kodowej, można uniknąć ostrzeżenia, a także obsłużyć niektóre przypadki brzegowe, na przykład jeśli ktoś wywołał `new UTF7Encoding()` lub podklasy typ.</span><span class="sxs-lookup"><span data-stu-id="58390-143">By comparing against the code page, you avoid the warning and also handle some edge cases, such as if somebody called `new UTF7Encoding()` or subclassed the type.</span></span>

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

- <span data-ttu-id="58390-144">Jeśli musisz użyć <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> lub <xref:System.Text.UTF7Encoding> :</span><span class="sxs-lookup"><span data-stu-id="58390-144">If you must use <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding>:</span></span>

  <span data-ttu-id="58390-145">Możesz pominąć `SYSLIB0001` ostrzeżenie w kodzie lub w pliku *. csproj* projektu.</span><span class="sxs-lookup"><span data-stu-id="58390-145">You can suppress the `SYSLIB0001` warning in code or within your project's *.csproj* file.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0001 // Disable the warning.
  Encoding enc = Encoding.UTF7;
  #pragma warning restore SYSLIB0001 // Re-enable the warning.
  ```

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > <span data-ttu-id="58390-146">Pomijanie `SYSLIB0001` powoduje wyłączenie tylko <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> <xref:System.Text.UTF7Encoding> ostrzeżeń i obsoletion.</span><span class="sxs-lookup"><span data-stu-id="58390-146">Suppressing `SYSLIB0001` only disables the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> and <xref:System.Text.UTF7Encoding> obsoletion warnings.</span></span> <span data-ttu-id="58390-147">Nie wyłącza żadnych innych ostrzeżeń ani nie zmienia zachowania interfejsów API, takich jak <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="58390-147">It doesn't disable any other warnings or change the behavior of APIs like <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="58390-148">Jeśli musisz obsługiwać `Encoding.GetEncoding("utf-7", ...)` :</span><span class="sxs-lookup"><span data-stu-id="58390-148">If you must support `Encoding.GetEncoding("utf-7", ...)`:</span></span>

  <span data-ttu-id="58390-149">Można ponownie włączyć obsługę tego programu za pośrednictwem przełącznika zgodności.</span><span class="sxs-lookup"><span data-stu-id="58390-149">You can re-enable support for this via a compatibility switch.</span></span> <span data-ttu-id="58390-150">Ten przełącznik zgodności można określić w pliku *. csproj* aplikacji lub w [pliku konfiguracji czasu wykonywania](../../../run-time-config/index.md), jak pokazano w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="58390-150">This compatibility switch can be specified in the application's *.csproj* file or in a [run-time configuration file](../../../run-time-config/index.md), as shown in the following examples.</span></span>

  <span data-ttu-id="58390-151">W pliku *. csproj* aplikacji:</span><span class="sxs-lookup"><span data-stu-id="58390-151">In the application's *.csproj* file:</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- Re-enable support for UTF-7 -->
     <EnableUnsafeUTF7Encoding>true</EnableUnsafeUTF7Encoding>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="58390-152">W *runtimeconfig.template.jsaplikacji w* pliku:</span><span class="sxs-lookup"><span data-stu-id="58390-152">In the application's *runtimeconfig.template.json* file:</span></span>

  ```json
  {
    "configProperties": {
      "System.Text.Encoding.EnableUnsafeUTF7Encoding": true
    }
  }
  ```

  > [!TIP]
  > <span data-ttu-id="58390-153">W przypadku ponownego włączenia obsługi UTF-7 należy przeprowadzić przegląd zabezpieczeń kodu, który wywołuje <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="58390-153">If you re-enable support for UTF-7, you should perform a security review of code that calls <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="58390-154">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="58390-154">Affected APIs</span></span>

- <xref:System.Text.Encoding.UTF7?displayProperty=fullName>
- <xref:System.Text.UTF7Encoding.%23ctor>
- <xref:System.Text.UTF7Encoding.%23ctor(System.Boolean)>
- <xref:System.Text.Encoding.GetEncoding(System.Int32)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncodings?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `System.Text.Encoding.UTF7`
- `System.Text.UTF7Encoding.#ctor`
- `System.Text.UTF7Encoding.#ctor(System.Boolean)`
- `System.Text.Encoding.GetEncoding(System.Int32)`
- `System.Text.Encoding.GetEncoding(System.String)`
- `System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncodings`

-->
