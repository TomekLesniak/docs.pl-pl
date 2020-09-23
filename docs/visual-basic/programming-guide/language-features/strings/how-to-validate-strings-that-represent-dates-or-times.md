---
title: 'Porady: Sprawdzanie poprawności ciągów reprezentujących daty lub godziny'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: f3654894e274404410179dab04422e20f6040440
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072603"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="34299-102">Porady: Sprawdzanie poprawności ciągów reprezentujących daty lub godziny (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34299-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>

<span data-ttu-id="34299-103">Poniższy przykład kodu ustawia `Boolean` wartość wskazującą, czy ciąg reprezentuje prawidłową datę lub godzinę.</span><span class="sxs-lookup"><span data-stu-id="34299-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34299-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="34299-104">Example</span></span>  

 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="34299-105">Kompiluj kod</span><span class="sxs-lookup"><span data-stu-id="34299-105">Compile the code</span></span>  

 <span data-ttu-id="34299-106">Zamień `("01/01/03")` i `"9:30 PM"` datę i godzinę, którą chcesz zweryfikować.</span><span class="sxs-lookup"><span data-stu-id="34299-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="34299-107">Można zastąpić ciąg innym zakodowanym ciągiem, ze `String` zmienną lub metodą zwracającą ciąg, na przykład `InputBox` .</span><span class="sxs-lookup"><span data-stu-id="34299-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="34299-108">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="34299-108">Robust Programming</span></span>  

 <span data-ttu-id="34299-109">Użyj tej metody, aby sprawdzić poprawność ciągu przed próbą przekonwertowania `String` na `DateTime` zmienną.</span><span class="sxs-lookup"><span data-stu-id="34299-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="34299-110">Sprawdzając najpierw datę lub godzinę, można uniknąć generowania wyjątku w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="34299-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34299-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="34299-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="34299-112">Sprawdzanie poprawności ciągów w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="34299-112">Validating Strings in Visual Basic</span></span>](validating-strings.md)
