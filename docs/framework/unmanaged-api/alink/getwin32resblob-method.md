---
title: GetWin32ResBlob — Metoda
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: 03f6c97b4a5bbbdc0aeaf7b3f07277e66d7d0e9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684515"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="b3be7-102">GetWin32ResBlob — Metoda</span><span class="sxs-lookup"><span data-stu-id="b3be7-102">GetWin32ResBlob Method</span></span>

<span data-ttu-id="b3be7-103">Pobiera obiekt BLOB zasobów Win32.</span><span class="sxs-lookup"><span data-stu-id="b3be7-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="b3be7-104">Wywołaj tę metodę po ustawieniu opcji zestawu.</span><span class="sxs-lookup"><span data-stu-id="b3be7-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3be7-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b3be7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3be7-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="b3be7-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="b3be7-107">Identyfikator zestawu.</span><span class="sxs-lookup"><span data-stu-id="b3be7-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b3be7-108">Token pliku używany do pobierania nazwy pliku do użycia podczas konstruowania zasobu wersji Win32</span><span class="sxs-lookup"><span data-stu-id="b3be7-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="b3be7-109">PRAWDA, jeśli plik jest biblioteką DLL, wartość false dla pliku EXE.</span><span class="sxs-lookup"><span data-stu-id="b3be7-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="b3be7-110">Opcjonalna ikona do wstawienia do obiektu BLOB zasobu.</span><span class="sxs-lookup"><span data-stu-id="b3be7-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="b3be7-111">Odbiera obiekt BLOB zasobu.</span><span class="sxs-lookup"><span data-stu-id="b3be7-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="b3be7-112">Odbiera rozmiar obiektu BLOB.</span><span class="sxs-lookup"><span data-stu-id="b3be7-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3be7-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b3be7-113">Return Value</span></span>  

 <span data-ttu-id="b3be7-114">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b3be7-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3be7-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b3be7-115">Requirements</span></span>  

 <span data-ttu-id="b3be7-116">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="b3be7-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3be7-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b3be7-117">See also</span></span>

- [<span data-ttu-id="b3be7-118">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b3be7-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b3be7-119">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b3be7-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b3be7-120">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="b3be7-120">ALink API</span></span>](index.md)
