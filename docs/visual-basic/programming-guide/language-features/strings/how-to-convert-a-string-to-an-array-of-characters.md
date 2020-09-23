---
title: 'Porady: konwertowanie ciągu do tablicy znaków'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: e1f634fcdb23f16e794449f8fe7b53c451c8c5b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059174"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="5852b-102">Porady: konwertowanie ciągu do tablicy znaków w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5852b-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>

<span data-ttu-id="5852b-103">Czasami warto mieć dane dotyczące znaków w ciągu i położenia tych znaków w ciągu, np. podczas analizowania ciągu.</span><span class="sxs-lookup"><span data-stu-id="5852b-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="5852b-104">Ten przykład pokazuje, jak można uzyskać tablicę znaków w ciągu, wywołując <xref:System.String.ToCharArray%2A> metodę ciągu.</span><span class="sxs-lookup"><span data-stu-id="5852b-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5852b-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="5852b-105">Example</span></span>  

 <span data-ttu-id="5852b-106">W tym przykładzie pokazano, jak podzielić ciąg na `Char` tablicę i jak podzielić ciąg na `String` tablicę znaków tekstu Unicode.</span><span class="sxs-lookup"><span data-stu-id="5852b-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="5852b-107">Przyczyną tego rozróżnienia jest to, że znaki tekstowe Unicode mogą składać się z co najmniej dwóch `Char` znaków (takich jak para zastępcza lub sekwencja znaków łączących).</span><span class="sxs-lookup"><span data-stu-id="5852b-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="5852b-108">Aby uzyskać więcej informacji, zobacz <xref:System.Globalization.TextElementEnumerator> i [standard Unicode](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="5852b-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="5852b-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="5852b-109">Example</span></span>  

 <span data-ttu-id="5852b-110">Trudno jest podzielić ciąg na znaki tekstowe Unicode, ale jest to konieczne, jeśli potrzebujesz informacji na temat wizualnej reprezentacji ciągu.</span><span class="sxs-lookup"><span data-stu-id="5852b-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="5852b-111">W tym przykładzie używa <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> metody, aby uzyskać informacje o znakach tekstowych Unicode, które tworzą ciąg.</span><span class="sxs-lookup"><span data-stu-id="5852b-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="5852b-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5852b-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="5852b-113">Porady: dostęp do znaków w ciągach</span><span class="sxs-lookup"><span data-stu-id="5852b-113">How to: Access Characters in Strings</span></span>](how-to-access-characters-in-strings.md)
- [<span data-ttu-id="5852b-114">Konwertowanie pomiędzy ciągami a innymi typami danych w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5852b-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="5852b-115">Ciągi</span><span class="sxs-lookup"><span data-stu-id="5852b-115">Strings</span></span>](index.md)
