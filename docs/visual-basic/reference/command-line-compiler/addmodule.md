---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2db122acc03056a9cb6f355119d4c4e6da6ed175
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097790"
---
# <a name="-addmodule"></a>-addmodule

Powoduje, że kompilator udostępnił wszystkie informacje o typie z określonych plików dla aktualnie kompilowanego projektu.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumenty  

 `fileList`  
 Wymagany. Rozdzielana przecinkami lista plików, które zawierają metadane, ale nie zawierają manifestów zestawów. Nazwy plików zawierające spacje powinny być ujęte w znaki cudzysłowu ("").  
  
## <a name="remarks"></a>Uwagi  

 Pliki wymienione przez `fileList` parametr muszą zostać utworzone przy użyciu `-target:module` opcji lub innego kompilatora, który jest odpowiednikiem `-target:module` .  
  
 Wszystkie dodane moduły `-addmodule` muszą znajdować się w tym samym katalogu, co plik wyjściowy w czasie wykonywania. Oznacza to, że można określić moduł w dowolnym katalogu w czasie kompilacji, ale moduł musi znajdować się w katalogu aplikacji w czasie wykonywania. Jeśli tak nie jest, zostanie wyświetlony <xref:System.TypeLoadException> komunikat o błędzie.  
  
 Jeśli określisz (niejawnie lub jawnie) opcję[docelową (Visual Basic)](target.md) inną niż `-target:module` with `-addmodule` , pliki przekazywane do `-addmodule` zestawu projektu stają się częścią. Zestaw jest wymagany do uruchomienia pliku wyjściowego, który ma co najmniej jeden plik, który został dodany za pomocą `-addmodule` .  
  
 Użyj [parametru-reference (Visual Basic)](reference.md) do zaimportowania metadanych z pliku, który zawiera zestaw.  
  
> [!NOTE]
> `-addmodule`Opcja jest niedostępna w środowisku deweloperskim programu Visual Studio. jest ona dostępna tylko podczas kompilowania z wiersza polecenia.  
  
## <a name="example"></a>Przykład  

 Poniższy kod tworzy moduł.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Poniższy kod importuje typy modułu.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 Po uruchomieniu `t1` programu jest to wyjście `802` .  
  
## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [-Target (Visual Basic)](target.md)
- [-Reference (Visual Basic)](reference.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
