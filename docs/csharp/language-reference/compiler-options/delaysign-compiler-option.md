---
description: -delaysign (opcje kompilatora C#)
title: -delaysign (opcje kompilatora C#)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 5512ebeca4672f5d69852ab07c3f3fa40c305327
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125842"
---
# <a name="-delaysign-c-compiler-options"></a>-delaysign (opcje kompilatora C#)

Ta opcja powoduje, że kompilator rezerwuje miejsce w pliku wyjściowym, aby można było później dodać podpis cyfrowy.

## <a name="syntax"></a>Składnia

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a>Argumenty

`+` &#124; `-`

Użyj **-delaysign —** Jeśli chcesz użyć w pełni podpisanego zestawu. Użyj **-delaysign +** , jeśli chcesz umieścić klucz publiczny w zestawie. Wartość domyślna to **-delaysign-**.

## <a name="remarks"></a>Uwagi

Opcja **-delaysign** nie ma żadnego efektu, chyba że jest używana z atrybutem [-KeyFile](./keyfile-compiler-option.md) lub [-Container](./keycontainer-compiler-option.md).

Opcje **-delaysign** i **-publicsign** wykluczają się wzajemnie.

Po zażądaniu w pełni podpisanego zestawu, kompilator skrótów pliku, który zawiera manifest (metadane zestawu) i podpisuje ten skrót z kluczem prywatnym. Ta operacja tworzy podpis cyfrowy, który jest przechowywany w pliku, który zawiera manifest. Gdy zestaw jest podpisany z opóźnieniem, kompilator nie oblicza i nie przechowuje podpisu, ale rezerwuje miejsce w pliku, aby podpis mógł zostać dodany później.

Na przykład przy użyciu polecenia **-delaysign +** umożliwia testerowi umieszczenie zestawu w globalnej pamięci podręcznej. Po przetestowaniu można w pełni podpisać zestaw, umieszczając klucz prywatny w zestawie przy użyciu narzędzia [konsolidatora zestawu](../../../framework/tools/al-exe-assembly-linker.md) .

Aby uzyskać więcej informacji, zobacz [Tworzenie i używanie zestawów o silnych nazwach](../../../standard/assembly/create-use-strong-named.md) oraz [opóźnienie podpisywania zestawu](../../../standard/assembly/delay-sign.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz stronę **Właściwości** dla projektu.
1. Zmodyfikuj właściwość **opóźnienia tylko do podpisywania** .

Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.DelaySign%2A> .

## <a name="see-also"></a>Zobacz też

- [C# — opcja publicsign](publicsign-compiler-option.md)
- [Opcje kompilatora C#](index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
