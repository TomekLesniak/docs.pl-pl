---
description: -noconfig (opcje kompilatora C#)
title: -noconfig (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 26d0680743ccc3af26a0e81eeec9cd2fc0d693af
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125231"
---
# <a name="-noconfig-c-compiler-options"></a>-noconfig (opcje kompilatora C#)
Opcja **-noconfig** informuje kompilator, że nie kompiluje się z plikiem CSC. rsp, który znajduje się w i załadowany z tego samego katalogu co plik csc.exe.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Uwagi  
 Plik csc. rsp odwołuje się do wszystkich zestawów dostarczonych z .NET Framework. Rzeczywiste odwołania, które zawiera środowisko programistyczne Visual Studio .NET, zależą od typu projektu.  
  
 Można zmodyfikować plik csc. rsp i określić dodatkowe opcje kompilatora, które powinny być zawarte w każdej kompilacji z wiersza polecenia z csc.exe (z wyjątkiem opcji **-noconfig** ).  
  
 Kompilator przetwarza opcje przesłane do polecenia **CSC** jako ostatni. W związku z tym każda opcja w wierszu polecenia zastępuje ustawienie tej samej opcji w pliku CSC. rsp.  
  
 Jeśli nie chcesz, aby kompilator wyszukał i używał ustawień w pliku CSC. rsp, określ **-noconfig**.  
  
 Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
