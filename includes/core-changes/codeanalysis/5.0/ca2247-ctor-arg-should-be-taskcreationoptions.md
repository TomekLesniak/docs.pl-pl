---
ms.openlocfilehash: 6bb3b11ef4e4cb6f6a039c97911b0acca862fe6f
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065190"
---
### <a name="ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a>CA2247: argumentem konstruktora TaskCompletionSource powinien być wartość opcji TaskCreationOptions

Reguła analizatora kodu platformy .NET [CA2247](/visualstudio/code-quality/ca2247) jest domyślnie włączona, począwszy od platformy .NET 5,0. Generuje ostrzeżenie kompilacji dla wywołań <xref:System.Threading.Tasks.TaskCompletionSource%601> konstruktora, który przekazuje argument typu <xref:System.Threading.Tasks.TaskContinuationOptions> .

#### <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Niektóre z tych reguł są domyślnie włączone, w tym [CA2247](/visualstudio/code-quality/ca2247). Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.

CA2247 reguły odnajduje wywołania <xref:System.Threading.Tasks.TaskCompletionSource%601> konstruktora, które przekazują argument typu <xref:System.Threading.Tasks.TaskContinuationOptions> . <xref:System.Threading.Tasks.TaskCompletionSource%601>Typ ma konstruktora, który akceptuje <xref:System.Threading.Tasks.TaskCreationOptions> wartość i inny Konstruktor akceptujący <xref:System.Object> . Jeśli przypadkowo przeszedł <xref:System.Threading.Tasks.TaskContinuationOptions> wartość zamiast <xref:System.Threading.Tasks.TaskCreationOptions> wartości, Konstruktor z <xref:System.Object> parametrem jest wywoływany w czasie wykonywania. Kod zostanie skompilowany i uruchomiony, ale nie będzie miał zamierzonego zachowania.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

- Zamień <xref:System.Threading.Tasks.TaskContinuationOptions> argument na odpowiadającą <xref:System.Threading.Tasks.TaskCreationOptions> wartość. Nie pomijaj tego ostrzeżenia, ponieważ prawie zawsze wyróżnia usterkę w kodzie. Aby uzyskać więcej informacji, zobacz [CA2247](/visualstudio/code-quality/ca2247).

- Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu. Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Kategoria

Analiza kodu

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

#### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

-->
