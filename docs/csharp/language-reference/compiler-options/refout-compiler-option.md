---
description: -opcji refout (opcje kompilatora C#)
title: -opcji refout (opcje kompilatora C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 424782e4607fea63130e95ab09a671c75fe1404d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128717"
---
# <a name="-refout-c-compiler-options"></a>-opcji refout (opcje kompilatora C#)

Opcja **-opcji refout** określa ścieżkę pliku, w którym zestaw odniesienia powinien być wyjściowy. Powoduje to przetłumaczenie na `metadataPeStream` w interfejsie API emisji. Ta opcja odnosi się do właściwości Project [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) programu MSBuild.

## <a name="syntax"></a>Składnia

```console
-refout:filepath
```

## <a name="arguments"></a>Argumenty

 `filepath` Ścieżka do zestawu referencyjnego. Zwykle powinna być zgodna z zestawem podstawowym. Zalecaną konwencją (używaną przez program MSBuild) jest umieszczenie zestawu odwołania w podfolderze "ref/" względem podstawowego zestawu.

## <a name="remarks"></a>Uwagi

Zestawy referencyjne są specjalnym typem zestawu, który zawiera tylko minimalną ilość metadanych wymaganą do reprezentowania publicznej powierzchni interfejsu API biblioteki. Obejmują one deklaracje dla wszystkich elementów członkowskich, które są istotne w przypadku odwoływania się do zestawu w narzędziach kompilacji, ale wyklucza wszystkie implementacje składowych i deklaracje prywatnych członków, którzy nie mają zauważalnego wpływu na ich kontrakt interfejsu API. Aby uzyskać więcej informacji, zobacz [zestawy referencyjne](../../../standard/assembly/reference-assemblies.md) w przewodniku .NET.

`-refout`Opcje i [`-refonly`](refonly-compiler-option.md) wzajemnie się wykluczają.

## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
