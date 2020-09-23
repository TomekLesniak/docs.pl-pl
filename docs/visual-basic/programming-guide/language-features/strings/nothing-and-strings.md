---
title: Nothing i ciągi
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d4c7ee6d13334617a80abb845af52bf388a12797
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072525"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing i ciągi w Visual Basic

Środowisko uruchomieniowe Visual Basic i .NET Framework są oceniane w `Nothing` różny sposób, gdy przejdzie do ciągów.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic środowisko uruchomieniowe i .NET Framework  

 Rozpatrzmy następujący przykład:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Środowisko uruchomieniowe Visual Basic zwykle jest obliczane `Nothing` jako ciąg pusty (""). .NET Framework nie jest jednak ani zgłasza wyjątek, gdy podejmowana jest próba wykonania operacji na ciągach `Nothing` .  
  
## <a name="see-also"></a>Zobacz także

- [Wprowadzenie do ciągów w Visual Basic](introduction-to-strings.md)
