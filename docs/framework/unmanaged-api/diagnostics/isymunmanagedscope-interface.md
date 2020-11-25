---
title: ISymUnmanagedScope — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 9256342ad3a91e6770d6fd19d9d2f94fab267d3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725888"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="e87b8-102">ISymUnmanagedScope — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e87b8-102">ISymUnmanagedScope Interface</span></span>

<span data-ttu-id="e87b8-103">Reprezentuje zakres leksykalny w ramach metody.</span><span class="sxs-lookup"><span data-stu-id="e87b8-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e87b8-104">Metody</span><span class="sxs-lookup"><span data-stu-id="e87b8-104">Methods</span></span>  
  
|<span data-ttu-id="e87b8-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-105">Method</span></span>|<span data-ttu-id="e87b8-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e87b8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e87b8-107">GetChildren, metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="e87b8-108">Pobiera elementy podrzędne tego zakresu.</span><span class="sxs-lookup"><span data-stu-id="e87b8-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="e87b8-109">GetEndOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="e87b8-110">Pobiera przesunięcie końca dla tego zakresu.</span><span class="sxs-lookup"><span data-stu-id="e87b8-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="e87b8-111">GetLocalCount, metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="e87b8-112">Pobiera liczbę zmiennych lokalnych zdefiniowanych w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="e87b8-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="e87b8-113">GetLocals, metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="e87b8-114">Pobiera zmienne lokalne zdefiniowane w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="e87b8-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="e87b8-115">GetMethod, metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="e87b8-116">Pobiera metodę, która zawiera ten zakres.</span><span class="sxs-lookup"><span data-stu-id="e87b8-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="e87b8-117">GetNamespaces, metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="e87b8-118">Pobiera przestrzenie nazw, które są używane w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="e87b8-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="e87b8-119">GetParent, metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="e87b8-120">Pobiera zakres nadrzędny tego zakresu.</span><span class="sxs-lookup"><span data-stu-id="e87b8-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="e87b8-121">GetStartOffset, metoda</span><span class="sxs-lookup"><span data-stu-id="e87b8-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="e87b8-122">Pobiera przesunięcie początku dla tego zakresu.</span><span class="sxs-lookup"><span data-stu-id="e87b8-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e87b8-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e87b8-123">Requirements</span></span>  

 <span data-ttu-id="e87b8-124">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e87b8-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e87b8-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e87b8-125">See also</span></span>

- [<span data-ttu-id="e87b8-126">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="e87b8-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e87b8-127">ISymUnmanagedScope2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e87b8-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
