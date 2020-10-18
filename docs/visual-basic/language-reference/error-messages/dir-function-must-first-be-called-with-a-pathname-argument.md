---
title: Należy najpierw wywołać funkcję „Dir” z argumentem „PathName”
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 7f8191b0ef5452fcf6f3a20c3e0f28ca84ef9c4a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163431"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Należy najpierw wywołać funkcję „Dir” z argumentem „PathName”

Początkowe wywołanie `Dir` funkcji nie zawiera `PathName` argumentu. Pierwsze wywołanie `Dir` musi zawierać a `PathName` , ale kolejne wywołania `Dir` nie muszą zawierać parametrów do pobrania następnego elementu.

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Podaj `PathName` argument w wywołaniu funkcji.

## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
