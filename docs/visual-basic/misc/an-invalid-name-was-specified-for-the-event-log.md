---
title: Określono nieprawidłową nazwę dziennika zdarzeń
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 36e2bc91a671a22e808d0e30e292471729b1e50b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083881"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="23ecf-102">Określono nieprawidłową nazwę dziennika zdarzeń</span><span class="sxs-lookup"><span data-stu-id="23ecf-102">An invalid name was specified for the event log</span></span>

<span data-ttu-id="23ecf-103">Określono nieprawidłową nazwę dziennika zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="23ecf-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="23ecf-104">Zwykle jest to wynik nieprawidłowych znaków w nazwie, pustej nazwie pliku lub nazwy pliku, która jest zbyt długa.</span><span class="sxs-lookup"><span data-stu-id="23ecf-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="23ecf-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="23ecf-105">To correct this error</span></span>  
  
- <span data-ttu-id="23ecf-106">Jeśli określona nazwa jest dłuższa niż osiem znaków, upewnij się, że nie występują konflikty z nazwami innych dzienników zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="23ecf-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="23ecf-107">Podczas ustalania, czy nazwa jest unikatowa, oceniane są tylko pierwsze osiem znaków.</span><span class="sxs-lookup"><span data-stu-id="23ecf-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
- <span data-ttu-id="23ecf-108">W przypadku podawania ścieżki upewnij się, że została ona prawidłowo przeanalizowana.</span><span class="sxs-lookup"><span data-stu-id="23ecf-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
- <span data-ttu-id="23ecf-109">Sprawdź, czy nazwa nie zawiera nieprawidłowych znaków.</span><span class="sxs-lookup"><span data-stu-id="23ecf-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="23ecf-110">Znaki, których nie można użyć w nazwie pliku, obejmują,,,,, `<` `>` `:` `"` `/` `\` i `|` .</span><span class="sxs-lookup"><span data-stu-id="23ecf-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ecf-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="23ecf-111">See also</span></span>

- [<span data-ttu-id="23ecf-112">Instrukcje: Analizowanie ścieżek plików</span><span class="sxs-lookup"><span data-stu-id="23ecf-112">How to: Parse File Paths</span></span>](../developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [<span data-ttu-id="23ecf-113">Instrukcje: Zmienianie nazwy pliku</span><span class="sxs-lookup"><span data-stu-id="23ecf-113">How to: Rename a File</span></span>](../developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
