---
title: Wyjątki hostingu
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: 342420f10ed53e4f4786ed9506cfde5fbfcfc957
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263337"
---
# <a name="hosting-exceptions"></a>Wyjątki hostingu

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez hosting.  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Pełny identyfikator URI jest niedozwolony. Pełne identyfikatory URI są niedozwolone dla interfejsu API ServiceHostingEnvironment. EnsureServiceAvailable. Użyj ścieżki wirtualnej odpowiedniej usługi.|  
|Hosting_BuildProviderCouldNotCreateType|Nie można załadować określonego typu CLR podczas kompilacji usługi. Sprawdź, czy ten typ jest zdefiniowany w pliku źródłowym znajdującym się w \\ katalogu \ App_Code aplikacji, zawarty w skompilowanym zestawie znajdującym się w \\ katalogu \Bin aplikacji lub w zestawie zainstalowanym w globalnej pamięci podręcznej zestawów. W nazwie typu jest rozróżniana wielkość liter. Katalogi, takie jak \\ \ App_Code i \\ \Bin, muszą znajdować się w katalogu głównym aplikacji. \\Katalogi \ App_Code i \\ \Bin nie mogą być zagnieżdżane w podkatalogach.|
