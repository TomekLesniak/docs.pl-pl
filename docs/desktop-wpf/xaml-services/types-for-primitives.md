---
title: Typy wbudowane dla wspólnych elementów podstawowych języka XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML language primitives [XAML Services]
- XAML [XAML Services], built-in types
- x:String [XAML Services]
- x:TimeSpan [XAML Services]
- x:Byte [XAML Services]
- x:Double [XAML Services]
- XAML [XAML Services], types
- x:Uri [XAML Services]
- XAML built-in types [XAML Services]
- x:Int64 [XAML Services]
- x:Single [XAML Services]
- x:Int32 [XAML Services]
ms.assetid: 11de2f08-5b95-4989-b5ec-5178eb968184
ms.openlocfilehash: ec0e2a29a191d5057ce66a5f3272d00e92b01bd7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540032"
---
# <a name="built-in-types-for-common-xaml-language-primitives"></a><span data-ttu-id="70615-102">Typy wbudowane dla wspólnych elementów podstawowych języka XAML</span><span class="sxs-lookup"><span data-stu-id="70615-102">Built-in types for common XAML language primitives</span></span>

<span data-ttu-id="70615-103">XAML 2009 wprowadza obsługę poziomu języka XAML dla kilku typów danych, które są często używane jako elementy pierwotne w środowisku uruchomieniowym języka wspólnego (CLR) i w innych językach programowania.</span><span class="sxs-lookup"><span data-stu-id="70615-103">XAML 2009 introduces XAML language-level support for several data types that are frequently used primitives in the common language runtime (CLR) and in other programming languages.</span></span> <span data-ttu-id="70615-104">Język XAML 2009 dodaje obsługę tych elementów podstawowych:,,,,,,,,, `x:Object` `x:Boolean` `x:Char` `x:String` `x:Decimal` `x:Single` `x:Double` `x:Int16` `x:Int32` `x:Int64` , `x:TimeSpan` , `x:Uri` ,, `x:Byte` i `x:Array`</span><span class="sxs-lookup"><span data-stu-id="70615-104">XAML 2009 adds support for these primitives: `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`, and `x:Array`</span></span>

## <a name="previous-techniques-for-language-primitives-in-xaml-markup"></a><span data-ttu-id="70615-105">Poprzednie techniki dla elementów podstawowych języka w znacznikach XAML</span><span class="sxs-lookup"><span data-stu-id="70615-105">Previous Techniques for Language Primitives in XAML Markup</span></span>

 <span data-ttu-id="70615-106">W języku XAML dla wcześniejszych wersji WPF można przywołać elementy podstawowe języka CLR, mapując zestaw i przestrzeń nazw, które zawierały klasę definicji pierwotnej CLR dla .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70615-106">In XAML for previous WPF versions, you could reference the CLR language primitives by mapping the assembly and namespace that contained a CLR primitive definition class for the .NET Framework.</span></span> <span data-ttu-id="70615-107">Większość z nich znajduje się w zestawie mscorlib i <xref:System> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="70615-107">Most of these are in the mscorlib assembly and <xref:System> namespace.</span></span> <span data-ttu-id="70615-108">Na przykład, aby użyć <xref:System.Int32> , można zadeklarować następujące mapowanie (z przykładowym użyciem):</span><span class="sxs-lookup"><span data-stu-id="70615-108">For example, to use <xref:System.Int32>, you could declare the following mapping (with an example usage shown thereafter):</span></span>

```xaml
<Application xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Application.Resources>
    <sys:Int32 x:Key="intMeaning">42</sys:Int32>
  </Application.Resources>
</Application>
```

## <a name="xaml-2009-language-primitives"></a><span data-ttu-id="70615-109">Elementy podstawowe języka XAML 2009</span><span class="sxs-lookup"><span data-stu-id="70615-109">XAML 2009 Language Primitives</span></span>

<span data-ttu-id="70615-110">Zgodnie z Konwencją, są wyświetlane elementy podstawowe języka XAML i wszystkich innych elementów języka XAML, łącznie z `x:` prefiksem.</span><span class="sxs-lookup"><span data-stu-id="70615-110">By convention, the language primitives for XAML and all other XAML language elements are shown, including the `x:` prefix.</span></span> <span data-ttu-id="70615-111">Jest to sposób, w jaki elementy języka XAML są zwykle używane w oznakowaniu rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="70615-111">This is how XAML language elements are typically used in real-world markup.</span></span> <span data-ttu-id="70615-112">Ta konwencja jest stosowana w dokumentacji koncepcyjnej języka XAML w WPF, a także w specyfikacji języka XAML.</span><span class="sxs-lookup"><span data-stu-id="70615-112">This convention is followed in the conceptual documentation for XAML in WPF and also in the XAML specification.</span></span>

### <a name="xobject"></a><span data-ttu-id="70615-113">x:Object</span><span class="sxs-lookup"><span data-stu-id="70615-113">x:Object</span></span>

<span data-ttu-id="70615-114">W przypadku środowiska CLR element `x:Object` podstawowy odpowiada <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="70615-114">For CLR backing, the `x:Object` primitive corresponds to <xref:System.Object>.</span></span>

<span data-ttu-id="70615-115">Ten element podstawowy nie jest zazwyczaj używany w znacznikach aplikacji, ale może być przydatny w niektórych scenariuszach, takich jak sprawdzanie możliwości przypisywania w systemie typów XAML.</span><span class="sxs-lookup"><span data-stu-id="70615-115">This primitive is not typically used in application markup, but might be useful for some scenarios such as checking assignability in a XAML type system.</span></span>

### <a name="xboolean"></a><span data-ttu-id="70615-116">x:Boolean</span><span class="sxs-lookup"><span data-stu-id="70615-116">x:Boolean</span></span>

<span data-ttu-id="70615-117">W przypadku środowiska CLR element `x:Boolean` podstawowy odpowiada <xref:System.Boolean> .</span><span class="sxs-lookup"><span data-stu-id="70615-117">For CLR backing, the `x:Boolean` primitive corresponds to <xref:System.Boolean>.</span></span>

<span data-ttu-id="70615-118">KOD XAML analizuje wartości `x:Boolean` jako nieuwzględniające wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="70615-118">XAML parses values for `x:Boolean` as case insensitive.</span></span> <span data-ttu-id="70615-119">Należy zauważyć, że `x:Bool` nie jest zaakceptowaną alternatywą.</span><span class="sxs-lookup"><span data-stu-id="70615-119">Note that `x:Bool` is not an accepted alternative.</span></span> <span data-ttu-id="70615-120">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.17 i 5.4.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-120">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.17 and 5.4.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xchar"></a><span data-ttu-id="70615-121">x:Char</span><span class="sxs-lookup"><span data-stu-id="70615-121">x:Char</span></span>

<span data-ttu-id="70615-122">W przypadku środowiska CLR element `x:Char` podstawowy odpowiada <xref:System.Char> .</span><span class="sxs-lookup"><span data-stu-id="70615-122">For CLR backing, the `x:Char` primitive corresponds to <xref:System.Char>.</span></span>

<span data-ttu-id="70615-123">Typy String i char mają interakcję z ogólnym kodowaniem pliku na poziomie XML.</span><span class="sxs-lookup"><span data-stu-id="70615-123">String and char types have interaction with the overall encoding of the file at the XML level.</span></span> <span data-ttu-id="70615-124">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.7 i 5.4.1](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-124">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.7 and 5.4.1](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xstring"></a><span data-ttu-id="70615-125">x:String</span><span class="sxs-lookup"><span data-stu-id="70615-125">x:String</span></span>

<span data-ttu-id="70615-126">W przypadku środowiska CLR element `x:String` podstawowy odpowiada <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="70615-126">For CLR backing, the `x:String` primitive corresponds to <xref:System.String>.</span></span>

<span data-ttu-id="70615-127">Typy String i char mają interakcję z ogólnym kodowaniem pliku na poziomie XML.</span><span class="sxs-lookup"><span data-stu-id="70615-127">String and char types have interaction with the overall encoding of the file at the XML level.</span></span> <span data-ttu-id="70615-128">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-128">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xdecimal"></a><span data-ttu-id="70615-129">x:Decimal</span><span class="sxs-lookup"><span data-stu-id="70615-129">x:Decimal</span></span>

<span data-ttu-id="70615-130">W przypadku środowiska CLR element `x:Decimal` podstawowy odpowiada <xref:System.Decimal> .</span><span class="sxs-lookup"><span data-stu-id="70615-130">For CLR backing, the `x:Decimal` primitive corresponds to <xref:System.Decimal>.</span></span>

<span data-ttu-id="70615-131">Analiza kodu XAML jest zaimplementowana w ramach `en-US` kultury.</span><span class="sxs-lookup"><span data-stu-id="70615-131">XAML parsing is inherently done under `en-US` culture.</span></span> <span data-ttu-id="70615-132">W obszarze `en-US` kultura prawidłowy separator składników dziesiętnych jest zawsze kropką ( `.` ) niezależnie od ustawień kultury środowiska programistycznego lub miejsca docelowego klienta, gdzie XAML jest ładowany w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="70615-132">Under `en-US` culture, the correct separator for the components of a decimal is always a period (`.`) regardless of culture settings of the development environment, or of the eventual client target where the XAML is loaded at run time.</span></span>

<span data-ttu-id="70615-133">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.14 i 5.4.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-133">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.14 and 5.4.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xsingle"></a><span data-ttu-id="70615-134">x:Single</span><span class="sxs-lookup"><span data-stu-id="70615-134">x:Single</span></span>

<span data-ttu-id="70615-135">W przypadku środowiska CLR element `x:Single` podstawowy odpowiada <xref:System.Single> .</span><span class="sxs-lookup"><span data-stu-id="70615-135">For CLR backing, the `x:Single` primitive corresponds to <xref:System.Single>.</span></span>

<span data-ttu-id="70615-136">Oprócz wartości liczbowych, składnia tekstu dla `x:Single` również zezwala na tokeny `Infinity` , `-Infinity` i `NaN` .</span><span class="sxs-lookup"><span data-stu-id="70615-136">In addition to the numeric values, text syntax for `x:Single` also permits the tokens `Infinity`, `-Infinity`, and `NaN`.</span></span> <span data-ttu-id="70615-137">Te tokeny są traktowane jako uwzględniające wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="70615-137">These tokens are treated as case sensitive.</span></span>

<span data-ttu-id="70615-138">`x:Single` może obsługiwać wartości w postaci notacji naukowej, jeśli pierwszy znak w składni tekstu jest `e` lub `E` .</span><span class="sxs-lookup"><span data-stu-id="70615-138">`x:Single` can support values in scientific notation form, if the first character in text syntax is `e` or `E`.</span></span>

<span data-ttu-id="70615-139">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.8 i 5.4.2](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-139">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.8 and 5.4.2](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xdouble"></a><span data-ttu-id="70615-140">x:Double</span><span class="sxs-lookup"><span data-stu-id="70615-140">x:Double</span></span>

<span data-ttu-id="70615-141">W przypadku środowiska CLR element `x:Double` podstawowy odpowiada <xref:System.Double> .</span><span class="sxs-lookup"><span data-stu-id="70615-141">For CLR backing, the `x:Double` primitive corresponds to <xref:System.Double>.</span></span>

<span data-ttu-id="70615-142">Oprócz wartości liczbowych, składnia tekstu dla zezwala na `x:Double` tokeny `Infinity` , `-Infinity` i `NaN` .</span><span class="sxs-lookup"><span data-stu-id="70615-142">In addition to the numeric values, text syntax for `x:Double` permits the tokens `Infinity`, `-Infinity`, and `NaN`.</span></span> <span data-ttu-id="70615-143">Te tokeny są traktowane jako uwzględniające wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="70615-143">These tokens are treated as case sensitive.</span></span>

<span data-ttu-id="70615-144">`x:Double` może obsługiwać wartości w postaci notacji naukowej.</span><span class="sxs-lookup"><span data-stu-id="70615-144">`x:Double` can support values in scientific notation form.</span></span> <span data-ttu-id="70615-145">Użyj znaku `e` lub, `E` Aby wprowadzić część wykładnika.</span><span class="sxs-lookup"><span data-stu-id="70615-145">Use the character `e` or `E` to introduce the exponent portion.</span></span>

<span data-ttu-id="70615-146">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.9 i 5.4.3](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-146">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.9 and 5.4.3](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint16"></a><span data-ttu-id="70615-147">x:Int16</span><span class="sxs-lookup"><span data-stu-id="70615-147">x:Int16</span></span>

<span data-ttu-id="70615-148">W przypadku tworzenia kopii zapasowych CLR element `x:Int16` podstawowy odpowiada <xref:System.Int16> i `x:Int16` jest traktowany jako podpisany.</span><span class="sxs-lookup"><span data-stu-id="70615-148">For CLR backing, the `x:Int16` primitive corresponds to <xref:System.Int16> and `x:Int16` is treated as signed.</span></span> <span data-ttu-id="70615-149">W języku XAML nieobecność znaku plus ( `+` ) w składni tekstu jest implikowana jako dodatnia wartość ze znakiem.</span><span class="sxs-lookup"><span data-stu-id="70615-149">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="70615-150">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.11 i 5.4.5](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-150">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.11 and 5.4.5](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint32"></a><span data-ttu-id="70615-151">x:Int32</span><span class="sxs-lookup"><span data-stu-id="70615-151">x:Int32</span></span>

<span data-ttu-id="70615-152">W przypadku środowiska CLR element `x:Int32` podstawowy odpowiada <xref:System.Int32> .</span><span class="sxs-lookup"><span data-stu-id="70615-152">For CLR backing, the `x:Int32` primitive corresponds to <xref:System.Int32>.</span></span> <span data-ttu-id="70615-153">`x:Int32` jest traktowane jako podpisane.</span><span class="sxs-lookup"><span data-stu-id="70615-153">`x:Int32` is treated as signed.</span></span> <span data-ttu-id="70615-154">W języku XAML nieobecność znaku plus ( `+` ) w składni tekstu jest implikowana jako dodatnia wartość ze znakiem.</span><span class="sxs-lookup"><span data-stu-id="70615-154">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="70615-155">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.12 i 5.4.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-155">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.12 and 5.4.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint64"></a><span data-ttu-id="70615-156">x:Int64</span><span class="sxs-lookup"><span data-stu-id="70615-156">x:Int64</span></span>

<span data-ttu-id="70615-157">W przypadku środowiska CLR element `x:Int64` podstawowy odpowiada <xref:System.Int64> .</span><span class="sxs-lookup"><span data-stu-id="70615-157">For CLR backing, the `x:Int64` primitive corresponds to <xref:System.Int64>.</span></span> <span data-ttu-id="70615-158">`x:Int64` jest traktowane jako podpisane.</span><span class="sxs-lookup"><span data-stu-id="70615-158">`x:Int64` is treated as signed.</span></span> <span data-ttu-id="70615-159">W języku XAML nieobecność znaku plus ( `+` ) w składni tekstu jest implikowana jako dodatnia wartość ze znakiem.</span><span class="sxs-lookup"><span data-stu-id="70615-159">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="70615-160">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.13 i 5.4.7](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-160">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.13 and 5.4.7](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xtimespan"></a><span data-ttu-id="70615-161">x:TimeSpan</span><span class="sxs-lookup"><span data-stu-id="70615-161">x:TimeSpan</span></span>

<span data-ttu-id="70615-162">W przypadku środowiska CLR element `x:TimeSpan` podstawowy odpowiada <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="70615-162">For CLR backing, the `x:TimeSpan` primitive corresponds to <xref:System.TimeSpan>.</span></span>

<span data-ttu-id="70615-163">Analiza kodu XAML dla formatu daty i godziny jest zaimplementowana w ramach `en-US` kultury.</span><span class="sxs-lookup"><span data-stu-id="70615-163">XAML parsing for time-date format is inherently done under `en-US` culture.</span></span>

<span data-ttu-id="70615-164">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.16 i 5.4.10](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-164">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.16 and 5.4.10](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xuri"></a><span data-ttu-id="70615-165">x:Uri</span><span class="sxs-lookup"><span data-stu-id="70615-165">x:Uri</span></span>

<span data-ttu-id="70615-166">W przypadku środowiska CLR element `x:Uri` podstawowy odpowiada <xref:System.Uri> .</span><span class="sxs-lookup"><span data-stu-id="70615-166">For CLR backing, the `x:Uri` primitive corresponds to <xref:System.Uri>.</span></span>

<span data-ttu-id="70615-167">Sprawdzanie protokołów nie jest częścią definicji XAML dla `x:Uri` .</span><span class="sxs-lookup"><span data-stu-id="70615-167">Checking for protocols is not part of the XAML definition for `x:Uri`.</span></span>

<span data-ttu-id="70615-168">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.15 i 5.4.9](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-168">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.15 and 5.4.9](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xbyte"></a><span data-ttu-id="70615-169">x:Byte</span><span class="sxs-lookup"><span data-stu-id="70615-169">x:Byte</span></span>

<span data-ttu-id="70615-170">W przypadku środowiska CLR element `x:Byte` podstawowy odpowiada <xref:System.Byte> .</span><span class="sxs-lookup"><span data-stu-id="70615-170">For CLR backing, the `x:Byte` primitive corresponds to <xref:System.Byte>.</span></span> <span data-ttu-id="70615-171">A <xref:System.Byte>  /  `x:Byte` jest traktowana jako niepodpisana.</span><span class="sxs-lookup"><span data-stu-id="70615-171">A <xref:System.Byte> / `x:Byte` is treated as unsigned.</span></span>

<span data-ttu-id="70615-172">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.10 i 5.4.4](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-172">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.10 and 5.4.4](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xarray"></a><span data-ttu-id="70615-173">x:Array</span><span class="sxs-lookup"><span data-stu-id="70615-173">x:Array</span></span>

<span data-ttu-id="70615-174">W przypadku środowiska CLR element `x:Array` podstawowy odpowiada <xref:System.Array> .</span><span class="sxs-lookup"><span data-stu-id="70615-174">For CLR backing, the `x:Array` primitive corresponds to <xref:System.Array>.</span></span>

<span data-ttu-id="70615-175">Można zdefiniować tablicę w języku XAML 2006 przy użyciu składni rozszerzenia znaczników; Jednak składnia XAML 2009 jest zdefiniowaną przez język podstawową, która nie wymaga dostępu do rozszerzenia znacznika.</span><span class="sxs-lookup"><span data-stu-id="70615-175">You can define an array in XAML 2006  by using a markup extension syntax; however, the XAML 2009 syntax is a language-defined primitive that does not require accessing a markup extension.</span></span> <span data-ttu-id="70615-176">Aby uzyskać więcej informacji na temat obsługi języka XAML 2006, zobacz [X:Array Markup Extension](xarray-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="70615-176">For more information about XAML 2006 support, see [x:Array Markup Extension](xarray-markup-extension.md).</span></span>

<span data-ttu-id="70615-177">Aby uzyskać definicję specyfikacji języka XAML, zobacz [ \[ sekcje MS-XAML \] 5.2.18](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="70615-177">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.18](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="wpf-support"></a><span data-ttu-id="70615-178">Obsługa WPF</span><span class="sxs-lookup"><span data-stu-id="70615-178">WPF Support</span></span>

<span data-ttu-id="70615-179">W programie WPF można używać funkcji języka XAML 2009, ale tylko dla języka XAML, który nie jest kompilowany do znaczników.</span><span class="sxs-lookup"><span data-stu-id="70615-179">In WPF, you can use XAML 2009 features but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="70615-180">Skompilowane znaczniki XAML dla WPF i forma BAML języka XAML nie obsługują obecnie słów kluczowych i funkcji języka XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="70615-180">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

<span data-ttu-id="70615-181">Scenariusz, w którym można używać funkcji języka XAML 2009 razem z WPF, to jeśli utworzysz luźny kod XAML, a następnie załadujesz ten kod XAML do środowiska uruchomieniowego WPF i grafu obiektów przy użyciu <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="70615-181">A scenario where you can use XAML 2009 features together with WPF is if you author loose XAML and you then load that XAML into a WPF runtime and object graph with <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="70615-182">WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> i jego <xref:System.Windows.Markup.XamlReader.Load%2A> Funkcja może przetwarzać słowa kluczowe języka XAML 2009 i funkcje do prawidłowej reprezentacji grafu obiektów.</span><span class="sxs-lookup"><span data-stu-id="70615-182">The WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> and its <xref:System.Windows.Markup.XamlReader.Load%2A> can process XAML 2009 language keywords and features into a valid object graph representation.</span></span>
