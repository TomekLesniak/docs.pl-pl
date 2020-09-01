---
description: -nostdlib (opcje kompilatora C#)
title: -nostdlib (opcje kompilatora C#)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 214918b32f1f1276eb936e66daba3d372a1e9228
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125101"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (opcje kompilatora C#)

**-nostdlib** uniemożliwia import mscorlib.dll, który definiuje całą przestrzeń nazw System.

## <a name="syntax"></a>Składnia

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a>Uwagi

Użyj tej opcji, jeśli chcesz zdefiniować lub utworzyć własną przestrzeń nazw systemu i obiekty.

Jeśli nie określisz opcji **-nostdlib**, mscorlib.dll jest zaimportowana do programu (tak samo jak w przypadku określenia **-nostdlib-**). Określenie **-nostdlib** jest taka sama jak w przypadku określenia **-nostdlib +**.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Aby ustawić tę opcję kompilatora w programie Visual Studio

> [!NOTE]
> Poniższe instrukcje dotyczą tylko programu Visual Studio 2015 (i jego wcześniejszych wersji). Właściwość kompilacji **mscorlib.dllnie ** istnieje w nowszych wersjach programu Visual Studio.

1. Otwórz stronę **Właściwości** dla projektu.

2. Kliknij stronę właściwości **kompilacji** .

3. Kliknij przycisk **Zaawansowane** .

4. Zmodyfikuj właściwość nie **odwołuj mscorlib.dll** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A> .

## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
