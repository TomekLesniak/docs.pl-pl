---
title: TextFieldParser nie obsługuje tokenów komentarzy zawierających odstępy
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 825f999f8eab3563dd77039ef19ae5e329bb4240
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078505"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a><span data-ttu-id="1d5bb-102">TextFieldParser nie obsługuje tokenów komentarzy zawierających odstępy</span><span class="sxs-lookup"><span data-stu-id="1d5bb-102">TextFieldParser does not support comment tokens that contain white space</span></span>

<span data-ttu-id="1d5bb-103">Podano token komentarza zawierający biały znak.</span><span class="sxs-lookup"><span data-stu-id="1d5bb-103">A comment token that contains white space has been supplied.</span></span> <span data-ttu-id="1d5bb-104">`TextFieldParser`Program nie obsługuje tokenów komentarzy zawierających biały znak, chyba że odstęp występuje na początku tokenu.</span><span class="sxs-lookup"><span data-stu-id="1d5bb-104">The `TextFieldParser` does not support comment tokens that contain white space unless the white space occurs at the beginning of the token.</span></span> <span data-ttu-id="1d5bb-105">Białe miejsce występujące na początku tokenu jest ignorowane.</span><span class="sxs-lookup"><span data-stu-id="1d5bb-105">White space occurring at the beginning of a token is ignored.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1d5bb-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="1d5bb-106">To correct this error</span></span>  
  
- <span data-ttu-id="1d5bb-107">Podaj poprawny token komentarza.</span><span class="sxs-lookup"><span data-stu-id="1d5bb-107">Supply a correct comment token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d5bb-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1d5bb-108">See also</span></span>

- [<span data-ttu-id="1d5bb-109">TextFieldParser. CommentTokens — Właściwość</span><span class="sxs-lookup"><span data-stu-id="1d5bb-109">TextFieldParser.CommentTokens Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [<span data-ttu-id="1d5bb-110">Analizowanie plików tekstowych za pomocą obiektu TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="1d5bb-110">Parsing Text Files with the TextFieldParser Object</span></span>](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="1d5bb-111">TextFieldParser — Obiekt</span><span class="sxs-lookup"><span data-stu-id="1d5bb-111">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
