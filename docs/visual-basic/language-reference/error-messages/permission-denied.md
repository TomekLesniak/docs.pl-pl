---
title: Odmowa uprawnień
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: 5ac585a86a783f36642545e368b1c2e694b89f62
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871166"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="2eced-102">Odmowa uprawnień (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2eced-102">Permission denied (Visual Basic)</span></span>

<span data-ttu-id="2eced-103">Podjęto próbę zapisu na dysku chronionym przed zapisem lub w celu uzyskania dostępu do zablokowanego pliku.</span><span class="sxs-lookup"><span data-stu-id="2eced-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2eced-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="2eced-104">To correct this error</span></span>  
  
1. <span data-ttu-id="2eced-105">Aby otworzyć plik chroniony przed zapisem, Zmień atrybut ochrona zapisu w pliku.</span><span class="sxs-lookup"><span data-stu-id="2eced-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="2eced-106">Upewnij się, że inny proces nie zablokował pliku i poczekaj na otwarcie pliku do momentu, aż inny proces zwolni go.</span><span class="sxs-lookup"><span data-stu-id="2eced-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="2eced-107">Aby uzyskać dostęp do rejestru, sprawdź, czy uprawnienia użytkownika obejmują ten typ dostępu do rejestru.</span><span class="sxs-lookup"><span data-stu-id="2eced-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eced-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2eced-108">See also</span></span>

- [<span data-ttu-id="2eced-109">Typy błędów</span><span class="sxs-lookup"><span data-stu-id="2eced-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
