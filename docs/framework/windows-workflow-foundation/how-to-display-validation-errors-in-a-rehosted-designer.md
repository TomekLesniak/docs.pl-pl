---
title: 'Instrukcje: Wyświetlanie błędów walidacji w rehostowanym projektancie'
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: ccdb8941f46683dd1fd12387c0c5db2abe1d8dec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280042"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Instrukcje: Wyświetlanie błędów walidacji w rehostowanym projektancie

W tym temacie opisano sposób pobierania i publikowania błędów walidacji w przeszukiwanym Projektant przepływu pracy systemu Windows. Dzięki temu można sprawdzić, czy przepływ pracy w przewidzianym przez niego projektancie jest prawidłowy.  
  
 To zadanie ma dwie części. Pierwszym etapem jest dostarczenie implementacji <xref:System.Activities.Presentation.Validation.IValidationErrorService> .  Istnieje jedna metoda krytyczna do zaimplementowania w tym interfejsie, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> która przekaże do <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> dziennika debugowania listę obiektów zawierających informacje o błędach.  Po wdrożeniu interfejsu można pobrać informacje o błędzie, publikując wystąpienie tej implementacji w kontekście edycji.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Implementowanie interfejsu IValidationErrorService  
  
1. Oto przykład kodu dla prostej implementacji, która będzie zapisywać błędy walidacji w dzienniku debugowania.  
  
    ```csharp  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine($"Error: {vei.Message}"));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a>Publikowanie w kontekście edycji  
  
1. Oto kod, który zostanie opublikowany w kontekście edycji.  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
