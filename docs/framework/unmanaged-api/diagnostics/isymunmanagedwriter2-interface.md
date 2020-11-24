---
title: ISymUnmanagedWriter2 — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: 6feb48b7c78dda64ba372e470b83ffb14f21f2f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683332"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="ded3b-102">ISymUnmanagedWriter2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ded3b-102">ISymUnmanagedWriter2 Interface</span></span>

<span data-ttu-id="ded3b-103">Reprezentuje moduł zapisujący symboli i zawiera metody definiowania dokumentów, punktów sekwencji, zakresów leksykalnych i zmiennych.</span><span class="sxs-lookup"><span data-stu-id="ded3b-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="ded3b-104">Ten interfejs rozszerza interfejs [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ded3b-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ded3b-105">Metody</span><span class="sxs-lookup"><span data-stu-id="ded3b-105">Methods</span></span>  
  
|<span data-ttu-id="ded3b-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="ded3b-106">Method</span></span>|<span data-ttu-id="ded3b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="ded3b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ded3b-108">DefineConstant2, metoda</span><span class="sxs-lookup"><span data-stu-id="ded3b-108">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="ded3b-109">Definiuje nazwę wartości stałej.</span><span class="sxs-lookup"><span data-stu-id="ded3b-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="ded3b-110">DefineGlobalVariable2, metoda</span><span class="sxs-lookup"><span data-stu-id="ded3b-110">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="ded3b-111">Definiuje pojedynczą zmienną globalną.</span><span class="sxs-lookup"><span data-stu-id="ded3b-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="ded3b-112">DefineLocalVariable2, metoda</span><span class="sxs-lookup"><span data-stu-id="ded3b-112">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="ded3b-113">Definiuje pojedynczą zmienną w bieżącym zakresie leksykalnym.</span><span class="sxs-lookup"><span data-stu-id="ded3b-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ded3b-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ded3b-114">Requirements</span></span>  

 <span data-ttu-id="ded3b-115">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ded3b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded3b-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ded3b-116">See also</span></span>

- [<span data-ttu-id="ded3b-117">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="ded3b-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ded3b-118">ISymUnmanagedWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ded3b-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ded3b-119">ISymUnmanagedWriter3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ded3b-119">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
