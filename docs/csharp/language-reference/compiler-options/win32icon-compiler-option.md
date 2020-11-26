---
description: -win32icon (opcje kompilatora C#)
title: -win32icon (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 5b62bbfe28bb5aa82605a88a83cf82eff9278807
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91168871"
---
# <a name="-win32icon-c-compiler-options"></a>-win32icon (opcje kompilatora C#)

Opcja **-win32icon** wstawia plik. ico w pliku wyjściowym, co daje plikowi wyjściowemu odpowiedni wygląd w Eksploratorze plików.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argumenty  

 `filename`  
 Plik ICO, który ma zostać dodany do pliku wyjściowego.  
  
## <a name="remarks"></a>Uwagi  

 Plik. ico można utworzyć za pomocą [kompilatora zasobów](/windows/desktop/menurc/resource-compiler). Kompilator zasobów jest wywoływany podczas kompilowania programu Visual C++owego; plik. ico jest tworzony na podstawie pliku. rc.  
  
 Zobacz [-linkresource —](./linkresource-compiler-option.md) (to Reference) lub [-Resource](./resource-compiler-option.md) (aby dołączyć) .NET Framework plik zasobów. Aby zaimportować plik. res, zobacz temat [-win32res —](./win32res-compiler-option.md) .  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz strony **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **aplikacji** .  
  
3. Zmodyfikuj właściwość **ikony aplikacji** .  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A> .  
  
## <a name="example"></a>Przykład  

 Kompiluj `in.cs` i Dołącz plik. ico `rf.ico` do produkcji `in.exe` :  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
