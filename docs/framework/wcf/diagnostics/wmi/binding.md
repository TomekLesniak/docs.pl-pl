---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: b72bd3903b7139c4adf2a8bd0ced6c34e7285640
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274299"
---
# <a name="binding"></a><span data-ttu-id="e593b-102">Wiązanie</span><span class="sxs-lookup"><span data-stu-id="e593b-102">Binding</span></span>

<span data-ttu-id="e593b-103">Powiązanie usługi WMI</span><span class="sxs-lookup"><span data-stu-id="e593b-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e593b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e593b-104">Syntax</span></span>  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e593b-105">Metody</span><span class="sxs-lookup"><span data-stu-id="e593b-105">Methods</span></span>  

 <span data-ttu-id="e593b-106">Klasa Binding nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="e593b-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e593b-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e593b-107">Properties</span></span>  

 <span data-ttu-id="e593b-108">Klasa powiązania ma następujące właściwości.</span><span class="sxs-lookup"><span data-stu-id="e593b-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="e593b-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="e593b-109">BindingElements</span></span>  

 <span data-ttu-id="e593b-110">Typ danych: tablica BindingElement</span><span class="sxs-lookup"><span data-stu-id="e593b-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="e593b-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e593b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e593b-112">Kolekcja elementów powiązania implementowanych przez powiązanie.</span><span class="sxs-lookup"><span data-stu-id="e593b-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="e593b-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="e593b-113">CloseTimeout</span></span>  

 <span data-ttu-id="e593b-114">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="e593b-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="e593b-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e593b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e593b-116">Przedział czasu podanego na zakończenie operacji zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="e593b-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="e593b-117">Nazwa</span><span class="sxs-lookup"><span data-stu-id="e593b-117">Name</span></span>  

 <span data-ttu-id="e593b-118">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="e593b-118">Data type: string</span></span>  
  
 <span data-ttu-id="e593b-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e593b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e593b-120">Nazwa powiązania.</span><span class="sxs-lookup"><span data-stu-id="e593b-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="e593b-121">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="e593b-121">Namespace</span></span>  

 <span data-ttu-id="e593b-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="e593b-122">Data type: string</span></span>  
  
 <span data-ttu-id="e593b-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e593b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e593b-124">Przestrzeń nazw XML powiązania.</span><span class="sxs-lookup"><span data-stu-id="e593b-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="e593b-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="e593b-125">OpenTimeout</span></span>  

 <span data-ttu-id="e593b-126">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="e593b-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="e593b-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e593b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e593b-128">Przedział czasu podanego na zakończenie operacji otwarcia.</span><span class="sxs-lookup"><span data-stu-id="e593b-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="e593b-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="e593b-129">ReceiveTimeout</span></span>  

 <span data-ttu-id="e593b-130">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="e593b-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="e593b-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e593b-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e593b-132">Przedział czasu podanego na zakończenie operacji odbioru.</span><span class="sxs-lookup"><span data-stu-id="e593b-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="e593b-133">Schemat</span><span class="sxs-lookup"><span data-stu-id="e593b-133">Scheme</span></span>  

 <span data-ttu-id="e593b-134">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="e593b-134">Data type: string</span></span>  
  
 <span data-ttu-id="e593b-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e593b-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e593b-136">Schemat transportu URI używany przez fabryki kanałów i odbiorników, które są tworzone przez powiązanie.</span><span class="sxs-lookup"><span data-stu-id="e593b-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="e593b-137">Właściwości SendTimeout</span><span class="sxs-lookup"><span data-stu-id="e593b-137">SendTimeout</span></span>  

 <span data-ttu-id="e593b-138">Typ danych: DateTime</span><span class="sxs-lookup"><span data-stu-id="e593b-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="e593b-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e593b-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e593b-140">Interwał przeznaczony na zakończenie operacji wysyłania.</span><span class="sxs-lookup"><span data-stu-id="e593b-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e593b-141">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e593b-141">Requirements</span></span>  
  
|<span data-ttu-id="e593b-142">PLIK</span><span class="sxs-lookup"><span data-stu-id="e593b-142">MOF</span></span>|<span data-ttu-id="e593b-143">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="e593b-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e593b-144">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="e593b-144">Namespace</span></span>|<span data-ttu-id="e593b-145">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e593b-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e593b-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e593b-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
