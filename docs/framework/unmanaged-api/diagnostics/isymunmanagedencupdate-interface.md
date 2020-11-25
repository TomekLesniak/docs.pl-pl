---
title: ISymUnmanagedENCUpdate — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: 5e3c2ecd1bdd5c1181223c7500eb7473e20fa5d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731348"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="f6063-102">ISymUnmanagedENCUpdate — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6063-102">ISymUnmanagedENCUpdate Interface</span></span>

<span data-ttu-id="f6063-103">Udostępnia funkcje funkcji Edytuj i Kontynuuj.</span><span class="sxs-lookup"><span data-stu-id="f6063-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6063-104">Metody</span><span class="sxs-lookup"><span data-stu-id="f6063-104">Methods</span></span>  
  
|<span data-ttu-id="f6063-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="f6063-105">Method</span></span>|<span data-ttu-id="f6063-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f6063-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6063-107">GetLocalVariableCount, metoda</span><span class="sxs-lookup"><span data-stu-id="f6063-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="f6063-108">Pobiera liczbę zmiennych lokalnych.</span><span class="sxs-lookup"><span data-stu-id="f6063-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="f6063-109">GetLocalVariables, metoda</span><span class="sxs-lookup"><span data-stu-id="f6063-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="f6063-110">Pobiera zmienne lokalne.</span><span class="sxs-lookup"><span data-stu-id="f6063-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="f6063-111">InitializeForEnc, metoda</span><span class="sxs-lookup"><span data-stu-id="f6063-111">InitializeForEnc Method</span></span>](isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="f6063-112">Umożliwia obliczenia granic metod przed pierwszym wywołaniem metody [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 —](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f6063-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="f6063-113">UpdateMethodLines, metoda</span><span class="sxs-lookup"><span data-stu-id="f6063-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="f6063-114">Umożliwia aktualizowanie informacji o wierszu dla metody, która nie została ponownie skompilowana, ale których linie nie zostały przesunięte niezależnie.</span><span class="sxs-lookup"><span data-stu-id="f6063-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="f6063-115">Różnicowa dla każdej instrukcji jest dozwolony.</span><span class="sxs-lookup"><span data-stu-id="f6063-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="f6063-116">UpdateSymbolStore2, metoda</span><span class="sxs-lookup"><span data-stu-id="f6063-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="f6063-117">Pozwala kompilatorowi pominąć funkcje, które nie zostały zmodyfikowane ze strumienia bazy danych programu (PDB), pod warunkiem, że informacje o wierszu spełniają wymagania.</span><span class="sxs-lookup"><span data-stu-id="f6063-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="f6063-118">Informacje o prawidłowych wierszach można określić ze starymi informacjami o wierszu PDB i jedną różnicą dla wszystkich wierszy w funkcji.</span><span class="sxs-lookup"><span data-stu-id="f6063-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6063-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f6063-119">Requirements</span></span>  

 <span data-ttu-id="f6063-120">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f6063-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6063-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f6063-121">See also</span></span>

- [<span data-ttu-id="f6063-122">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="f6063-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
