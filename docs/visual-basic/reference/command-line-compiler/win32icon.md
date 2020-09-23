---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: c6d5e054063592db5777a76fe19da79337ed5034
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084960"
---
# <a name="-win32icon"></a>-win32icon

Wstawia plik. ico w pliku wyjściowym. Ten plik. ico reprezentuje plik wyjściowy w **Eksploratorze plików**.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argumenty  
  
|Termin|Definicja|  
|---|---|  
|`filename`|Plik. ico, który ma zostać dodany do pliku wyjściowego. Nazwa pliku należy ująć w cudzysłów (""), jeśli zawiera spację.|  
  
## <a name="remarks"></a>Uwagi  

 Plik. ico można utworzyć za pomocą kompilatora zasobów systemu Microsoft Windows (RC). Kompilator zasobów jest wywoływany podczas kompilowania programu Visual C++owego; plik. ico jest tworzony na podstawie pliku. rc. `-win32icon`Opcje i `-win32resource` wzajemnie się wykluczają.  
  
 Zobacz [-linkresource — (Visual Basic)](linkresource.md) , aby odwołać się do .NET Framework pliku zasobów, lub [-Resource (Visual Basic)](resource.md) , aby dołączyć plik zasobów .NET Framework. Aby zaimportować plik. res, zobacz temat [-win32resource](win32resource.md) .  
  
|Aby ustawić-win32icon w środowisku IDE programu Visual Studio|  
|---|  
|1. zaznaczono projekt w **Eksplorator rozwiązań**. W menu **projekt** kliknij polecenie **Właściwości**. <br />2. Kliknij kartę **aplikacja** .<br />3. Zmodyfikuj wartość w polu **ikony** .|  
  
## <a name="example"></a>Przykład  

 Poniższy kod kompiluje `In.vb` i dołącza plik. ico, `Rf.ico` .  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
