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
ms.openlocfilehash: a5c38c29a45a9ce6f8aed7205c5bd44bebb023c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683723"
---
# <a name="parse-strings-in-net"></a><span data-ttu-id="3093e-105">Analizowanie ciągów w programie .NET</span><span class="sxs-lookup"><span data-stu-id="3093e-105">Parse strings in .NET</span></span>

<span data-ttu-id="3093e-106">Operacja *analizowania* konwertuje ciąg, który reprezentuje typ podstawowy platformy .NET do tego typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="3093e-106">A *parsing* operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="3093e-107">Na przykład operacja analizowania służy do konwertowania ciągu na liczbę zmiennoprzecinkową lub na wartość daty i godziny.</span><span class="sxs-lookup"><span data-stu-id="3093e-107">For example, a parsing operation is used to convert a string to a floating-point number or to a date-and-time value.</span></span> <span data-ttu-id="3093e-108">Metoda najczęściej używana do wykonywania operacji analizowania jest `Parse` metodą.</span><span class="sxs-lookup"><span data-stu-id="3093e-108">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="3093e-109">Ponieważ analizowanie jest operacją wsteczną formatowania (która wymaga przekonwertowania typu bazowego na jego reprezentację ciągu), mają zastosowanie wiele z tych samych zasad i Konwencji.</span><span class="sxs-lookup"><span data-stu-id="3093e-109">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="3093e-110">Tak samo jak formatowanie korzysta z obiektu, który implementuje <xref:System.IFormatProvider> interfejs, aby zapewnić informacje o formatowaniu z uwzględnieniem kultury, podczas analizy używa również obiektu, który implementuje <xref:System.IFormatProvider> interfejs, aby określić sposób interpretowania przedstawienia ciągu.</span><span class="sxs-lookup"><span data-stu-id="3093e-110">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="3093e-111">Aby uzyskać więcej informacji, zobacz [typy formatów](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="3093e-111">For more information, see [Format types](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3093e-112">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="3093e-112">In This Section</span></span>

 <span data-ttu-id="3093e-113">[Analizowanie ciągów liczbowych](parsing-numeric.md)</span><span class="sxs-lookup"><span data-stu-id="3093e-113">[Parsing Numeric Strings](parsing-numeric.md)</span></span>\
 <span data-ttu-id="3093e-114">Opisuje sposób konwersji ciągów na typy liczbowe platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="3093e-114">Describes how to convert strings into .NET numeric types.</span></span>

 <span data-ttu-id="3093e-115">[Analizowanie ciągów daty i godziny](parsing-datetime.md)</span><span class="sxs-lookup"><span data-stu-id="3093e-115">[Parsing Date and Time Strings](parsing-datetime.md)</span></span>\
 <span data-ttu-id="3093e-116">Opisuje sposób konwertowania ciągów na typy **datetimes** platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="3093e-116">Describes how to convert strings into .NET **DateTime** types.</span></span>

 <span data-ttu-id="3093e-117">[Analizowanie innych ciągów](parsing-other.md)</span><span class="sxs-lookup"><span data-stu-id="3093e-117">[Parsing Other Strings](parsing-other.md)</span></span>\
 <span data-ttu-id="3093e-118">Opisuje sposób konwersji ciągów na typy **znaków**, **wartości logicznych** i typów **wyliczeniowych** .</span><span class="sxs-lookup"><span data-stu-id="3093e-118">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>

## <a name="related-sections"></a><span data-ttu-id="3093e-119">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="3093e-119">Related Sections</span></span>

 <span data-ttu-id="3093e-120">[Formatowanie typów](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="3093e-120">[Formatting Types](formatting-types.md)</span></span>\
 <span data-ttu-id="3093e-121">Opisuje podstawowe pojęcia dotyczące formatowania, takie jak specyfikatory formatu i dostawcy formatowania.</span><span class="sxs-lookup"><span data-stu-id="3093e-121">Describes basic formatting concepts like format specifiers and format providers.</span></span>

 <span data-ttu-id="3093e-122">[Konwersja typów w programie .NET](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="3093e-122">[Type Conversion in .NET](type-conversion.md)</span></span>\
 <span data-ttu-id="3093e-123">Opisuje sposób konwersji typów.</span><span class="sxs-lookup"><span data-stu-id="3093e-123">Describes how to convert types.</span></span>
