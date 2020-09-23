---
title: 'Porady: tworzenie ciągu z tablicy wartości znaków'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 08ad2f1c9455853e92533a7f00726c73b6adb87e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071160"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="c423d-102">Porady: tworzenie ciągu z tablicy wartości znaków (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c423d-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>

<span data-ttu-id="c423d-103">Ten przykład tworzy ciąg "abcd" z pojedynczych znaków.</span><span class="sxs-lookup"><span data-stu-id="c423d-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c423d-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="c423d-104">Example</span></span>  

 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="c423d-105">Kompiluj kod</span><span class="sxs-lookup"><span data-stu-id="c423d-105">Compile the code</span></span>  

 <span data-ttu-id="c423d-106">Ta metoda nie ma specjalnych wymagań.</span><span class="sxs-lookup"><span data-stu-id="c423d-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="c423d-107">Składnia `"a"c` , w której pojedynczy `c` znak w cudzysłowie jest używany do tworzenia literału znakowego.</span><span class="sxs-lookup"><span data-stu-id="c423d-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c423d-108">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="c423d-108">Robust Programming</span></span>  

 <span data-ttu-id="c423d-109">Znaki null (równoważne `Chr(0)` ) w ciągu powodują nieoczekiwane wyniki przy użyciu ciągu.</span><span class="sxs-lookup"><span data-stu-id="c423d-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="c423d-110">Znak null zostanie dołączony do ciągu, ale znaki po znaku null nie będą wyświetlane w niektórych sytuacjach.</span><span class="sxs-lookup"><span data-stu-id="c423d-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c423d-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c423d-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="c423d-112">Char, typ danych</span><span class="sxs-lookup"><span data-stu-id="c423d-112">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="c423d-113">Typy danych</span><span class="sxs-lookup"><span data-stu-id="c423d-113">Data Types</span></span>](../data-types/index.md)
