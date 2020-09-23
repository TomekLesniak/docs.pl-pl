---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 7ded2b7d102430d8d4e545da5ab6ce8bafe3609e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095425"
---
# <a name="-recurse"></a>-recurse

Kompiluje pliki kodu źródłowego we wszystkich katalogach podrzędnych określonego katalogu lub katalogu projektu.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumenty  

 `dir`  
 Opcjonalny. Katalog, w którym ma zostać rozpoczęte wyszukiwanie. Jeśli nie zostanie określony, wyszukiwanie rozpoczyna się w katalogu projektu.  
  
 `file`  
 Wymagany. Pliki do wyszukania. Symbole wieloznaczne są dozwolone.  
  
## <a name="remarks"></a>Uwagi  

 W nazwie pliku można użyć symboli wieloznacznych, aby skompilować wszystkie zgodne pliki w katalogu projektu bez użycia `-recurse` . Jeśli nazwa pliku wyjściowego nie zostanie określona, kompilator opiera się na nazwie pliku wyjściowego w pierwszym przetworzonym pliku wejściowym. Zwykle jest to pierwszy plik na liście plików skompilowanych podczas wyświetlania alfabetycznie. Z tego powodu najlepiej określić plik wyjściowy przy użyciu `-out` opcji.  
  
> [!NOTE]
> `-recurse`Opcja jest niedostępna w środowisku deweloperskim programu Visual Studio. jest ona dostępna tylko podczas kompilowania z wiersza polecenia.  
  
## <a name="example"></a>Przykład  

 Poniższe polecenie kompiluje wszystkie pliki Visual Basic w bieżącym katalogu.  
  
```console
vbc *.vb  
```  
  
 Poniższe polecenie kompiluje wszystkie pliki Visual Basic w `Test\ABC` katalogu i wszystkie znajdujące się w nim katalogi, a następnie generuje `Test.ABC.dll` .  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [-out (Visual Basic)](out.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
