---
title: -publicsign (opcje kompilatora C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 2655e0216a412053e052ab2ec2fcc8c68ea4f968
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268052"
---
# <a name="-publicsign-c-compiler-options"></a>-publicsign (opcje kompilatora C#)

Ta opcja powoduje, że kompilator zastosuje klucz publiczny, ale w rzeczywistości nie podpisze zestawu. Opcja **-publicsign** ustawia również bit w zestawie, który informuje środowisko uruchomieniowe, że plik jest rzeczywiście podpisany.

## <a name="syntax"></a>Składnia

```console
-publicsign
```

## <a name="arguments"></a>Argumenty

Brak.

## <a name="remarks"></a>Uwagi

Opcja **-publicsign** wymaga użycia elementu [-KeyFile](keyfile-compiler-option.md) lub [-containerer](keycontainer-compiler-option.md). Opcje **KeyFile** lub **containerer** określają klucz publiczny.

Opcje **-publicsign** i **-delaysign** wykluczają się wzajemnie.

Czasami nazywane "fałszywym znakiem" lub "OSS Sign", podpisywanie publiczne obejmuje klucz publiczny w zestawie danych wyjściowych i ustawia flagę "podpisane", ale w rzeczywistości nie podpisuje zestawu przy użyciu klucza prywatnego. Jest to przydatne w przypadku projektów open source, w których osoby chcą tworzyć zestawy, które są zgodne z opublikowanymi "w pełni podpisanymi", ale nie mają dostępu do klucza prywatnego używanego do podpisywania zestawów. Ponieważ niemal żaden konsument nie musi sprawdzić, czy zestaw jest w pełni podpisany, te publicznie skompilowane zestawy są dostępne w prawie każdym scenariuszu, w którym zostanie użyty całkowicie podpisany.

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a>Aby ustawić tę opcję kompilatora w pliku csproj

Otwórz plik. csproj projektu i Dodaj następujący element:

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a>Zobacz także

- [Kompilator języka C# — opcja delaysign](delaysign-compiler-option.md)
- [Kompilator języka C# — opcja keyfile](keyfile-compiler-option.md)
- [Kompilator języka C# — opcja kontenera](keycontainer-compiler-option.md)
- [Opcje kompilatora C#](index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
