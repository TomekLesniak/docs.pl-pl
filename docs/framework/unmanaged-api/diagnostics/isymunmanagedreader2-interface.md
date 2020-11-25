---
title: ISymUnmanagedReader2 — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709079"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="57743-102">ISymUnmanagedReader2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="57743-102">ISymUnmanagedReader2 Interface</span></span>

<span data-ttu-id="57743-103">Reprezentuje czytnik symboli, który zapewnia dostęp do dokumentów, metod i zmiennych w magazynie symboli.</span><span class="sxs-lookup"><span data-stu-id="57743-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="57743-104">Ten interfejs rozszerza interfejs [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="57743-104">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57743-105">Metody</span><span class="sxs-lookup"><span data-stu-id="57743-105">Methods</span></span>  
  
|<span data-ttu-id="57743-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="57743-106">Method</span></span>|<span data-ttu-id="57743-107">Opis</span><span class="sxs-lookup"><span data-stu-id="57743-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57743-108">GetMethodByVersionPreRemap, metoda</span><span class="sxs-lookup"><span data-stu-id="57743-108">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="57743-109">Pobierz metodę czytnika symboli, używając tokenu metody oraz numeru wersji Edit-and-Continue.</span><span class="sxs-lookup"><span data-stu-id="57743-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="57743-110">GetMethodsInDocument, metoda</span><span class="sxs-lookup"><span data-stu-id="57743-110">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="57743-111">Pobiera każdą metodę, która zawiera informacje o wierszu w podanym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="57743-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="57743-112">GetSymAttributePreRemap, metoda</span><span class="sxs-lookup"><span data-stu-id="57743-112">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="57743-113">Pobiera atrybut niestandardowy na podstawie jego nazwy.</span><span class="sxs-lookup"><span data-stu-id="57743-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57743-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="57743-114">Requirements</span></span>  

 <span data-ttu-id="57743-115">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="57743-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57743-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="57743-116">See also</span></span>

- [<span data-ttu-id="57743-117">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="57743-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="57743-118">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="57743-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
