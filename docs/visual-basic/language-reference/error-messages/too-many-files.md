---
title: Za dużo plików
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: cd168ce86569d2d7558e21a5b4cc5ef385b28313
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873555"
---
# <a name="too-many-files"></a><span data-ttu-id="d1c38-102">Za dużo plików</span><span class="sxs-lookup"><span data-stu-id="d1c38-102">Too many files</span></span>

<span data-ttu-id="d1c38-103">Więcej plików został utworzony w katalogu głównym niż zezwala na system operacyjny, lub więcej plików został otwarty niż liczba określona w ustawieniu **Files =** w pliku CONFIG.SYS.</span><span class="sxs-lookup"><span data-stu-id="d1c38-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d1c38-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="d1c38-104">To correct this error</span></span>  
  
1. <span data-ttu-id="d1c38-105">Jeśli program otwiera, zamyka lub zapisuje pliki w katalogu głównym, należy zmienić program tak, aby korzystał z podkatalogu.</span><span class="sxs-lookup"><span data-stu-id="d1c38-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="d1c38-106">Zwiększ liczbę plików określoną w ustawieniach **plików =** w pliku CONFIG.SYS i uruchom ponownie komputer.</span><span class="sxs-lookup"><span data-stu-id="d1c38-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c38-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d1c38-107">See also</span></span>

- [<span data-ttu-id="d1c38-108">Typy błędów</span><span class="sxs-lookup"><span data-stu-id="d1c38-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
