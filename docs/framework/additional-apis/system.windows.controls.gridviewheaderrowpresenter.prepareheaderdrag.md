---
title: Metoda PrepareHeaderDrag (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Dowiedz się więcej o metodzie prywatnej WPF o nazwie PrepareHeaderDrag.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877766"
---
# <a name="prepareheaderdrag-method"></a>PrepareHeaderDrag, Metoda

Przygotowuje określony nagłówek kolumny dla zmiany kolejności.

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> Ta metoda jest prywatna i nie jest przeznaczona do użycia bezpośrednio w kodzie.
>
> Firma Microsoft nie obsługuje korzystania z tej metody w aplikacji produkcyjnej w żadnej sytuacji.

## <a name="parameters"></a>Parametry

`header` <xref:System.Windows.Controls.GridViewColumnHeader>\
Nagłówek kolumny, aby przygotować się do zmiany kolejności.

`pos` <xref:System.Windows.Point>\
Pozycja, względem <xref:System.Windows.Controls.GridViewHeaderRowPresenter> której rozpocznie się przeciąganie.

`relativePos` <xref:System.Windows.Point>\
Pozycja, względem `header` której rozpocznie się przeciąganie.

`cancelInvoke` <xref:System.Boolean>\
`true` Aby anulować zmianę kolejności; w przeciwnym razie `false` .

## <a name="requirements"></a>Wymagania

**Przestrzeń nazw:**<xref:System.Windows.Controls>

**Zestaw:** PresentationFramework.dll

## <a name="see-also"></a>Zobacz też

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
