---
title: ISymUnmanagedWriter3 — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: dfc2e39a6a39e7386bd7358d422d5c6978ec42ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683293"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="50059-102">ISymUnmanagedWriter3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="50059-102">ISymUnmanagedWriter3 Interface</span></span>

<span data-ttu-id="50059-103">Reprezentuje moduł zapisujący symboli i zawiera metody definiowania dokumentów, punktów sekwencji, zakresów leksykalnych i zmiennych.</span><span class="sxs-lookup"><span data-stu-id="50059-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="50059-104">Ten interfejs rozszerza interfejs [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="50059-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50059-105">Metody</span><span class="sxs-lookup"><span data-stu-id="50059-105">Methods</span></span>  
  
|<span data-ttu-id="50059-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="50059-106">Method</span></span>|<span data-ttu-id="50059-107">Opis</span><span class="sxs-lookup"><span data-stu-id="50059-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50059-108">Commit — metoda</span><span class="sxs-lookup"><span data-stu-id="50059-108">Commit Method</span></span>](isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="50059-109">Zatwierdza zmiany zapisywane do strumienia.</span><span class="sxs-lookup"><span data-stu-id="50059-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="50059-110">OpenMethod2, metoda</span><span class="sxs-lookup"><span data-stu-id="50059-110">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="50059-111">Otwiera metodę i udostępnia jej rzeczywiste przesunięcie sekcji w obrazie.</span><span class="sxs-lookup"><span data-stu-id="50059-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50059-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="50059-112">Requirements</span></span>  

 <span data-ttu-id="50059-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="50059-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50059-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="50059-114">See also</span></span>

- [<span data-ttu-id="50059-115">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="50059-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="50059-116">ISymUnmanagedWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="50059-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="50059-117">ISymUnmanagedWriter2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="50059-117">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
