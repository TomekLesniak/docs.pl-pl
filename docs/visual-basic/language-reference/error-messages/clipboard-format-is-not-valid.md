---
title: Format schowka nie jest prawidłowy
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874583"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="96b75-102">Format schowka nie jest prawidłowy</span><span class="sxs-lookup"><span data-stu-id="96b75-102">Clipboard format is not valid</span></span>

<span data-ttu-id="96b75-103">Określony format Schowka jest niezgodny z uruchomioną metodą.</span><span class="sxs-lookup"><span data-stu-id="96b75-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="96b75-104">Wśród możliwych przyczyn tego błędu są:</span><span class="sxs-lookup"><span data-stu-id="96b75-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="96b75-105">Używanie schowka `GetText` lub `SetText` metody z innym formatem schowka niż `vbCFText` lub `vbCFLink` .</span><span class="sxs-lookup"><span data-stu-id="96b75-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="96b75-106">Używanie schowka `GetData` lub `SetData` metody z formatem schowka innym niż `vbCFBitmap` , `vbCFDIB` lub `vbCFMetafile` .</span><span class="sxs-lookup"><span data-stu-id="96b75-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="96b75-107">Używanie `GetData` metod lub z w `SetData` `DataObject` formacie Schowka w zakresie zarezerwowanym przez system Microsoft Windows dla zarejestrowanych formatów (&HC000-&HFFFF), gdy ten format schowka nie został zarejestrowany w systemie Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="96b75-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96b75-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="96b75-108">To correct this error</span></span>  
  
- <span data-ttu-id="96b75-109">Usuń nieprawidłowy format i określ prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="96b75-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b75-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96b75-110">See also</span></span>

- [<span data-ttu-id="96b75-111">Schowek: Dodawanie innych formatów</span><span class="sxs-lookup"><span data-stu-id="96b75-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
