---
title: ISymUnmanagedReader::ReplaceSymbolStore — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
ms.openlocfilehash: 3fa94094ad066496cc8a1fc4dd2ccb0ee16b5aac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675844"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="0eb41-102">ISymUnmanagedReader::ReplaceSymbolStore — Metoda</span><span class="sxs-lookup"><span data-stu-id="0eb41-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>

<span data-ttu-id="0eb41-103">Zamienia istniejący magazyn symboli na magazyn symboli różnicowych.</span><span class="sxs-lookup"><span data-stu-id="0eb41-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="0eb41-104">Ta metoda jest podobna do metody [UpdateSymbolStore —](isymunmanagedreader-updatesymbolstore-method.md) , z tą różnicą, że dana różnicowa działa jako kompletne zastąpienie, a nie aktualizacja.</span><span class="sxs-lookup"><span data-stu-id="0eb41-104">This method is similar to the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0eb41-105">Należy określić tylko jeden z `filename` `pIStream` parametrów lub, ale nie oba.</span><span class="sxs-lookup"><span data-stu-id="0eb41-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="0eb41-106">Jeśli `filename` jest określony, magazyn symboli zostanie zaktualizowany przy użyciu symboli w tym pliku.</span><span class="sxs-lookup"><span data-stu-id="0eb41-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="0eb41-107">Jeśli `pIStream` jest określony, magazyn zostanie zaktualizowany o dane z <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="0eb41-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eb41-108">Składnia</span><span class="sxs-lookup"><span data-stu-id="0eb41-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eb41-109">Parametry</span><span class="sxs-lookup"><span data-stu-id="0eb41-109">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="0eb41-110">podczas Nazwa pliku zawierającego magazyn symboli.</span><span class="sxs-lookup"><span data-stu-id="0eb41-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="0eb41-111">podczas Strumień pliku używany jako alternatywa dla `filename` parametru.</span><span class="sxs-lookup"><span data-stu-id="0eb41-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0eb41-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0eb41-112">Return Value</span></span>  

 <span data-ttu-id="0eb41-113">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="0eb41-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eb41-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0eb41-114">Requirements</span></span>  

 <span data-ttu-id="0eb41-115">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0eb41-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb41-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0eb41-116">See also</span></span>

- [<span data-ttu-id="0eb41-117">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0eb41-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
