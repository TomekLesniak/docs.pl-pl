---
ms.openlocfilehash: f61cf21f9f30662cc8e383bb3aeb5c642f1665b8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497936"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>Zakleszczenie może wynikać z używania usług współużytkowanych

#### <a name="details"></a>Szczegóły

Zakleszczenie może skutkować usługą współużytkowaną, która ogranicza wystąpienia usługi do jednego wątku wykonywania w danym momencie. Usługi podatne na wystąpienie tego problemu będą miały następujące <xref:System.ServiceModel.ServiceBehaviorAttribute> kody:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a>Sugestia

Aby rozwiązać ten problem, można wykonać następujące czynności:

- Ustaw tryb współbieżności usługi na <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> lub <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType> . Przykład:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- Zainstaluj najnowszą aktualizację do .NET Framework 4.6.2 lub Uaktualnij do nowszej wersji .NET Framework. Spowoduje to wyłączenie przepływu <xref:System.Threading.ExecutionContext> w programie <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> . To zachowanie można skonfigurować. jest to równoznaczne z dodaniem do pliku konfiguracji następującego ustawienia aplikacji:

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

Wartość `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` nie powinna być nigdy ustawiona na `false` dla usług współużytkowanych.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Mały       |
| Wersja | 4.6.2       |
| Typ    | Przekierowanie |

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
