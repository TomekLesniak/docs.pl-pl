---
ms.openlocfilehash: 086dac69d085d070511fcfd5820bd2644ee4598e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497173"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>Marshal. SizeOf i Marshaling. PtrToStructure overloads Break Dynamic Code

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4.5.1, dynamiczne powiązanie z metodami,,,, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601> <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)> <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)> <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)> <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> lub <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> , (za pomocą programu Windows PowerShell, IronPython lub dynamicznego słowa kluczowego C#, na przykład) może spowodować, <code>MethodInvocationExceptions</code> że dodano nowe przeciążenia tych metod, które mogą być niejednoznaczne dla aparatów obsługi skryptów.

#### <a name="suggestion"></a>Sugestia

Aktualizuj skrypty, aby jasno wskazać, które Przeciążenie powinno być używane. Można to zrobić zazwyczaj przez jawne rzutowanie parametrów typu metody na <xref:System.Type> . Zobacz [ten link](https://support.microsoft.com/kb/2909958/) , aby uzyskać szczegółowe informacje i przykłady obejścia problemu.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
