---
title: Niestandardowe rekordy śledzenia
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: e0bbb9d57290b072d834f0b8bc0815dfe265e72a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543904"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="505de-102">Niestandardowe rekordy śledzenia</span><span class="sxs-lookup"><span data-stu-id="505de-102">Custom Tracking Records</span></span>

<span data-ttu-id="505de-103">W tym temacie pokazano, jak utworzyć niestandardowe rekordy śledzenia i wypełnić je danymi, które mają być emitowane wraz z rekordami.</span><span class="sxs-lookup"><span data-stu-id="505de-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>

## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="505de-104">Emitowanie niestandardowych rekordów śledzenia</span><span class="sxs-lookup"><span data-stu-id="505de-104">Emitting Custom Tracking Records</span></span>

<span data-ttu-id="505de-105">Niestandardowe rekordy śledzenia mogą być emitowane z działania kodu, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="505de-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<span data-ttu-id="505de-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> jest emitowane w działaniu kodu przez wywołanie <xref:System.Activities.NativeActivityContext.Track%2A> metody w `ActivityContext` .</span><span class="sxs-lookup"><span data-stu-id="505de-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActivityContext`.</span></span>

## <a name="see-also"></a><span data-ttu-id="505de-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="505de-107">See also</span></span>

- <span data-ttu-id="505de-108">[Monitorowanie aplikacji sieci szkieletowej systemu Windows Server](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="505de-108">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="505de-109">[Monitorowanie aplikacji przy użyciu sieci szkieletowej aplikacji](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="505de-109">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
