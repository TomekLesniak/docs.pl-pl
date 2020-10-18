---
title: Instrukcje „Line” nie są już obsługiwane (Błąd kompilatora Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: f34095becf321c6cb4b316b6378a2da0107577ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162482"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a><span data-ttu-id="93c6f-102">BC30830: instrukcje "line" nie są już obsługiwane</span><span class="sxs-lookup"><span data-stu-id="93c6f-102">BC30830: 'Line' statements are no longer supported</span></span>

<span data-ttu-id="93c6f-103">Instrukcje liniowe nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="93c6f-103">Line statements are no longer supported.</span></span> <span data-ttu-id="93c6f-104">Funkcja we/wy plików jest dostępna, ponieważ `Microsoft.VisualBasic.FileSystem.LineInput` Funkcja graficzna jest dostępna jako `System.Drawing.Graphics.DrawLine` .</span><span class="sxs-lookup"><span data-stu-id="93c6f-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>

 <span data-ttu-id="93c6f-105">**Identyfikator błędu:** BC30830</span><span class="sxs-lookup"><span data-stu-id="93c6f-105">**Error ID:** BC30830</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="93c6f-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="93c6f-106">To correct this error</span></span>

- <span data-ttu-id="93c6f-107">W przypadku uzyskiwania dostępu do plików użyj `Microsoft.VisualBasic.FileSystem.LineInput` .</span><span class="sxs-lookup"><span data-stu-id="93c6f-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>

- <span data-ttu-id="93c6f-108">Jeśli wykonujesz grafikę, użyj `System.Drawing.Graphics.Drawline` .</span><span class="sxs-lookup"><span data-stu-id="93c6f-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>

## <a name="see-also"></a><span data-ttu-id="93c6f-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="93c6f-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="93c6f-110">Dostęp do plików za pomocą Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93c6f-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
