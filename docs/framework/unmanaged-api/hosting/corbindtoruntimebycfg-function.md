---
title: CorBindToRuntimeByCfg — Funkcja
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: d319382b577844a804c3e4562676491a15de5f63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673790"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="1d107-102">CorBindToRuntimeByCfg — Funkcja</span><span class="sxs-lookup"><span data-stu-id="1d107-102">CorBindToRuntimeByCfg Function</span></span>

<span data-ttu-id="1d107-103">Ładuje środowisko uruchomieniowe języka wspólnego (CLR) do procesu przy użyciu informacji o wersji, które są odczytywane z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="1d107-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="1d107-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1d107-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d107-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="1d107-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d107-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="1d107-106">Parameters</span></span>  

 `pCfgStream`  
 <span data-ttu-id="1d107-107">podczas Wskaźnik do `IStream` obiektu, który odczytuje plik XML.</span><span class="sxs-lookup"><span data-stu-id="1d107-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="1d107-108">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="1d107-108">[in] Reserved for future use.</span></span> <span data-ttu-id="1d107-109">Użyj 0 (zero) jako wartości.</span><span class="sxs-lookup"><span data-stu-id="1d107-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="1d107-110">podczas Wartość wyliczenia [STARTUP_FLAGS](startup-flags-enumeration.md) , która określa zachowanie uruchamiania środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="1d107-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="1d107-111">podczas `CLSID` Klasy coclass implementującej interfejs [ICorRuntimeHost](icorruntimehost-interface.md) lub [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1d107-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="1d107-112">Obsługiwane wartości to CLSID_CorRuntimeHost lub CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="1d107-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="1d107-113">podczas `IID` `ICorRuntimeHost` `ICLRRuntimeHost` Interfejs lub.</span><span class="sxs-lookup"><span data-stu-id="1d107-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="1d107-114">Obsługiwane wartości to IID_ICorRuntimeHost lub IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="1d107-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="1d107-115">określoną Wskaźnik do adresu zwracanego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="1d107-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d107-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1d107-116">Remarks</span></span>  

 <span data-ttu-id="1d107-117">Format pliku XML jest modelowany po standardowym pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1d107-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="1d107-118">Aby uzyskać więcej informacji na temat plików XML, zobacz [Schemat pliku konfiguracji](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="1d107-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d107-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1d107-119">Requirements</span></span>  

 <span data-ttu-id="1d107-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d107-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d107-121">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1d107-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d107-122">**Biblioteka:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d107-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d107-123">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d107-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d107-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1d107-124">See also</span></span>

- [<span data-ttu-id="1d107-125">CorBindToCurrentRuntime — Funkcja</span><span class="sxs-lookup"><span data-stu-id="1d107-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="1d107-126">CorBindToRuntime — Funkcja</span><span class="sxs-lookup"><span data-stu-id="1d107-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="1d107-127">CorBindToRuntimeEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="1d107-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="1d107-128">CorBindToRuntimeHost — Funkcja</span><span class="sxs-lookup"><span data-stu-id="1d107-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="1d107-129">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1d107-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="1d107-130">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="1d107-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
