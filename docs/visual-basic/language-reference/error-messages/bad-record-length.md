---
title: Zła długość rekordu
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 6967015572b2567f52697f7ddcb1ff594013a2c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869257"
---
# <a name="bad-record-length"></a><span data-ttu-id="1cf49-102">Zła długość rekordu</span><span class="sxs-lookup"><span data-stu-id="1cf49-102">Bad record length</span></span>

<span data-ttu-id="1cf49-103">Wśród możliwych przyczyn tego błędu są:</span><span class="sxs-lookup"><span data-stu-id="1cf49-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="1cf49-104">Zmienna rekordu określona w `FileGet` `FileGetObject` instrukcji,, `FilePut` lub `FilePutObject` jest inna niż długość określona w odpowiedniej `FileOpen` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="1cf49-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="1cf49-105">Zmienna w `FilePut` `FilePutObject` instrukcji or ma lub zawiera ciąg o zmiennej długości.</span><span class="sxs-lookup"><span data-stu-id="1cf49-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="1cf49-106">Zmienna w `FilePut` lub `FilePutObject` jest lub zawiera `Variant` Typ.</span><span class="sxs-lookup"><span data-stu-id="1cf49-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1cf49-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="1cf49-107">To correct this error</span></span>  
  
1. <span data-ttu-id="1cf49-108">Upewnij się, że suma rozmiarów zmiennych o stałej długości w typie zdefiniowanym przez użytkownika definiująca typ zmiennej rekordu jest taka sama jak wartość określona w `FileOpen` `Len` klauzuli instrukcji.</span><span class="sxs-lookup"><span data-stu-id="1cf49-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="1cf49-109">Jeśli zmienna w `FilePut` `FilePutObject` instrukcji or ma lub zawiera ciąg o zmiennej długości, upewnij się, że ciąg o zmiennej długości ma co najmniej 2 znaki krótsze niż długość rekordu określona w `Len` klauzuli `FileOpen` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="1cf49-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="1cf49-110">Jeśli zmienna w lub lub `FilePut` `FilePutObject` jest lub zawiera, `Variant` upewnij się, że ciąg o zmiennej długości występuje co najmniej 4 bajty krótszy niż długość rekordu określona w `Len` klauzuli `FileOpen` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="1cf49-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cf49-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1cf49-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
