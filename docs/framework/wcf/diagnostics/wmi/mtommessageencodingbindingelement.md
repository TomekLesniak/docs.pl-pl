---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: b4d8503543c93d0112fc39e4b2dba5434bc56472
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237407"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="7ac4f-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="7ac4f-102">MtomMessageEncodingBindingElement</span></span>

<span data-ttu-id="7ac4f-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="7ac4f-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ac4f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7ac4f-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7ac4f-105">Metody</span><span class="sxs-lookup"><span data-stu-id="7ac4f-105">Methods</span></span>  

 <span data-ttu-id="7ac4f-106">Klasa MtomMessageEncodingBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="7ac4f-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7ac4f-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7ac4f-107">Properties</span></span>  

 <span data-ttu-id="7ac4f-108">Klasa MtomMessageEncodingBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="7ac4f-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="7ac4f-109">Encoding</span><span class="sxs-lookup"><span data-stu-id="7ac4f-109">Encoding</span></span>  

 <span data-ttu-id="7ac4f-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7ac4f-110">Data type: string</span></span>  
  
 <span data-ttu-id="7ac4f-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7ac4f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ac4f-112">Kodowanie zestawu znaków, które ma być używane do emitowania komunikatów w powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="7ac4f-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="7ac4f-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="7ac4f-113">MaxReadPoolSize</span></span>  

 <span data-ttu-id="7ac4f-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="7ac4f-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="7ac4f-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7ac4f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ac4f-116">Liczba całkowita, która określa, ile komunikatów można jednocześnie odczytać bez przydziału nowych czytników.</span><span class="sxs-lookup"><span data-stu-id="7ac4f-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="7ac4f-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="7ac4f-117">MaxWritePoolSize</span></span>  

 <span data-ttu-id="7ac4f-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="7ac4f-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="7ac4f-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7ac4f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ac4f-120">Liczba całkowita, która określa, ile komunikatów można jednocześnie wysłać bez przydziału nowych modułów zapisujących.</span><span class="sxs-lookup"><span data-stu-id="7ac4f-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="7ac4f-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="7ac4f-121">ReaderQuotas</span></span>  

 <span data-ttu-id="7ac4f-122">Typ danych: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="7ac4f-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="7ac4f-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7ac4f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ac4f-124">Przydziały czytelników.</span><span class="sxs-lookup"><span data-stu-id="7ac4f-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ac4f-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7ac4f-125">Requirements</span></span>  
  
|<span data-ttu-id="7ac4f-126">PLIK</span><span class="sxs-lookup"><span data-stu-id="7ac4f-126">MOF</span></span>|<span data-ttu-id="7ac4f-127">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="7ac4f-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7ac4f-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="7ac4f-128">Namespace</span></span>|<span data-ttu-id="7ac4f-129">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7ac4f-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ac4f-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7ac4f-130">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
