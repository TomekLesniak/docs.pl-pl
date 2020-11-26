---
title: 4209 — TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9aa8cdffebb0cdf8b1e8225a394edf78ecf032b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238681"
---
# <a name="4209---timeoutopeningsqlconnection"></a>4209 — TimeoutOpeningSqlConnection

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|4209|  
|Słowa kluczowe|WFInstanceStore|  
|Poziom|Błąd|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że podczas próby otwarcia połączenia SQL został przekroczony limit czasu.  
  
## <a name="message"></a>Wiadomość  

 Przekroczono limit czasu podczas próby otwarcia połączenia SQL. Operacja nie została ukończona w wyznaczonym limicie czasu wynoszącym %1. Czas przydzielony na tę operację mógł być częścią dłuższego limitu czasu.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Limit czasu|XS: ciąg|Wartość limitu czasu dla otwierania połączenia SQL.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
