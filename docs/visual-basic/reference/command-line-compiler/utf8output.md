---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 2faebb7870cbc019d479215563261f331f9fddcf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085077"
---
# <a name="-utf8output-visual-basic"></a>-utf8output — (Visual Basic)

Wyświetla dane wyjściowe kompilatora przy użyciu kodowania UTF-8.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argumenty  

 `+` &#124; `-`  
 Opcjonalny. Wartość domyślna dla tej opcji to `-utf8output-` , co oznacza, że wyjście kompilatora nie używa kodowania UTF-8. Określanie `-utf8output` jest takie samo jak określanie `-utf8output+` .  
  
## <a name="remarks"></a>Uwagi  

 W niektórych konfiguracjach międzynarodowych dane wyjściowe kompilatora nie mogą być prawidłowo wyświetlane w konsoli programu. W takich sytuacjach należy używać `-utf8output` i przekierować dane wyjściowe kompilatora do pliku.  
  
> [!NOTE]
> `-utf8output`Opcja jest niedostępna w środowisku deweloperskim programu Visual Studio. jest ona dostępna tylko podczas kompilowania z wiersza polecenia.  
  
## <a name="example"></a>Przykład  

 Poniższy kod kompiluje `In.vb` i kieruje kompilator do wyświetlania danych wyjściowych przy użyciu kodowania UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
