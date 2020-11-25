---
title: ISymUnmanagedBinder3 — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: 0cb0b91f2dca8203c37599400b3b61f84eb7d282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727318"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="ce2c9-102">ISymUnmanagedBinder3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ce2c9-102">ISymUnmanagedBinder3 Interface</span></span>

<span data-ttu-id="ce2c9-103">Rozszerza interfejs segregatora symboli.</span><span class="sxs-lookup"><span data-stu-id="ce2c9-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="ce2c9-104">Uzyskaj ten interfejs, wywołując `QueryInterface` obiekt, który implementuje `ISymUnmanagedBinder` interfejs.</span><span class="sxs-lookup"><span data-stu-id="ce2c9-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ce2c9-105">Jest to zagrożenie bezpieczeństwa, aby otworzyć plik bazy danych programu (PDB) z niezaufanego źródła.</span><span class="sxs-lookup"><span data-stu-id="ce2c9-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce2c9-106">Metody</span><span class="sxs-lookup"><span data-stu-id="ce2c9-106">Methods</span></span>  
  
|<span data-ttu-id="ce2c9-107">Metoda</span><span class="sxs-lookup"><span data-stu-id="ce2c9-107">Method</span></span>|<span data-ttu-id="ce2c9-108">Opis</span><span class="sxs-lookup"><span data-stu-id="ce2c9-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce2c9-109">GetReaderFromCallback, metoda</span><span class="sxs-lookup"><span data-stu-id="ce2c9-109">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="ce2c9-110">Zezwala użytkownikowi na implementowanie lub dostarczanie za pośrednictwem wywołania zwrotnego albo `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` uzyskanie informacji o katalogu debugowania z pamięci</span><span class="sxs-lookup"><span data-stu-id="ce2c9-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce2c9-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ce2c9-111">Requirements</span></span>  

 <span data-ttu-id="ce2c9-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ce2c9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2c9-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ce2c9-113">See also</span></span>

- [<span data-ttu-id="ce2c9-114">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="ce2c9-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ce2c9-115">ISymUnmanagedBinder — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ce2c9-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="ce2c9-116">ISymUnmanagedBinder2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ce2c9-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
