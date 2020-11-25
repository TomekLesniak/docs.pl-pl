---
title: 'Przykładowe wyrażenie regularne: zmienianie formatów daty'
ms.date: 06/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET regular expressions, examples
- regular expressions [.NET], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
ms.openlocfilehash: 9e23a11bd6eac0a77ef04d95cfab8db5d5e26807
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733571"
---
# <a name="regular-expression-example-changing-date-formats"></a><span data-ttu-id="6af4d-102">Przykładowe wyrażenie regularne: zmienianie formatów daty</span><span class="sxs-lookup"><span data-stu-id="6af4d-102">Regular Expression Example: Changing Date Formats</span></span>

<span data-ttu-id="6af4d-103">Poniższy przykład kodu używa <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> metody, aby zastąpić daty, które mają postać *mm* / *DD* / *yy* z datami, które mają postać *DD* - *mm* - *RR*.</span><span class="sxs-lookup"><span data-stu-id="6af4d-103">The following code example uses the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to replace dates that have the form *mm*/*dd*/*yy* with dates that have the form *dd*-*mm*-*yy*.</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="6af4d-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="6af4d-104">Example</span></span>  

 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 <span data-ttu-id="6af4d-105">Poniższy kod pokazuje, jak `MDYToDMY` Metoda może być wywoływana w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6af4d-105">The following code shows how the `MDYToDMY` method can be called in an application.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a><span data-ttu-id="6af4d-106">Komentarze</span><span class="sxs-lookup"><span data-stu-id="6af4d-106">Comments</span></span>  

 <span data-ttu-id="6af4d-107">Wzorzec wyrażenia regularnego  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` jest interpretowany jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="6af4d-107">The regular expression pattern  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="6af4d-108">Wzorce</span><span class="sxs-lookup"><span data-stu-id="6af4d-108">Pattern</span></span>|<span data-ttu-id="6af4d-109">Opis</span><span class="sxs-lookup"><span data-stu-id="6af4d-109">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="6af4d-110">Rozpoczyna dopasowanie na granicy wyrazu.</span><span class="sxs-lookup"><span data-stu-id="6af4d-110">Begin the match at a word boundary.</span></span>|  
|`(?<month>\d{1,2})`|<span data-ttu-id="6af4d-111">Dopasowuje jedną lub dwie cyfry dziesiętne.</span><span class="sxs-lookup"><span data-stu-id="6af4d-111">Match one or two decimal digits.</span></span> <span data-ttu-id="6af4d-112">To jest `month` Grupa przechwycona.</span><span class="sxs-lookup"><span data-stu-id="6af4d-112">This is the `month` captured group.</span></span>|  
|`/`|<span data-ttu-id="6af4d-113">Dopasowuje znak ukośnika.</span><span class="sxs-lookup"><span data-stu-id="6af4d-113">Match the slash mark.</span></span>|  
|`(?<day>\d{1,2})`|<span data-ttu-id="6af4d-114">Dopasowuje jedną lub dwie cyfry dziesiętne.</span><span class="sxs-lookup"><span data-stu-id="6af4d-114">Match one or two decimal digits.</span></span> <span data-ttu-id="6af4d-115">To jest `day` Grupa przechwycona.</span><span class="sxs-lookup"><span data-stu-id="6af4d-115">This is the `day` captured group.</span></span>|  
|`/`|<span data-ttu-id="6af4d-116">Dopasowuje znak ukośnika.</span><span class="sxs-lookup"><span data-stu-id="6af4d-116">Match the slash mark.</span></span>|  
|`(?<year>\d{2,4})`|<span data-ttu-id="6af4d-117">Dopasowuje od dwóch do czterech cyfr dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="6af4d-117">Match from two to four decimal digits.</span></span> <span data-ttu-id="6af4d-118">To jest `year` Grupa przechwycona.</span><span class="sxs-lookup"><span data-stu-id="6af4d-118">This is the `year` captured group.</span></span>|  
|`\b`|<span data-ttu-id="6af4d-119">Kończy dopasowanie na granicy wyrazu.</span><span class="sxs-lookup"><span data-stu-id="6af4d-119">End the match at a word boundary.</span></span>|  
  
 <span data-ttu-id="6af4d-120">Wzorzec `${day}-${month}-${year}` definiuje ciąg zamienny, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="6af4d-120">The pattern `${day}-${month}-${year}` defines the replacement string as shown in the following table.</span></span>  
  
|<span data-ttu-id="6af4d-121">Wzorce</span><span class="sxs-lookup"><span data-stu-id="6af4d-121">Pattern</span></span>|<span data-ttu-id="6af4d-122">Opis</span><span class="sxs-lookup"><span data-stu-id="6af4d-122">Description</span></span>|  
|-------------|-----------------|  
|`$(day)`|<span data-ttu-id="6af4d-123">Dodaj ciąg przechwytywany przez `day` grupę przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="6af4d-123">Add the string captured by the `day` capturing group.</span></span>|  
|`-`|<span data-ttu-id="6af4d-124">Dodaj łącznik.</span><span class="sxs-lookup"><span data-stu-id="6af4d-124">Add a hyphen.</span></span>|  
|`$(month)`|<span data-ttu-id="6af4d-125">Dodaj ciąg przechwytywany przez `month` grupę przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="6af4d-125">Add the string captured by the `month` capturing group.</span></span>|  
|`-`|<span data-ttu-id="6af4d-126">Dodaj łącznik.</span><span class="sxs-lookup"><span data-stu-id="6af4d-126">Add a hyphen.</span></span>|  
|`$(year)`|<span data-ttu-id="6af4d-127">Dodaj ciąg przechwytywany przez `year` grupę przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="6af4d-127">Add the string captured by the `year` capturing group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6af4d-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6af4d-128">See also</span></span>

- [<span data-ttu-id="6af4d-129">Wyrażenia regularne .NET</span><span class="sxs-lookup"><span data-stu-id="6af4d-129">.NET Regular Expressions</span></span>](regular-expressions.md)
