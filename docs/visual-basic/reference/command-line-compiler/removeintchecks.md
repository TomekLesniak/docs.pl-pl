---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: ce1f24f25ea58cb6ddc2f5c582b6103d8f18d922
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085168"
---
# <a name="-removeintchecks"></a>-removeintchecks

Włącza lub wyłącza przepełnienie — sprawdzanie błędów dla operacji całkowitych.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argumenty  
  
|Termin|Definicja|  
|---|---|  
|`+` &#124; `-`|Opcjonalny. `-removeintchecks-`Opcja powoduje, że kompilator sprawdza wszystkie obliczenia całkowite dla błędów przepełnienia. Wartość domyślna to `-removeintchecks-`.<br /><br /> Określanie `-removeintchecks` lub `-removeintchecks+` zapobiega sprawdzaniu błędów i umożliwia szybsze Obliczanie liczb całkowitych. Jednak bez sprawdzania błędów, a w przypadku przepełnienia zdolności do typów danych można przechowywać nieprawidłowe wyniki bez zgłaszania błędu.|  
  
|Aby ustawić-removeintchecks w zintegrowanym środowisku programistycznym programu Visual Studio|  
|---|  
|1. zaznaczono projekt w **Eksplorator rozwiązań**. W menu **projekt** kliknij polecenie **Właściwości**. <br />2. Kliknij kartę **kompilacja** .<br />3. kliknij przycisk **Zaawansowane** .<br />4. Zmodyfikuj wartość pola **sprawdzania przepełnienia liczby całkowitej** .|  
  
## <a name="example"></a>Przykład  

 Poniższy kod kompiluje `Test.vb` i wyłącza przepełnienie całkowite — sprawdzanie błędów.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
