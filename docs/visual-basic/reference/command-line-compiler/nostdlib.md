---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 4fcc5305985f5ba32b3e6ffb740c0611821215d3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097660"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)

Powoduje, że kompilator nie będzie automatycznie odwoływać się do bibliotek standardowych.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Uwagi  

 `-nostdlib`Opcja usuwa automatyczne odwołanie do zestawu System.dll i uniemożliwia kompilatorowi odczytywanie pliku VBC. rsp. Plik VBC. rsp, który znajduje się w tym samym katalogu co plik Vbc.exe, odwołuje się do najczęściej używanych .NET Framework zestawów i importuje `System` `Microsoft.VisualBasic` przestrzenie nazw.  
  
> [!NOTE]
> Zestawy Mscorlib.dll i Microsoft.VisualBasic.dll są zawsze przywoływane.  
  
> [!NOTE]
> `-nostdlib`Opcja jest niedostępna w środowisku deweloperskim programu Visual Studio. jest ona dostępna tylko podczas kompilowania z wiersza polecenia.  
  
## <a name="example"></a>Przykład  

 Poniższy kod kompiluje się `T2.vb` bez odwoływania się do bibliotek standardowych. `_MYTYPE`Aby usunąć obiekt, należy ustawić stałą dla kompilacji warunkowej na ciąg "Empty" `My` .  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Zobacz także

- [-noconfig](noconfig.md)
- [Kompilator wiersza polecenia Visual Basic](index.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
- [Dostosowywanie, które obiekty są dostępne w My](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
