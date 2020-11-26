---
description: -nowin32manifest (opcje kompilatora C#)
title: -nowin32manifest (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 13bbee66901149d54632d9b164431f8898cdf52e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91194001"
---
# <a name="-nowin32manifest-c-compiler-options"></a>-nowin32manifest (opcje kompilatora C#)

Użyj opcji **-nowin32manifest** , aby nakazać kompilatorowi nie osadzenie żadnego manifestu aplikacji w pliku wykonywalnym.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Uwagi  

 Gdy ta opcja jest używana, aplikacja będzie podlegać wirtualizacji w systemie Windows Vista, o ile nie podajesz manifestu aplikacji w pliku zasobów Win32 lub w późniejszym kroku kompilacji.  
  
 W programie Visual Studio Ustaw tę opcję na stronie **właściwości aplikacji** , wybierając opcję **Utwórz aplikację bez manifestu** na liście rozwijanej **manifestu** . Aby uzyskać więcej informacji, zobacz [Strona aplikacji, Projektant projektu (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Aby uzyskać więcej informacji na temat tworzenia manifestu, zobacz [-WIN32MANIFEST (opcje kompilatora C#)](./win32manifest-compiler-option.md).  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
