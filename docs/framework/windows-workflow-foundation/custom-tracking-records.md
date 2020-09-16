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
# <a name="custom-tracking-records"></a>Niestandardowe rekordy śledzenia

W tym temacie pokazano, jak utworzyć niestandardowe rekordy śledzenia i wypełnić je danymi, które mają być emitowane wraz z rekordami.

## <a name="emitting-custom-tracking-records"></a>Emitowanie niestandardowych rekordów śledzenia

Niestandardowe rekordy śledzenia mogą być emitowane z działania kodu, jak pokazano w poniższym przykładzie.

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

A <xref:System.Activities.Tracking.CustomTrackingRecord> jest emitowane w działaniu kodu przez wywołanie <xref:System.Activities.NativeActivityContext.Track%2A> metody w `ActivityContext` .

## <a name="see-also"></a>Zobacz także

- [Monitorowanie aplikacji sieci szkieletowej systemu Windows Server](/previous-versions/appfabric/ee677251(v=azure.10))
- [Monitorowanie aplikacji przy użyciu sieci szkieletowej aplikacji](/previous-versions/appfabric/ee677276(v=azure.10))
