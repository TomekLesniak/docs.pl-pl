---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 551761af255681dd2c2dbb9e40b7103c95cd2e0a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267224"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="7d30d-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="7d30d-102">TextMessageEncodingBindingElement</span></span>

<span data-ttu-id="7d30d-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="7d30d-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d30d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7d30d-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7d30d-105">Metody</span><span class="sxs-lookup"><span data-stu-id="7d30d-105">Methods</span></span>  

 <span data-ttu-id="7d30d-106">Klasa TextMessageEncodingBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="7d30d-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7d30d-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="7d30d-107">Properties</span></span>  

 <span data-ttu-id="7d30d-108">Klasa TextMessageEncodingBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="7d30d-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="7d30d-109">Encoding</span><span class="sxs-lookup"><span data-stu-id="7d30d-109">Encoding</span></span>  

 <span data-ttu-id="7d30d-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="7d30d-110">Data type: string</span></span>  
  
 <span data-ttu-id="7d30d-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7d30d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d30d-112">Kodowanie zestawu znaków, które ma być używane do emitowania komunikatów w powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="7d30d-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="7d30d-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="7d30d-113">MaxReadPoolSize</span></span>  

 <span data-ttu-id="7d30d-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="7d30d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="7d30d-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7d30d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d30d-116">Liczba całkowita, która określa, ile komunikatów można jednocześnie odczytać bez przydziału nowych czytników.</span><span class="sxs-lookup"><span data-stu-id="7d30d-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="7d30d-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="7d30d-117">MaxWritePoolSize</span></span>  

 <span data-ttu-id="7d30d-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="7d30d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="7d30d-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7d30d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d30d-120">Liczba całkowita, która określa, ile komunikatów można jednocześnie wysłać bez przydziału nowych modułów zapisujących.</span><span class="sxs-lookup"><span data-stu-id="7d30d-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="7d30d-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="7d30d-121">ReaderQuotas</span></span>  

 <span data-ttu-id="7d30d-122">Typ danych: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="7d30d-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="7d30d-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="7d30d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d30d-124">Przydziały czytelników.</span><span class="sxs-lookup"><span data-stu-id="7d30d-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d30d-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7d30d-125">Requirements</span></span>  
  
|<span data-ttu-id="7d30d-126">PLIK</span><span class="sxs-lookup"><span data-stu-id="7d30d-126">MOF</span></span>|<span data-ttu-id="7d30d-127">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="7d30d-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7d30d-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="7d30d-128">Namespace</span></span>|<span data-ttu-id="7d30d-129">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7d30d-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d30d-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7d30d-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
