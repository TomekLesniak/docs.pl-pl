---
title: Typy SIMD-przyspieszone w programie .NET
description: W tym artykule opisano typy SIMD-Enable w programie .NET i pokazano, jak używać sprzętowych operacji SIMD w językach C# i .NET.
author: FIVIL
ms.author: tagoo
ms.date: 04/28/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 5c1ad01ea15a9c4352cf7f87e5fba3bf74b4679c
ms.sourcegitcommit: 2987e241e2f76c9248d2146bf2761a33e2c7a882
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/14/2020
ms.locfileid: "88228736"
---
# <a name="use-simd-accelerated-numeric-types"></a><span data-ttu-id="b6557-103">Użyj SIMD — przyspieszone typy liczbowe</span><span class="sxs-lookup"><span data-stu-id="b6557-103">Use SIMD-accelerated numeric types</span></span>

<span data-ttu-id="b6557-104">SIMD (pojedyncza instrukcja, wiele danych) zapewnia obsługę sprzętu na potrzeby wykonywania operacji na wielu danych, równolegle przy użyciu jednej instrukcji.</span><span class="sxs-lookup"><span data-stu-id="b6557-104">SIMD (Single instruction, multiple data) provides hardware support for performing an operation on multiple pieces of data, in parallel, using a single instruction.</span></span> <span data-ttu-id="b6557-105">W programie .NET istnieje zestaw SIMD-przyspieszone typy w <xref:System.Numerics> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b6557-105">In .NET, there's set of SIMD-accelerated types under the <xref:System.Numerics> namespace.</span></span> <span data-ttu-id="b6557-106">Operacje SIMD mogą być równoległe na poziomie sprzętu.</span><span class="sxs-lookup"><span data-stu-id="b6557-106">SIMD operations can be parallelized at the hardware level.</span></span> <span data-ttu-id="b6557-107">Zwiększa to przepływność obliczeń wektorowych, które są wspólne w aplikacjach matematycznych, naukowych i graficznych.</span><span class="sxs-lookup"><span data-stu-id="b6557-107">That increases the throughput of the vectorized computations, which are common in mathematical, scientific, and graphics apps.</span></span>

## <a name="net-simd-accelerated-types"></a><span data-ttu-id="b6557-108">.NET SIMD — przyspieszone typy</span><span class="sxs-lookup"><span data-stu-id="b6557-108">.NET SIMD-accelerated types</span></span>

<span data-ttu-id="b6557-109">Typy przyspieszone dla programu .NET SIMD obejmują następujące typy:</span><span class="sxs-lookup"><span data-stu-id="b6557-109">The .NET SIMD-accelerated types include the following types:</span></span>

- <span data-ttu-id="b6557-110"><xref:System.Numerics.Vector2>Typy, <xref:System.Numerics.Vector3> i <xref:System.Numerics.Vector4> , które reprezentują wektory z 2, 3 i 4 <xref:System.Single> wartościami.</span><span class="sxs-lookup"><span data-stu-id="b6557-110">The <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, and <xref:System.Numerics.Vector4> types, which represent vectors with 2, 3, and 4 <xref:System.Single> values.</span></span>

- <span data-ttu-id="b6557-111">Dwa typy macierzy, <xref:System.Numerics.Matrix3x2> , które reprezentują macierz 3 x 2, i <xref:System.Numerics.Matrix4x4> , która reprezentuje macierz 4x4 <xref:System.Single> wartości.</span><span class="sxs-lookup"><span data-stu-id="b6557-111">Two matrix types, <xref:System.Numerics.Matrix3x2>, which represents a 3x2 matrix, and <xref:System.Numerics.Matrix4x4>, which represents a 4x4 matrix of <xref:System.Single> values.</span></span>

- <span data-ttu-id="b6557-112"><xref:System.Numerics.Plane>Typ, który reprezentuje płaszczyznę w trójwymiarowym miejscu przy użyciu <xref:System.Single> wartości.</span><span class="sxs-lookup"><span data-stu-id="b6557-112">The <xref:System.Numerics.Plane> type, which represents a plane in three-dimensional space using <xref:System.Single> values.</span></span>

- <span data-ttu-id="b6557-113"><xref:System.Numerics.Quaternion>Typ, który reprezentuje wektor, który jest używany do kodowania trójwymiarowych obrotów fizycznych przy użyciu <xref:System.Single> wartości.</span><span class="sxs-lookup"><span data-stu-id="b6557-113">The <xref:System.Numerics.Quaternion> type, which represents a vector that is used to encode three-dimensional physical rotations using <xref:System.Single> values.</span></span>

- <span data-ttu-id="b6557-114"><xref:System.Numerics.Vector%601>Typ, który reprezentuje wektor określonego typu liczbowego i zawiera szeroki zestaw operatorów, które korzystają z obsługi SIMD.</span><span class="sxs-lookup"><span data-stu-id="b6557-114">The <xref:System.Numerics.Vector%601> type, which represents a vector of a specified numeric type and provides a broad set of operators that benefit from SIMD support.</span></span> <span data-ttu-id="b6557-115">Liczba <xref:System.Numerics.Vector%601> wystąpień jest ustalona przez okres istnienia aplikacji, ale jej wartość <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> zależy od procesora komputera, na którym uruchomiono kod.</span><span class="sxs-lookup"><span data-stu-id="b6557-115">The count of a <xref:System.Numerics.Vector%601> instance is fixed for the lifetime of an application, but its value <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> depends on the CPU of the machine running the code.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b6557-116"><xref:System.Numerics.Vector%601>Typ nie jest uwzględniony w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6557-116">The <xref:System.Numerics.Vector%601> type is not included in the .NET Framework.</span></span> <span data-ttu-id="b6557-117">Musisz zainstalować pakiet NuGet [System. Numerics. Vectors](https://www.nuget.org/packages/System.Numerics.Vectors) , aby uzyskać dostęp do tego typu.</span><span class="sxs-lookup"><span data-stu-id="b6557-117">You must install the [System.Numerics.Vectors](https://www.nuget.org/packages/System.Numerics.Vectors) NuGet package to get access to this type.</span></span>
  
<span data-ttu-id="b6557-118">Typy SIMD-przyspieszone są implementowane w taki sposób, że mogą być używane z akceleratorami sprzętu lub kompilatorów JIT nieSIMDymi.</span><span class="sxs-lookup"><span data-stu-id="b6557-118">The SIMD-accelerated types are implemented in such a way that they can be used with non-SIMD-accelerated hardware or JIT compilers.</span></span> <span data-ttu-id="b6557-119">Aby skorzystać z instrukcji SIMD, aplikacje 64-bitowe muszą być uruchamiane przez środowisko uruchomieniowe, które używa kompilatora **RyuJIT** .</span><span class="sxs-lookup"><span data-stu-id="b6557-119">To take advantage of SIMD instructions, your 64-bit apps must be run by the runtime that uses the **RyuJIT** compiler.</span></span> <span data-ttu-id="b6557-120">Kompilator **RyuJIT** jest dołączany do oprogramowania .NET Core i w .NET Framework 4,6 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="b6557-120">A **RyuJIT** compiler is included in .NET Core and in .NET Framework 4.6 and later.</span></span> <span data-ttu-id="b6557-121">Obsługa SIMD jest zapewniana tylko w przypadku procesorów 64-bitowych.</span><span class="sxs-lookup"><span data-stu-id="b6557-121">SIMD support is only provided when targeting 64-bit processors.</span></span>

## <a name="how-to-use-simd"></a><span data-ttu-id="b6557-122">Jak używać SIMD?</span><span class="sxs-lookup"><span data-stu-id="b6557-122">How to use SIMD?</span></span>

<span data-ttu-id="b6557-123">Przed wykonaniem niestandardowych algorytmów SIMD można sprawdzić, czy maszyna hosta obsługuje SIMD przy użyciu <xref:System.Numerics.Vector.IsHardwareAccelerated?displayProperty=nameWithType> , która zwraca <xref:System.Boolean> .</span><span class="sxs-lookup"><span data-stu-id="b6557-123">Before executing custom SIMD algorithms, it's possible to check if the host machine supports SIMD by using <xref:System.Numerics.Vector.IsHardwareAccelerated?displayProperty=nameWithType>, which returns a <xref:System.Boolean>.</span></span> <span data-ttu-id="b6557-124">Nie gwarantuje to, że przyspieszenie SIMD jest włączone dla określonego typu, ale jest wskaźnikiem, który jest obsługiwany przez niektóre typy.</span><span class="sxs-lookup"><span data-stu-id="b6557-124">This doesn't guarantee that SIMD-acceleration is enabled for a specific type, but is an indicator that it's supported by some types.</span></span>

## <a name="simple-vectors"></a><span data-ttu-id="b6557-125">Proste wektory</span><span class="sxs-lookup"><span data-stu-id="b6557-125">Simple Vectors</span></span>

<span data-ttu-id="b6557-126">Najbardziej pierwotne typy SIMD-przyspieszone w programie .NET to <xref:System.Numerics.Vector2> , <xref:System.Numerics.Vector3> i <xref:System.Numerics.Vector4> typy, które reprezentują wektory z 2, 3 i 4 <xref:System.Single> wartościami.</span><span class="sxs-lookup"><span data-stu-id="b6557-126">The most primitive SIMD-accelerated types in .NET are <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, and <xref:System.Numerics.Vector4> types, which represent vectors with 2, 3, and 4 <xref:System.Single> values.</span></span> <span data-ttu-id="b6557-127">Poniższy przykład używa <xref:System.Numerics.Vector2> do dodawania dwóch wektorów.</span><span class="sxs-lookup"><span data-stu-id="b6557-127">The example below uses <xref:System.Numerics.Vector2> to add two vectors.</span></span>

```csharp
var v1 = new Vector2(0.1f, 0.2f);
var v2 = new Vector2(1.1f, 2.2f);
var vResult = v1 + v2;
```

<span data-ttu-id="b6557-128">Istnieje również możliwość użycia wektorów .NET do obliczenia innych właściwości matematycznych wektorów, takich jak `Dot product` , `Transform` , `Clamp` i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="b6557-128">It's also possible to use .NET vectors to calculate other mathematical properties of vectors such as `Dot product`, `Transform`, `Clamp` and so on.</span></span>

```csharp
var v1 = new Vector2(0.1f, 0.2f);
var v2 = new Vector2(1.1f, 2.2f);
var vResult1 = Vector2.Dot(v1, v2);
var vResult2 = Vector2.Distance(v1, v2);
var vResult3 = Vector2.Clamp(v1, Vector2.Zero, Vector2.One);
```

## <a name="matrix"></a><span data-ttu-id="b6557-129">Macierz</span><span class="sxs-lookup"><span data-stu-id="b6557-129">Matrix</span></span>

<span data-ttu-id="b6557-130"><xref:System.Numerics.Matrix3x2>, która reprezentuje macierz 3 x 2, i <xref:System.Numerics.Matrix4x4> reprezentuje macierz 4x4.</span><span class="sxs-lookup"><span data-stu-id="b6557-130"><xref:System.Numerics.Matrix3x2>, which represents a 3x2 matrix, and <xref:System.Numerics.Matrix4x4>, which represents a 4x4 matrix.</span></span> <span data-ttu-id="b6557-131">Może służyć do obliczeń dotyczących macierzy.</span><span class="sxs-lookup"><span data-stu-id="b6557-131">Can be used for matrix-related calculations.</span></span> <span data-ttu-id="b6557-132">W poniższym przykładzie pokazano mnożenie macierzy do macierzy transtransponowanej przy użyciu SIMD.</span><span class="sxs-lookup"><span data-stu-id="b6557-132">The example below demonstrates multiplication of a matrix to its correspondent transpose matrix using SIMD.</span></span>

```csharp
var m1 = new Matrix4x4(
            1.1f, 1.2f, 1.3f, 1.4f,
            2.1f, 2.2f, 3.3f, 4.4f,
            3.1f, 3.2f, 3.3f, 3.4f,
            4.1f, 4.2f, 4.3f, 4.4f);

var m2 = Matrix4x4.Transpose(m1);
var mResult = Matrix4x4.Multiply(m1, m2);
```

## <a name="vectort"></a><span data-ttu-id="b6557-133">Niemożliwe\<T></span><span class="sxs-lookup"><span data-stu-id="b6557-133">Vector\<T></span></span>

<span data-ttu-id="b6557-134"><xref:System.Numerics.Vector%601>Daje możliwość użycia dłuższych wektorów.</span><span class="sxs-lookup"><span data-stu-id="b6557-134">The <xref:System.Numerics.Vector%601> gives the ability to use longer vectors.</span></span> <span data-ttu-id="b6557-135">Licznik <xref:System.Numerics.Vector%601> wystąpienia został naprawiony, ale jego wartość <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> zależy od procesora komputera, na którym uruchomiono kod.</span><span class="sxs-lookup"><span data-stu-id="b6557-135">The count of a <xref:System.Numerics.Vector%601> instance is fixed, but its value <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> depends on the CPU of the machine running the code.</span></span>

<span data-ttu-id="b6557-136">W poniższym przykładzie pokazano Dodawanie długich elementów tablic za pomocą <xref:System.Numerics.Vector%601> .</span><span class="sxs-lookup"><span data-stu-id="b6557-136">The example below demonstrates adding long arrays elements using <xref:System.Numerics.Vector%601>.</span></span>

```csharp
double[] SimdVectorProd(double[] left, double[] right)
{
    var offset = Vector<double>.Count;
    double[] result = new double[left.Length];
    int i = 0;
    for (i = 0; i < left.Length; i += offset)
    {
        var v1 = new Vector<double>(left, i);
        var v2 = new Vector<double>(right, i);
        (v1 * v2).CopyTo(result, i);
    }

    //remaining items
    for (; i < left.Length; ++i)
    {
        result[i] = left[i] * right[i];
    }

    return result;
}
```

## <a name="remarks"></a><span data-ttu-id="b6557-137">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b6557-137">Remarks</span></span>

<span data-ttu-id="b6557-138">SIMD może usunąć jedną wąskie gardła i uwidocznić kolejne, na przykład przepustowość pamięci.</span><span class="sxs-lookup"><span data-stu-id="b6557-138">SIMD is more likely to remove one bottleneck and expose the next, for example memory throughput.</span></span> <span data-ttu-id="b6557-139">Ogólnie rzecz biorąc, korzyści wynikające z używania SIMD różnią się w zależności od konkretnego scenariusza, a w niektórych przypadkach może to nawet być gorsza niż prostszy kod nieSIMD równoważny.</span><span class="sxs-lookup"><span data-stu-id="b6557-139">In general the performance benefit of using SIMD varies depending on the specific scenario, and in some cases it can even perform worse than simpler non-SIMD equivalent code.</span></span>
