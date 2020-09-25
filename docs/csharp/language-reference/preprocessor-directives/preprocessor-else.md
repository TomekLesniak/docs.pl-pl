---
description: '#Odwołanie w języku C#'
title: '#Odwołanie w języku C#'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: f0dc8c34672c3e9e5a2207211794fbc8099640c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168676"
---
# <a name="else-c-reference"></a>#else (odwołanie w C#)

`#else` umożliwia utworzenie złożonej dyrektywy warunkowej, tak aby w przypadku braku wyrażeń w powyższym [#if](./preprocessor-if.md) lub (opcjonalnie) [#elif](./preprocessor-elif.md) dyrektywy nie były oceniane do `true` , kompilator oceni cały kod między i po `#else` nim `#endif` .  
  
## <a name="remarks"></a>Uwagi  

 [#endif](./preprocessor-endif.md) musi być następną dyrektywą preprocesora `#else` . Zobacz [#if](./preprocessor-if.md) , aby zapoznać się z przykładem sposobu korzystania z programu `#else` .  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
