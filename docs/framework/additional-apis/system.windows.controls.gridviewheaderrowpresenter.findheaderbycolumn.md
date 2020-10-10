---
title: Metoda FindHeaderByColumn (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Dowiedz się więcej o metodzie prywatnej WPF o nazwie FindHeaderByColumn.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877773"
---
# <a name="findheaderbycolumn-method"></a>FindHeaderByColumn, Metoda

Znajduje nagłówek kolumny dla określonej kolumny w drzewie wizualnym.

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> Ta metoda jest prywatna i nie jest przeznaczona do użycia bezpośrednio w kodzie.
>
> Firma Microsoft nie obsługuje korzystania z tej metody w aplikacji produkcyjnej w żadnej sytuacji.

## <a name="parameters"></a>Parametry

`column` <xref:System.Windows.Controls.GridViewColumn>\
Kolumna, której nagłówek ma być znaleziony i zwrócony.

## <a name="return-value"></a>Wartość zwracana

<xref:System.Windows.Controls.GridViewColumnHeader>\
Nagłówek określonej kolumny lub `null` Jeśli określona kolumna nie istnieje.

## <a name="requirements"></a>Wymagania

**Przestrzeń nazw:**<xref:System.Windows.Controls>

**Zestaw:** PresentationFramework.dll

## <a name="see-also"></a>Zobacz też

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
