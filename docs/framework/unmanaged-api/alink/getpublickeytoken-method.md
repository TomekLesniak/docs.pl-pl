---
title: GetPublicKeyToken — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
ms.openlocfilehash: e41be6407076a2609a83a5be3b0c42d28914ec38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720345"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="f2f1c-102">GetPublicKeyToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="f2f1c-102">GetPublicKeyToken Method</span></span>

<span data-ttu-id="f2f1c-103">Pobiera token klucza publicznego dla danego keyfile lub kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f1c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f2f1c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2f1c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f2f1c-105">Parameters</span></span>  

 `pszKeyFile`  
 <span data-ttu-id="f2f1c-106">Nazwa pliku klucza.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="f2f1c-107">Nazwa kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="f2f1c-108">Adres, pod którym ma być przechowywany token klucza.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="f2f1c-109">Określa rozmiar buforu wskazywanego przez `pvPublicKeyToken` .</span><span class="sxs-lookup"><span data-stu-id="f2f1c-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="f2f1c-110">Po powrocie, zawiera rzeczywistą liczbę użytych bajtów.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2f1c-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f2f1c-111">Return Value</span></span>  

 <span data-ttu-id="f2f1c-112">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f1c-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f2f1c-113">Requirements</span></span>  

 <span data-ttu-id="f2f1c-114">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="f2f1c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f1c-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f2f1c-115">See also</span></span>

- [<span data-ttu-id="f2f1c-116">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f2f1c-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f2f1c-117">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f2f1c-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f2f1c-118">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="f2f1c-118">ALink API</span></span>](index.md)
