---
title: ISymUnmanagedWriter::DefineParameter — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
ms.openlocfilehash: c5e36443295395997303cb94202f534a83d086f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677872"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="80818-102">ISymUnmanagedWriter::DefineParameter — Metoda</span><span class="sxs-lookup"><span data-stu-id="80818-102">ISymUnmanagedWriter::DefineParameter Method</span></span>

<span data-ttu-id="80818-103">Definiuje pojedynczy parametr w bieżącej metodzie.</span><span class="sxs-lookup"><span data-stu-id="80818-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="80818-104">Typ parametru jest pobierany z pozycji parametru (Sequence) w podpisie metody.</span><span class="sxs-lookup"><span data-stu-id="80818-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="80818-105">Jeśli parametry są zdefiniowane w metadanych dla danej metody, nie trzeba ich definiować ponownie przy użyciu tej metody.</span><span class="sxs-lookup"><span data-stu-id="80818-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="80818-106">Czytelnicy symboli muszą sprawdzić normalne metadane parametrów przed sprawdzeniem magazynu symboli.</span><span class="sxs-lookup"><span data-stu-id="80818-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80818-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="80818-107">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80818-108">Parametry</span><span class="sxs-lookup"><span data-stu-id="80818-108">Parameters</span></span>  

 `name`  
 <span data-ttu-id="80818-109">podczas Nazwa parametru.</span><span class="sxs-lookup"><span data-stu-id="80818-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="80818-110">podczas Atrybuty parametru.</span><span class="sxs-lookup"><span data-stu-id="80818-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="80818-111">podczas Sygnatura parametru.</span><span class="sxs-lookup"><span data-stu-id="80818-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="80818-112">podczas Typ adresu.</span><span class="sxs-lookup"><span data-stu-id="80818-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="80818-113">podczas Pierwszy adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="80818-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="80818-114">podczas Drugi adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="80818-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="80818-115">podczas Trzeci adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="80818-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80818-116">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="80818-116">Return Value</span></span>  

 <span data-ttu-id="80818-117">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="80818-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80818-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="80818-118">Requirements</span></span>  

 <span data-ttu-id="80818-119">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="80818-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80818-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="80818-120">See also</span></span>

- [<span data-ttu-id="80818-121">ISymUnmanagedWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="80818-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
