---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: eb174d12731d7f1bc78f4d709cf043daf2346bd2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269798"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="eb6b6-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="eb6b6-102">BinaryMessageEncodingBindingElement</span></span>

<span data-ttu-id="eb6b6-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="eb6b6-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb6b6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="eb6b6-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eb6b6-105">Metody</span><span class="sxs-lookup"><span data-stu-id="eb6b6-105">Methods</span></span>  

 <span data-ttu-id="eb6b6-106">Klasa BinaryMessageEncodingBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="eb6b6-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eb6b6-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="eb6b6-107">Properties</span></span>  

 <span data-ttu-id="eb6b6-108">Klasa BinaryMessageEncodingBindingElement ma następujące właściwości.</span><span class="sxs-lookup"><span data-stu-id="eb6b6-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="eb6b6-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="eb6b6-109">MaxReadPoolSize</span></span>  

 <span data-ttu-id="eb6b6-110">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="eb6b6-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb6b6-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="eb6b6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb6b6-112">Liczba całkowita, która określa, ile komunikatów można jednocześnie odczytać bez przydziału nowych czytników.</span><span class="sxs-lookup"><span data-stu-id="eb6b6-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="eb6b6-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="eb6b6-113">MaxSessionSize</span></span>  

 <span data-ttu-id="eb6b6-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="eb6b6-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb6b6-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="eb6b6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb6b6-116">Wartość określająca wyrażony w bajtach rozmiar buforu używany do kodowania.</span><span class="sxs-lookup"><span data-stu-id="eb6b6-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="eb6b6-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="eb6b6-117">MaxWritePoolSize</span></span>  

 <span data-ttu-id="eb6b6-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="eb6b6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb6b6-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="eb6b6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb6b6-120">Liczba całkowita, która określa, ile komunikatów można jednocześnie wysłać bez przydziału nowych modułów zapisujących.</span><span class="sxs-lookup"><span data-stu-id="eb6b6-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="eb6b6-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="eb6b6-121">ReaderQuotas</span></span>  

 <span data-ttu-id="eb6b6-122">Typ danych: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="eb6b6-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="eb6b6-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="eb6b6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb6b6-124">Przydziały czytelników.</span><span class="sxs-lookup"><span data-stu-id="eb6b6-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb6b6-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="eb6b6-125">Requirements</span></span>  
  
|<span data-ttu-id="eb6b6-126">PLIK</span><span class="sxs-lookup"><span data-stu-id="eb6b6-126">MOF</span></span>|<span data-ttu-id="eb6b6-127">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="eb6b6-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eb6b6-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="eb6b6-128">Namespace</span></span>|<span data-ttu-id="eb6b6-129">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="eb6b6-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb6b6-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eb6b6-130">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
