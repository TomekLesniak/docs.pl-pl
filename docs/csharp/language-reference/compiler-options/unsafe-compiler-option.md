---
description: -unsafe (opcje kompilatora C#)
title: -unsafe (opcje kompilatora C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 0f6d94dd25a020d96430746c4b5e7aefd0f679da
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140844"
---
# <a name="-unsafe-c-compiler-options"></a>-unsafe (opcje kompilatora C#)

Opcja **niebezpiecznego** kompilatora umożliwia kompilowanie kodu, który używa [niebezpiecznego](../keywords/unsafe.md) słowa kluczowego.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat niebezpiecznego kodu, zobacz artykuł [niebezpieczny kod i wskaźniki](../../programming-guide/unsafe-code-pointers/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **kompilacja** .  
  
3. Zaznacz pole wyboru **Zezwalaj na niebezpieczny kod** .  
  
### <a name="to-add-this-option-in-a-csproj-file"></a>Aby dodać tę opcję w pliku csproj

Otwórz plik. csproj projektu i Dodaj następujące elementy:

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A> .  
  
## <a name="example"></a>Przykład

Kompiluj `in.cs` dla trybu niebezpiecznego:  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
