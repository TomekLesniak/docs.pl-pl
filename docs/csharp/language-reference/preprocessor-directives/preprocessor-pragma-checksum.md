---
description: '#pragma checksum — odwołanie w C#'
title: '#pragma checksum — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 60c491000337fd50da217e97054e86faccb2e7d7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137984"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="89824-103">#pragma checksum (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="89824-103">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="89824-104">Generuje sumy kontrolne dla plików źródłowych, aby pomóc w debugowaniu stron ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="89824-104">Generates checksums for source files to aid with debugging ASP.NET pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89824-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="89824-105">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a><span data-ttu-id="89824-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="89824-106">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="89824-107">Nazwa pliku, który wymaga monitorowania pod kątem zmian lub aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="89824-107">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="89824-108">Unikatowy identyfikator globalny (GUID) algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="89824-108">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="89824-109">Ciąg cyfr szesnastkowych reprezentujących bajty sum kontrolnych.</span><span class="sxs-lookup"><span data-stu-id="89824-109">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="89824-110">Musi być parzystą liczbą cyfr szesnastkowych.</span><span class="sxs-lookup"><span data-stu-id="89824-110">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="89824-111">Nieparzysta liczba cyfr skutkuje ostrzeżeniem w czasie kompilacji, a dyrektywa jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="89824-111">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89824-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="89824-112">Remarks</span></span>  
 <span data-ttu-id="89824-113">Debuger programu Visual Studio używa sumy kontrolnej, aby upewnić się, że zawsze znajdzie prawidłowe źródło.</span><span class="sxs-lookup"><span data-stu-id="89824-113">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="89824-114">Kompilator oblicza sumę kontrolną pliku źródłowego, a następnie emituje dane wyjściowe do pliku bazy danych programu (PDB).</span><span class="sxs-lookup"><span data-stu-id="89824-114">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="89824-115">Debuger następnie używa pliku PDB do porównania z sumą kontrolną, która jest obliczana dla plików źródłowych.</span><span class="sxs-lookup"><span data-stu-id="89824-115">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="89824-116">To rozwiązanie nie działa w przypadku projektów ASP.NET, ponieważ obliczona suma kontrolna jest dla wygenerowanego pliku źródłowego, a nie pliku. aspx.</span><span class="sxs-lookup"><span data-stu-id="89824-116">This solution does not work for ASP.NET projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="89824-117">Aby rozwiązać ten problem, program `#pragma checksum` zapewnia obsługę sum kontrolnych dla stron ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="89824-117">To address this problem, `#pragma checksum` provides checksum support for ASP.NET pages.</span></span>  
  
 <span data-ttu-id="89824-118">Podczas tworzenia projektu ASP.NET w programie Visual C# wygenerowany plik źródłowy zawiera sumę kontrolną dla pliku. aspx, z którego jest generowane źródło.</span><span class="sxs-lookup"><span data-stu-id="89824-118">When you create an ASP.NET project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="89824-119">Następnie kompilator zapisuje te informacje w pliku PDB.</span><span class="sxs-lookup"><span data-stu-id="89824-119">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="89824-120">Jeśli kompilator napotka brak `#pragma checksum` dyrektywy w pliku, oblicza sumę kontrolną i zapisuje wartość do pliku PDB.</span><span class="sxs-lookup"><span data-stu-id="89824-120">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89824-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="89824-121">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="89824-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="89824-122">See also</span></span>

- [<span data-ttu-id="89824-123">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="89824-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="89824-124">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="89824-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="89824-125">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="89824-125">C# Preprocessor Directives</span></span>](./index.md)
