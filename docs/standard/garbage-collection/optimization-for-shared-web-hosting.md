---
title: Optymalizacja udostępnionej usługi hostingu sieci Web
ms.date: 03/30/2017
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
ms.openlocfilehash: 6398c6749028827e5e3ee79a5511ac0879facbef
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824470"
---
# <a name="optimization-for-shared-web-hosting"></a>Optymalizacja udostępnionej usługi hostingu sieci Web
Jeśli jesteś administratorem serwera, który jest udostępniany przez hosting kilku małych witryn sieci Web, możesz zoptymalizować wydajność i zwiększyć pojemność lokacji, dodając następujące `gcTrimCommitOnLowMemory` ustawienie do `runtime` węzła w pliku Aspnet.config w katalogu .NET:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
> To ustawienie jest zalecane tylko w scenariuszach hostingu w sieci Web.  
  
 Ponieważ moduł wyrzucania elementów bezużytecznych zachowuje pamięć dla przyszłych przydziałów, jego zatwierdzone miejsce może być większe niż to, co jest absolutnie wymagane. Można zmniejszyć to miejsce do czasu, gdy występuje duże obciążenie pamięci systemowej. Zmniejszenie ilości tego zajmowanego miejsca zwiększa wydajność i zwiększa możliwości hostowania większej liczby lokacji.  
  
 Gdy to `gcTrimCommitOnLowMemory` ustawienie jest włączone, moduł zbierający elementy bezużyteczne szacuje obciążenie pamięci systemowej i przechodzi do trybu przycinania, gdy obciążenie osiągnie 90%. Utrzymuje tryb przycinania do momentu spadku obciążenia poniżej 85%.  
  
 Gdy warunki zezwalają, Moduł wyrzucania elementów bezużytecznych może zdecydować, że to `gcTrimCommitOnLowMemory` ustawienie nie będzie pomocne dla bieżącej aplikacji i nie zostanie zignorowane.  
  
## <a name="example"></a>Przykład  
 Poniższy fragment kodu XML pokazuje, jak włączyć `gcTrimCommitOnLowMemory` ustawienie. Elipsy wskazują inne ustawienia, które mogą znajdować się w `runtime` węźle.  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz także

- [Odzyskiwanie pamięci](index.md)
