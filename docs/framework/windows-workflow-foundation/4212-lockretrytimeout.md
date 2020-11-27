---
title: 4212 — LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 43ec434064f768fc976232c6d3013f17c80fe053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267172"
---
# <a name="4212---lockretrytimeout"></a>4212 — LockRetryTimeout

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|4212|  
|Słowa kluczowe|WFInstanceStore|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Dostawca SQL napotkał przekroczenie limitu czasu podczas próby uzyskania blokady wystąpienia.  
  
## <a name="message"></a>Wiadomość  

 Przekroczono limit czasu podczas próby uzyskania blokady wystąpienia.  Operacja nie została ukończona w wyznaczonym limicie czasu wynoszącym %1. Czas przydzielony na tę operację mógł być częścią dłuższego limitu czasu.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Opóźnienie|XS: ciąg|Opóźnienie między ponownymi próbami.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
