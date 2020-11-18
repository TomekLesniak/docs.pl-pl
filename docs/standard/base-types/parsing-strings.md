---
title: Konwertowanie ciągów na typy
description: Zrozumienie analizy ciągów w programie .NET. Analizowanie konwertuje ciąg reprezentujący typ podstawowy platformy .NET na ten typ podstawowy. Analizowanie jest operacją wsteczną do formatowania.
ms.date: 03/30/2017
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 8fbfe8596e49ed101ea7d6bb65298e432a6fac13
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821908"
---
# <a name="parse-strings-in-net"></a><span data-ttu-id="c49e0-105">Analizowanie ciągów w programie .NET</span><span class="sxs-lookup"><span data-stu-id="c49e0-105">Parse strings in .NET</span></span>

<span data-ttu-id="c49e0-106">Operacja *analizowania* konwertuje ciąg, który reprezentuje typ podstawowy platformy .NET do tego typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="c49e0-106">A *parsing* operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="c49e0-107">Na przykład operacja analizowania służy do konwertowania ciągu na liczbę zmiennoprzecinkową lub na wartość daty i godziny.</span><span class="sxs-lookup"><span data-stu-id="c49e0-107">For example, a parsing operation is used to convert a string to a floating-point number or to a date-and-time value.</span></span> <span data-ttu-id="c49e0-108">Metoda najczęściej używana do wykonywania operacji analizowania jest `Parse` metodą.</span><span class="sxs-lookup"><span data-stu-id="c49e0-108">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="c49e0-109">Ponieważ analizowanie jest operacją wsteczną formatowania (która wymaga przekonwertowania typu bazowego na jego reprezentację ciągu), mają zastosowanie wiele z tych samych zasad i Konwencji.</span><span class="sxs-lookup"><span data-stu-id="c49e0-109">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="c49e0-110">Tak samo jak formatowanie korzysta z obiektu, który implementuje <xref:System.IFormatProvider> interfejs, aby zapewnić informacje o formatowaniu z uwzględnieniem kultury, podczas analizy używa również obiektu, który implementuje <xref:System.IFormatProvider> interfejs, aby określić sposób interpretowania przedstawienia ciągu.</span><span class="sxs-lookup"><span data-stu-id="c49e0-110">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="c49e0-111">Aby uzyskać więcej informacji, zobacz [typy formatów](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="c49e0-111">For more information, see [Format types](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c49e0-112">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="c49e0-112">In This Section</span></span>
 <span data-ttu-id="c49e0-113">[Analizowanie ciągów liczbowych](parsing-numeric.md)</span><span class="sxs-lookup"><span data-stu-id="c49e0-113">[Parsing Numeric Strings](parsing-numeric.md)</span></span>\
 <span data-ttu-id="c49e0-114">Opisuje sposób konwersji ciągów na typy liczbowe platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c49e0-114">Describes how to convert strings into .NET numeric types.</span></span>

 <span data-ttu-id="c49e0-115">[Analizowanie ciągów daty i godziny](parsing-datetime.md)</span><span class="sxs-lookup"><span data-stu-id="c49e0-115">[Parsing Date and Time Strings](parsing-datetime.md)</span></span>\
 <span data-ttu-id="c49e0-116">Opisuje sposób konwertowania ciągów na typy **datetimes** platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c49e0-116">Describes how to convert strings into .NET **DateTime** types.</span></span>

 <span data-ttu-id="c49e0-117">[Analizowanie innych ciągów](parsing-other.md)</span><span class="sxs-lookup"><span data-stu-id="c49e0-117">[Parsing Other Strings](parsing-other.md)</span></span>\
 <span data-ttu-id="c49e0-118">Opisuje sposób konwersji ciągów na typy **znaków**, **wartości logicznych** i typów **wyliczeniowych** .</span><span class="sxs-lookup"><span data-stu-id="c49e0-118">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c49e0-119">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="c49e0-119">Related Sections</span></span>
 <span data-ttu-id="c49e0-120">[Formatowanie typów](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="c49e0-120">[Formatting Types](formatting-types.md)</span></span>\
 <span data-ttu-id="c49e0-121">Opisuje podstawowe pojęcia dotyczące formatowania, takie jak specyfikatory formatu i dostawcy formatowania.</span><span class="sxs-lookup"><span data-stu-id="c49e0-121">Describes basic formatting concepts like format specifiers and format providers.</span></span>

 <span data-ttu-id="c49e0-122">[Konwersja typów w programie .NET](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="c49e0-122">[Type Conversion in .NET](type-conversion.md)</span></span>\
 <span data-ttu-id="c49e0-123">Opisuje sposób konwersji typów.</span><span class="sxs-lookup"><span data-stu-id="c49e0-123">Describes how to convert types.</span></span>
