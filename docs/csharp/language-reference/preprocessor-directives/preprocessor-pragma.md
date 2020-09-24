---
description: '#pragma — odwołanie w C#'
title: '#pragma — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168520"
---
# <a name="pragma-c-reference"></a>#pragma (odwołanie w C#)

`#pragma` przekazuje specjalne instrukcje kompilatora dla kompilacji pliku, w którym występuje. Instrukcje muszą być obsługiwane przez kompilator. Innymi słowy, nie można użyć `#pragma` programu do utworzenia niestandardowych instrukcji przetwarzania wstępnego. Kompilator języka C# firmy Microsoft obsługuje następujące dwie `#pragma` instrukcje:  
  
 [Ostrzeżenie #pragma](./preprocessor-pragma-warning.md)  
  
 [#pragma sum kontrolnych](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a>Składnia  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a>Parametry  

 `pragma-name`  
 Nazwa rozpoznanej dyrektywy pragma.  
  
 `pragma-arguments`  
 Argumenty specyficzne dla dyrektywy pragma.  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
- [Ostrzeżenie #pragma](./preprocessor-pragma-warning.md)
- [#pragma sum kontrolnych](./preprocessor-pragma-checksum.md)
