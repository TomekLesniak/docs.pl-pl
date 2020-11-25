---
title: ISymUnmanagedWriter4 — Interfejs
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: c2b57897e4f0e8b23337302f344065d79677e0c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725810"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="b6b2e-102">ISymUnmanagedWriter4 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b6b2e-102">ISymUnmanagedWriter4 Interface</span></span>

<span data-ttu-id="b6b2e-103">Interfejs ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="b6b2e-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b2e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b6b2e-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="b6b2e-105">Metody</span><span class="sxs-lookup"><span data-stu-id="b6b2e-105">Methods</span></span>  

 <span data-ttu-id="b6b2e-106">Ten interfejs zawiera następujące metody:</span><span class="sxs-lookup"><span data-stu-id="b6b2e-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b6b2e-107">Metoda</span><span class="sxs-lookup"><span data-stu-id="b6b2e-107">Method</span></span>|<span data-ttu-id="b6b2e-108">Opis</span><span class="sxs-lookup"><span data-stu-id="b6b2e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6b2e-109">GetDebugInfoWithPadding, metoda</span><span class="sxs-lookup"><span data-stu-id="b6b2e-109">GetDebugInfoWithPadding Method</span></span>](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="b6b2e-110">Działa tak samo jak [Metoda GetDebugInfo —](isymunmanagedwriter-getdebuginfo-method.md) , z tą różnicą, że ciąg ścieżki jest dopełniany zerami po zamykającym znaku null, aby dane ciągu miały stały rozmiar `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="b6b2e-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="b6b2e-111">Uzupełnienie jest udzielane tylko wtedy, gdy sama długość ciągu ścieżki jest mniejsza niż `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="b6b2e-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="b6b2e-112">Ułatwia to pisanie narzędzi, które różnicuje pliki PE.</span><span class="sxs-lookup"><span data-stu-id="b6b2e-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6b2e-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b6b2e-113">Requirements</span></span>  

 <span data-ttu-id="b6b2e-114">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b6b2e-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b2e-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b6b2e-115">See also</span></span>

- [<span data-ttu-id="b6b2e-116">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="b6b2e-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="b6b2e-117">ISymUnmanagedWriter3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b6b2e-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
