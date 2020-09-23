---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: d4b50d56373676bf78a7591102095209401c907d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097595"
---
# <a name="-optimize"></a>-optimize

Włącza lub wyłącza optymalizacje kompilatora.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argumenty  
  
|Termin|Definicja|  
|---|---|  
|`+` &#124; `-`|Opcjonalny. `-optimize-`Opcja wyłącza optymalizacje kompilatora. `-optimize+`Opcja włącza optymalizacje. Optymalizacje są domyślnie wyłączone.|  
  
## <a name="remarks"></a>Uwagi  

 Optymalizacje kompilatora sprawiają, że plik wyjściowy jest mniejszy, szybszy i bardziej wydajny. Jednakże, ponieważ optymalizacje powodują przemieszczenie kodu w pliku wyjściowym, `-optimize+` może utrudniać debugowanie.  
  
 Wszystkie moduły wygenerowane `-target:module` dla zestawu muszą używać tych samych `-optimize` ustawień co zestaw. Aby uzyskać więcej informacji, zobacz [-Target (Visual Basic)](target.md).  
  
 Można połączyć `-optimize` `-debug` Opcje i.  
  
|Aby ustawić-optymalizować w zintegrowanym środowisku programistycznym programu Visual Studio|  
|---|  
|1. zaznaczono projekt w **Eksplorator rozwiązań**. W menu **projekt** kliknij polecenie **Właściwości**.<br />     <br />2. Kliknij kartę **kompilacja** .<br />3. kliknij przycisk **Zaawansowane** .<br />4. Zmodyfikuj pole wyboru **Włącz optymalizacje** .|  
  
## <a name="example"></a>Przykład  

 Poniższy kod kompiluje `T2.vb` i włącza optymalizacje kompilatora.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [-Debug (Visual Basic)](debug.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
- [-Target (Visual Basic)](target.md)
