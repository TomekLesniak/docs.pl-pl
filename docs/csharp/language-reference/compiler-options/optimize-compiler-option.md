---
description: -Optymalizuj (opcje kompilatora C#)
title: -Optymalizuj (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: 1862794e4d823e38ce19780300a0b04f4e57dc44
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193988"
---
# <a name="-optimize-c-compiler-options"></a>-Optymalizuj (opcje kompilatora C#)

Opcja **-Optimize** włącza lub wyłącza optymalizacje wykonywane przez kompilator, aby plik wyjściowy był mniejszy, szybszy i bardziej wydajny.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a>Uwagi  

 **-Optymalizuj** również informuje środowisko uruchomieniowe języka wspólnego, aby zoptymalizować kod w czasie wykonywania.  
  
 Optymalizacje są domyślnie wyłączone. Określ **-Optimize +** , aby włączyć optymalizacje.  
  
 Podczas kompilowania modułu, który ma być używany przez zestaw, należy użyć **tych samych ustawień** , co w przypadku zestawu.  
  
 **-o** jest krótką formą **optymalizacji**.  
  
 Istnieje możliwość połączenia opcji **-Optimize** i [-Debug](./debug-compiler-option.md) .  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **kompilacja** .  
  
3. Zmodyfikuj właściwość **Optimize Code** .  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A> .  
  
## <a name="example"></a>Przykład  

 Kompiluj `t2.cs` i Włącz optymalizacje kompilatora:  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
