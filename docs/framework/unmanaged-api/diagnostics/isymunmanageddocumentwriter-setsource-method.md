---
title: ISymUnmanagedDocumentWriter::SetSource — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
ms.openlocfilehash: 31475b08b569b925aab9cab869545f0912c4ecf8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691594"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="2d2c9-102">ISymUnmanagedDocumentWriter::SetSource — Metoda</span><span class="sxs-lookup"><span data-stu-id="2d2c9-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>

<span data-ttu-id="2d2c9-103">Ustawia osadzone źródło dla dokumentu, który jest zapisywany.</span><span class="sxs-lookup"><span data-stu-id="2d2c9-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d2c9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2d2c9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d2c9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2d2c9-105">Parameters</span></span>  

 `sourceSize`  
 <span data-ttu-id="2d2c9-106">podczas A `ULONG32` , który zawiera rozmiar `source` buforu.</span><span class="sxs-lookup"><span data-stu-id="2d2c9-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="2d2c9-107">podczas Bufor przechowujący osadzone źródło.</span><span class="sxs-lookup"><span data-stu-id="2d2c9-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d2c9-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2d2c9-108">Return Value</span></span>  

 <span data-ttu-id="2d2c9-109">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="2d2c9-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d2c9-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2d2c9-110">Requirements</span></span>  

 <span data-ttu-id="2d2c9-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2d2c9-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d2c9-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2d2c9-112">See also</span></span>

- [<span data-ttu-id="2d2c9-113">ISymUnmanagedDocumentWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2d2c9-113">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
