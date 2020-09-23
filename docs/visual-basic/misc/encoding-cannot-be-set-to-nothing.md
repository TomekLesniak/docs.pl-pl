---
title: Nie można ustawić wartości Nothing dla kodowania
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 0356098ca3fb41804ea396b0ff792cf2990b3340
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077543"
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="14e3c-102">Nie można ustawić wartości Nothing dla kodowania</span><span class="sxs-lookup"><span data-stu-id="14e3c-102">Encoding cannot be set to Nothing</span></span>

<span data-ttu-id="14e3c-103">Próba odczytu z pliku lub zapisu do niego nie powiodła się, ponieważ parametr został `encoding` ustawiony na `Nothing` wartość, ale wymaga prawidłowej wartości.</span><span class="sxs-lookup"><span data-stu-id="14e3c-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="14e3c-104"><xref:System.Text.Encoding> służy do określania kodowania, które ma być używane podczas zapisywania w pliku.</span><span class="sxs-lookup"><span data-stu-id="14e3c-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="14e3c-105">Domyślnym ustawieniem jest UTF-8.</span><span class="sxs-lookup"><span data-stu-id="14e3c-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14e3c-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="14e3c-106">To correct this error</span></span>  
  
- <span data-ttu-id="14e3c-107">Podaj prawidłową wartość `encoding` parametru.</span><span class="sxs-lookup"><span data-stu-id="14e3c-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e3c-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="14e3c-108">See also</span></span>

- [<span data-ttu-id="14e3c-109">Kodowanie pliku</span><span class="sxs-lookup"><span data-stu-id="14e3c-109">File Encodings</span></span>](../developing-apps/programming/drives-directories-files/file-encodings.md)
- [<span data-ttu-id="14e3c-110">Odczyt z plików</span><span class="sxs-lookup"><span data-stu-id="14e3c-110">Reading from Files</span></span>](../developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="14e3c-111">Zapisywanie w plikach</span><span class="sxs-lookup"><span data-stu-id="14e3c-111">Writing to Files</span></span>](../developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="14e3c-112">My. Computer. FileSystem. ReadAllText obiektu</span><span class="sxs-lookup"><span data-stu-id="14e3c-112">My.Computer.FileSystem.ReadAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [<span data-ttu-id="14e3c-113">My. Computer. FileSystem. WriteAllText —</span><span class="sxs-lookup"><span data-stu-id="14e3c-113">My.Computer.FileSystem.WriteAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
