---
description: -refonly (opcje kompilatora C#)
title: -refonly (opcje kompilatora C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: f9a92462203bedff93a4a711ca8742465b7a561c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89124750"
---
# <a name="-refonly-c-compiler-options"></a>-refonly (opcje kompilatora C#)

Opcja **-refonly** wskazuje, że zestaw odwołania powinien być wyjściem, a nie zestawem implementacji, jako podstawowy wynik. `-refonly`Parametr dyskretnie wyłącza umieszczanie plików PDB, ponieważ nie można wykonać zestawów referencyjnych. Ta opcja odnosi się do właściwości Project [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) programu MSBuild.

## <a name="syntax"></a>Składnia

```console
-refonly
```

## <a name="remarks"></a>Uwagi

Zestawy referencyjne są specjalnym typem zestawu, który zawiera tylko minimalną ilość metadanych wymaganą do reprezentowania publicznej powierzchni interfejsu API biblioteki. Obejmują one deklaracje dla wszystkich elementów członkowskich, które są istotne w przypadku odwoływania się do zestawu w narzędziach kompilacji, ale wyklucza wszystkie implementacje składowych i deklaracje prywatnych członków, którzy nie mają zauważalnego wpływu na ich kontrakt interfejsu API. Aby uzyskać więcej informacji, zobacz [zestawy referencyjne](../../../standard/assembly/reference-assemblies.md) w przewodniku .NET.

`-refonly`Opcje i [`-refout`](refout-compiler-option.md) wzajemnie się wykluczają.

## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
