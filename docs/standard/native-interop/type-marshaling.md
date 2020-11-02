---
title: Kierowanie typów — .NET
description: Dowiedz się, w jaki sposób platforma .NET umożliwia kierowanie typów do natywnej reprezentacji.
ms.date: 01/18/2019
ms.openlocfilehash: bedaf49a5f7c5274f5e1bc7774490fec73651259
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188396"
---
# <a name="type-marshaling"></a><span data-ttu-id="68ffa-103">Marshaling typów</span><span class="sxs-lookup"><span data-stu-id="68ffa-103">Type marshaling</span></span>

<span data-ttu-id="68ffa-104">**Kierowanie** jest procesem przekształcania typów, gdy muszą one przecinać się między kodem zarządzanym i natywnym.</span><span class="sxs-lookup"><span data-stu-id="68ffa-104">**Marshaling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="68ffa-105">Organizowanie jest niezbędna, ponieważ typy w kodzie zarządzanym i niezarządzanym są różne.</span><span class="sxs-lookup"><span data-stu-id="68ffa-105">Marshaling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="68ffa-106">W kodzie zarządzanym, na przykład, posiadasz `String` , natomiast w niezarządzanych ciągach świata mogą być Unicode ("szerokie"), inne niż Unicode, zakończonych znakiem null, ASCII itd. Domyślnie podsystem P/Invoke próbuje wykonać właściwe czynności na podstawie domyślnego zachowania opisanego w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="68ffa-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="68ffa-107">Jednak dla tych sytuacji, gdy potrzebna jest dodatkowa kontrola, można użyć atrybutu [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) , aby określić, jaki jest oczekiwany typ na stronie niezarządzanej.</span><span class="sxs-lookup"><span data-stu-id="68ffa-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="68ffa-108">Na przykład, jeśli chcesz, aby ciąg był wysyłany jako ciąg ANSI zakończony wartością null, można to zrobić w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="68ffa-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshaling-common-types"></a><span data-ttu-id="68ffa-109">Domyślne reguły organizowania wspólnych typów</span><span class="sxs-lookup"><span data-stu-id="68ffa-109">Default rules for marshaling common types</span></span>

<span data-ttu-id="68ffa-110">Ogólnie rzecz biorąc, środowisko uruchomieniowe próbuje wykonać "prawo" podczas organizowania, aby wymagać od Ciebie najmniejszej ilości pracy.</span><span class="sxs-lookup"><span data-stu-id="68ffa-110">Generally, the runtime tries to do the "right thing" when marshaling to require the least amount of work from you.</span></span> <span data-ttu-id="68ffa-111">W poniższych tabelach opisano, jak każdy typ jest zorganizowany domyślnie, gdy jest używany w parametrze lub polu.</span><span class="sxs-lookup"><span data-stu-id="68ffa-111">The following tables describe how each type is marshaled by default when used in a parameter or field.</span></span> <span data-ttu-id="68ffa-112">Typy całkowite i znaki stałej szerokości C99/C++ 11 są używane w celu upewnienia się, że Poniższa tabela jest poprawna dla wszystkich platform.</span><span class="sxs-lookup"><span data-stu-id="68ffa-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="68ffa-113">Można użyć dowolnego typu natywnego, który ma takie same wymagania dotyczące wyrównania i rozmiaru co te typy.</span><span class="sxs-lookup"><span data-stu-id="68ffa-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="68ffa-114">W pierwszej tabeli opisano mapowania dla różnych typów, dla których kierowanie jest takie same dla obydwu P/Invoke i organizowania pól.</span><span class="sxs-lookup"><span data-stu-id="68ffa-114">This first table describes the mappings for various types for whom the marshaling is the same for both P/Invoke and field marshaling.</span></span>

| <span data-ttu-id="68ffa-115">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="68ffa-115">.NET Type</span></span> | <span data-ttu-id="68ffa-116">Typ natywny</span><span class="sxs-lookup"><span data-stu-id="68ffa-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="68ffa-117">Albo `char` w `char16_t` zależności od `CharSet` typu P/Invoke lub struktury.</span><span class="sxs-lookup"><span data-stu-id="68ffa-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="68ffa-118">Zobacz [dokumentację zestawu znaków](charset.md).</span><span class="sxs-lookup"><span data-stu-id="68ffa-118">See the [charset documentation](charset.md).</span></span> |
| `string`  | <span data-ttu-id="68ffa-119">Albo `char*` w `char16_t*` zależności od `CharSet` typu P/Invoke lub struktury.</span><span class="sxs-lookup"><span data-stu-id="68ffa-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="68ffa-120">Zobacz [dokumentację zestawu znaków](charset.md).</span><span class="sxs-lookup"><span data-stu-id="68ffa-120">See the [charset documentation](charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="68ffa-121">Typy wskaźników .NET (np.</span><span class="sxs-lookup"><span data-stu-id="68ffa-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="68ffa-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="68ffa-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="68ffa-123">Typ pochodzący od `System.Runtime.InteropServices.SafeHandle`</span><span class="sxs-lookup"><span data-stu-id="68ffa-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="68ffa-124">Typ pochodzący od `System.Runtime.InteropServices.CriticalHandle`</span><span class="sxs-lookup"><span data-stu-id="68ffa-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="68ffa-125">`BOOL`Typ Win32</span><span class="sxs-lookup"><span data-stu-id="68ffa-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="68ffa-126">`DECIMAL`Struktura com</span><span class="sxs-lookup"><span data-stu-id="68ffa-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="68ffa-127">Delegat platformy .NET</span><span class="sxs-lookup"><span data-stu-id="68ffa-127">.NET Delegate</span></span> | <span data-ttu-id="68ffa-128">Wskaźnik funkcji natywnej</span><span class="sxs-lookup"><span data-stu-id="68ffa-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="68ffa-129">`DATE`Typ Win32</span><span class="sxs-lookup"><span data-stu-id="68ffa-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="68ffa-130">`GUID`Typ Win32</span><span class="sxs-lookup"><span data-stu-id="68ffa-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="68ffa-131">Niektóre kategorie organizowania mają różne wartości domyślne, jeśli są organizowane jako parametry lub struktura.</span><span class="sxs-lookup"><span data-stu-id="68ffa-131">A few categories of marshaling have different defaults if you're marshaling as a parameter or structure.</span></span>

| <span data-ttu-id="68ffa-132">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="68ffa-132">.NET Type</span></span> | <span data-ttu-id="68ffa-133">Typ natywny (parametr)</span><span class="sxs-lookup"><span data-stu-id="68ffa-133">Native Type (Parameter)</span></span> | <span data-ttu-id="68ffa-134">Typ natywny (pole)</span><span class="sxs-lookup"><span data-stu-id="68ffa-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="68ffa-135">Tablica .NET</span><span class="sxs-lookup"><span data-stu-id="68ffa-135">.NET array</span></span> | <span data-ttu-id="68ffa-136">Wskaźnik do początku tablicy natywnych reprezentacji elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="68ffa-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="68ffa-137">Niedozwolone bez `[MarshalAs]` atrybutu</span><span class="sxs-lookup"><span data-stu-id="68ffa-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="68ffa-138">Klasa z `LayoutKind` `Sequential` lub `Explicit`</span><span class="sxs-lookup"><span data-stu-id="68ffa-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="68ffa-139">Wskaźnik do natywnej reprezentacji klasy</span><span class="sxs-lookup"><span data-stu-id="68ffa-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="68ffa-140">Natywna Reprezentacja klasy</span><span class="sxs-lookup"><span data-stu-id="68ffa-140">The native representation of the class</span></span> |

<span data-ttu-id="68ffa-141">Poniższa tabela zawiera domyślne reguły organizowania, które są przeznaczone tylko dla systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="68ffa-141">The following table includes the default marshaling rules that are Windows-only.</span></span> <span data-ttu-id="68ffa-142">Na platformach innych niż Windows nie można zorganizować tych typów.</span><span class="sxs-lookup"><span data-stu-id="68ffa-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="68ffa-143">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="68ffa-143">.NET Type</span></span> | <span data-ttu-id="68ffa-144">Typ natywny (parametr)</span><span class="sxs-lookup"><span data-stu-id="68ffa-144">Native Type (Parameter)</span></span> | <span data-ttu-id="68ffa-145">Typ natywny (pole)</span><span class="sxs-lookup"><span data-stu-id="68ffa-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="68ffa-146">Interfejs COM</span><span class="sxs-lookup"><span data-stu-id="68ffa-146">COM interface</span></span> | <span data-ttu-id="68ffa-147">Niedozwolone bez `[MarshalAs]` atrybutu</span><span class="sxs-lookup"><span data-stu-id="68ffa-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="68ffa-148">Niedozwolone</span><span class="sxs-lookup"><span data-stu-id="68ffa-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="68ffa-149">Niedozwolone</span><span class="sxs-lookup"><span data-stu-id="68ffa-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="68ffa-150">Niedozwolone</span><span class="sxs-lookup"><span data-stu-id="68ffa-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="68ffa-151">`int64_t` reprezentująca liczbę taktów od północy 1 stycznia 1601</span><span class="sxs-lookup"><span data-stu-id="68ffa-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="68ffa-152">`int64_t` reprezentująca liczbę taktów od północy 1 stycznia 1601</span><span class="sxs-lookup"><span data-stu-id="68ffa-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="68ffa-153">Niektóre typy mogą być organizowane tylko jako parametry, a nie jako pola.</span><span class="sxs-lookup"><span data-stu-id="68ffa-153">Some types can only be marshaled as parameters and not as fields.</span></span> <span data-ttu-id="68ffa-154">Te typy są wymienione w poniższej tabeli:</span><span class="sxs-lookup"><span data-stu-id="68ffa-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="68ffa-155">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="68ffa-155">.NET Type</span></span> | <span data-ttu-id="68ffa-156">Typ natywny (tylko parametr)</span><span class="sxs-lookup"><span data-stu-id="68ffa-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="68ffa-157">Albo w zależności od parametru `char*` `char16_t*` `CharSet` P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="68ffa-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="68ffa-158">Zobacz [dokumentację zestawu znaków](charset.md).</span><span class="sxs-lookup"><span data-stu-id="68ffa-158">See the [charset documentation](charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="68ffa-159">`va_list` (tylko w systemie Windows x86/x64/arm64)</span><span class="sxs-lookup"><span data-stu-id="68ffa-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="68ffa-160">Jeśli te wartości domyślne nie wykonują dokładnie tego, co chcesz, możesz dostosować sposób organizowania parametrów.</span><span class="sxs-lookup"><span data-stu-id="68ffa-160">If these defaults don't do exactly what you want, you can customize how parameters are marshaled.</span></span> <span data-ttu-id="68ffa-161">Artykuł dotyczący [organizowania parametrów](customize-parameter-marshaling.md) przeprowadzi Cię przez proces dostosowywania sposobu organizowania różnych typów parametrów.</span><span class="sxs-lookup"><span data-stu-id="68ffa-161">The [parameter marshaling](customize-parameter-marshaling.md) article walks you through how to customize how different parameter types are marshaled.</span></span>

## <a name="default-marshaling-in-com-scenarios"></a><span data-ttu-id="68ffa-162">Kierowanie domyślne w scenariuszach COM</span><span class="sxs-lookup"><span data-stu-id="68ffa-162">Default marshaling in COM scenarios</span></span>

<span data-ttu-id="68ffa-163">Podczas wywoływania metod obiektów COM w programie .NET środowisko uruchomieniowe platformy .NET zmienia domyślne reguły organizowania w celu dopasowania do wspólnej semantyki modelu COM.</span><span class="sxs-lookup"><span data-stu-id="68ffa-163">When you are calling methods on COM objects in .NET, the .NET runtime changes the default marshaling rules to match common COM semantics.</span></span> <span data-ttu-id="68ffa-164">W poniższej tabeli wymieniono reguły, których środowiska uruchomieniowe platformy .NET używają w scenariuszach COM:</span><span class="sxs-lookup"><span data-stu-id="68ffa-164">The following table lists the rules that .NET runtimes uses in COM scenarios:</span></span>

| <span data-ttu-id="68ffa-165">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="68ffa-165">.NET Type</span></span> | <span data-ttu-id="68ffa-166">Typ natywny (wywołania metody COM)</span><span class="sxs-lookup"><span data-stu-id="68ffa-166">Native Type (COM method calls)</span></span> |
|-----------|--------------------------------|
| `bool`    | `VARIANT_BOOL`                 |
| `StringBuilder` | `LPWSTR`                 |
| `string`  | `BSTR`                         |
| <span data-ttu-id="68ffa-167">Typy delegatów</span><span class="sxs-lookup"><span data-stu-id="68ffa-167">Delegate types</span></span> | <span data-ttu-id="68ffa-168">`_Delegate*` w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68ffa-168">`_Delegate*` in .NET Framework.</span></span> <span data-ttu-id="68ffa-169">Niedozwolone w przypadku programów .NET Core i .NET 5 +.</span><span class="sxs-lookup"><span data-stu-id="68ffa-169">Disallowed in .NET Core and .NET 5+.</span></span> |
| `System.Drawing.Color` | `OLECOLOR`        |
| <span data-ttu-id="68ffa-170">Tablica .NET</span><span class="sxs-lookup"><span data-stu-id="68ffa-170">.NET array</span></span> | `SAFEARRAY`                   |
| `string[]` | <span data-ttu-id="68ffa-171">`SAFEARRAY` z `BSTR` s</span><span class="sxs-lookup"><span data-stu-id="68ffa-171">`SAFEARRAY` of `BSTR`s</span></span>        |

## <a name="marshaling-classes-and-structs"></a><span data-ttu-id="68ffa-172">Kierowanie klas i struktur</span><span class="sxs-lookup"><span data-stu-id="68ffa-172">Marshaling classes and structs</span></span>

<span data-ttu-id="68ffa-173">Innym aspektem organizowania typów jest sposób przekazywania struktury do niezarządzanej metody.</span><span class="sxs-lookup"><span data-stu-id="68ffa-173">Another aspect of type marshaling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="68ffa-174">Na przykład niektóre metody niezarządzane wymagają struktury jako parametru.</span><span class="sxs-lookup"><span data-stu-id="68ffa-174">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="68ffa-175">W takich przypadkach należy utworzyć odpowiednią strukturę lub klasę w zarządzanej części świata, aby użyć jej jako parametru.</span><span class="sxs-lookup"><span data-stu-id="68ffa-175">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="68ffa-176">Jednak tylko zdefiniowanie klasy jest niewystarczające, należy również poinstruować organizatora, jak mapować pola w klasie na niezarządzaną strukturę.</span><span class="sxs-lookup"><span data-stu-id="68ffa-176">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="68ffa-177">W tym miejscu `StructLayout` atrybut jest przydatny.</span><span class="sxs-lookup"><span data-stu-id="68ffa-177">Here the `StructLayout` attribute becomes useful.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="68ffa-178">Poprzedni kod pokazuje prosty przykład wywołania `GetSystemTime()` funkcji.</span><span class="sxs-lookup"><span data-stu-id="68ffa-178">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="68ffa-179">Interesujący bit jest w wierszu 4.</span><span class="sxs-lookup"><span data-stu-id="68ffa-179">The interesting bit is on line 4.</span></span> <span data-ttu-id="68ffa-180">Ten atrybut określa, że pola klasy powinny być mapowane sekwencyjnie do struktury na drugiej (niezarządzanej) stronie.</span><span class="sxs-lookup"><span data-stu-id="68ffa-180">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="68ffa-181">Oznacza to, że nazwy pól nie są ważne, tylko ich kolejność jest ważna, ponieważ musi odpowiadać strukturze niezarządzanej, pokazanej w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="68ffa-181">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="68ffa-182">Czasami domyślne kierowanie dla Twojej struktury nie robi tego, czego potrzebujesz.</span><span class="sxs-lookup"><span data-stu-id="68ffa-182">Sometimes the default marshaling for your structure doesn't do what you need.</span></span> <span data-ttu-id="68ffa-183">W artykule [Dostosowywanie struktury dostosowywania](./customize-struct-marshaling.md) przedstawiono sposób dostosowywania struktury struktur.</span><span class="sxs-lookup"><span data-stu-id="68ffa-183">The [Customizing structure marshaling](./customize-struct-marshaling.md) article teaches you how to customize how your structure is marshaled.</span></span>
