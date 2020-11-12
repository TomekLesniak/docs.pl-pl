---
title: Azure Functions — aplikacje bezserwerowe
description: Usługa Azure Functions zapewnia bezserwerowe funkcje w wielu językach (C#, JavaScript, Java) i na platformach, aby zapewnić błyskawiczny kod skali oparty na zdarzeniach.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 08e1aaecdee753dc25cca0d6356caaafae1ad510
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557119"
---
# <a name="azure-functions"></a>Azure Functions

Azure Functions zapewnić środowisko obliczeniowe bezserwerowe. Funkcja jest wywoływana przez *wyzwalacz* (taki jak dostęp do punktu końcowego http lub Timer) i wykonuje blok kodu lub logiki biznesowej. Funkcje obsługują także wyspecjalizowane *powiązania* , które łączą się z zasobami, takimi jak magazyn i kolejki.

![Logo usługi Azure Functions](./media/azure-functions-logo.png)

Bieżąca wersja środowiska uruchomieniowego 3,0 obsługuje Międzyplatformowe aplikacje platformy .NET Core 3,1. Obsługiwane są dodatkowe języki, takie jak JavaScript, F # i Java. Funkcje utworzone w portalu zawierają rozbudowaną składnię skryptów. Funkcje utworzone jako projekty autonomiczne mogą być wdrażane z pełną obsługą platformy i możliwościami.

Aby uzyskać więcej informacji, zobacz [dokumentację Azure Functions](/azure/azure-functions).

## <a name="programming-language-support"></a>Obsługa języków programowania

Poniższe języki są obsługiwane ogólnie dostępnym.

|Język      |Obsługiwane środowiska uruchomieniowe|
|--------------|------------------|
|**C#**        |.NET Core 3,1     |
|**JavaScript**|Node 10 & 12      |
|**F#**        |.NET Core 3,1     |
|**Java**      |Java 8            |
|**Python**    |Python 3,6, 3,7, & 3,8|
|**TypeScript**|Node 10 & 12 (za pośrednictwem języka JavaScript)|
|**Program PowerShell**|Program PowerShell Core 6|

Aby uzyskać więcej informacji, zobacz listę [obsługiwanych języków](/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Plany usługi App Service

Funkcje są obsługiwane przez *plan usługi App Service*. Plan definiuje zasoby używane przez aplikację Functions. Można przypisać plany do regionu, określić rozmiar i liczbę maszyn wirtualnych, które będą używane, i wybrać warstwę cenową. W przypadku prawdziwej metody bezserwerowej aplikacje funkcji mogą korzystać z planu **zużycia** . Plan zużycia spowoduje automatyczne skalowanie zaplecza na podstawie obciążenia.

Inną opcją hostingu dla aplikacji funkcji jest [Plan Premium](/azure/azure-functions/functions-premium-plan). Ten plan zapewnia wystąpienie "Always On", aby uniknąć zimnego uruchamiania, obsługuje zaawansowane funkcje, takie jak łączność z siecią wirtualną i działa na sprzęcie Premium.

Aby uzyskać więcej informacji, zobacz [plany usługi App Service](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Tworzenie pierwszej funkcji

Istnieją trzy typowe sposoby tworzenia aplikacji funkcji.

- Funkcje skryptów w portalu.
- Tworzenie niezbędnych zasobów przy użyciu interfejsu wiersza polecenia platformy Azure.
- Twórz funkcje lokalnie przy użyciu ulubionego środowiska IDE i publikuj je na platformie Azure.

Aby uzyskać więcej informacji na temat tworzenia funkcji skryptowej w portalu, zobacz [Tworzenie pierwszej funkcji w Azure Portal](/azure/azure-functions/functions-create-first-azure-function).

Aby skompilować z poziomu interfejsu wiersza polecenia platformy Azure, zobacz [Tworzenie pierwszej funkcji przy użyciu interfejsu wiersza polecenia platformy Azure](/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Aby utworzyć funkcję z programu Visual Studio, zobacz [Tworzenie pierwszej funkcji przy użyciu programu Visual Studio](/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Omówienie wyzwalaczy i powiązań

Funkcje są wywoływane przez *wyzwalacz* i mogą mieć dokładnie jeden. Oprócz wywoływania funkcji, niektóre wyzwalacze również pełnią rolę powiązań. Oprócz wyzwalacza można również zdefiniować wiele powiązań. *Powiązania* zapewniają deklaratywny sposób łączenia danych z kodem. Mogą być przekazywane (dane wejściowe) lub odbierać dane (dane wyjściowe). Wyzwalacze i powiązania ułatwiają korzystanie z funkcji. Powiązania usuwają koszty ręcznego tworzenia połączeń bazy danych lub systemu plików. Wszystkie informacje dotyczące powiązań są zawarte w specjalnym *functions.jsw* pliku dla skryptów lub zadeklarowane z atrybutami w kodzie.

Niektóre typowe wyzwalacze obejmują:

- Blob Storage: wywołaj funkcję, gdy plik lub folder zostanie przekazany lub zmieniony w magazynie.
- HTTP: wywoływanie funkcji, takiej jak interfejs API REST.
- Kolejka: wywoływanie funkcji, gdy istnieją elementy w kolejce.
- Czasomierz: wywołaj funkcję na zwykłych erze.

Przykłady powiązań obejmują:

- CosmosDB: łatwo Nawiązuj połączenie z bazą danych w celu załadowania lub zapisania plików.
- Table Storage: Pracuj z magazynem kluczy/wartości z aplikacji funkcji.
- Queue Storage: łatwo Pobieraj elementy z kolejki lub umieszczaj nowe elementy w kolejce.

Poniższy przykład *functions.jsw* pliku definiuje wyzwalacz i powiązanie:

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

W tym przykładzie funkcja jest wyzwalana przez zmianę w magazynie obiektów BLOB w `images` kontenerze. Informacje dotyczące pliku są przesyłane, więc wyzwalacz działa również jako powiązanie. Istnieje inne powiązanie, aby umieścić informacje w kolejce o nazwie `images` .

Oto skrypt języka C# dla funkcji:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

Przykładem jest prosta funkcja, która przyjmuje nazwę pliku, który został zmodyfikowany lub przekazany do usługi BLOB Storage, i umieszcza go w kolejce do późniejszego przetwarzania.

Aby zapoznać się z pełną listą wyzwalaczy i powiązań, zobacz temat [Azure Functions wyzwalacze i koncepcje powiązań](/azure/azure-functions/functions-triggers-bindings).

>[!div class="step-by-step"]
>[Poprzedni](azure-serverless-platform.md) 
> [Dalej](application-insights.md)
