---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497049"
---
### <a name="wpf-printing-stack-update"></a>Aktualizacja stosu drukowania WPF

#### <a name="details"></a>Szczegóły

Interfejsy API drukowania platformy WPF korzystające z <xref:System.Printing.PrintQueue?displayProperty=fullName> interfejsu API Wywołaj teraz okna wywołującego na rzecz obecnie przestarzałego interfejsu API drukowania XPS. Zmiany zostały wprowadzone z myślą o potrzebach. ani użytkownicy, ani deweloperzy nie powinni widzieć żadnych zmian w zachowaniu lub użyciu interfejsu API. Nowy stos drukowania jest domyślnie włączony podczas uruchamiania aktualizacji systemu Windows 10 dla twórców. Stary stos drukowania nadal będzie działać tak samo jak wcześniej w starszych wersjach systemu Windows.

#### <a name="suggestion"></a>Sugestia

Aby użyć starego stosu w aktualizacji systemu Windows 10 dla twórców, należy ustawić <code>UseXpsOMPrinting</code> wartość REG_DWORD <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> klucza rejestru na <code>1</code> .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4,7|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
