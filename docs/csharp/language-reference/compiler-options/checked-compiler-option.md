---
description: — zaznaczone (opcje kompilatora C#)
title: — zaznaczone (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: c92ad61b2f482631230e0e6aeb0af5716a4fcb61
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91196835"
---
# <a name="-checked-c-compiler-options"></a>— zaznaczone (opcje kompilatora C#)

Opcja **-** Check określa, czy instrukcja arytmetyczna liczb całkowitych, która skutkuje wartością, która jest poza zakresem danych, i która nie jest w zakresie [zaznaczonego](../keywords/checked.md) lub [niesprawdzonego](../keywords/unchecked.md) słowa kluczowego, powoduje wyjątek czasu wykonywania.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a>Uwagi  

 Instrukcja arytmetyczna liczb całkowitych, która znajduje się w `checked` zakresie `unchecked` słowa kluczowego or, nie podlega wpływowi opcji **-Checked** .  
  
 Jeśli instrukcja arytmetyczna liczb całkowitych, która nie znajduje się w `checked` zakresie `unchecked` słowa kluczowego lub, powoduje użycie wartości spoza zakresu typu danych i **-Checked +** (lub **-Checked**) jest używana w kompilacji, ta instrukcja powoduje wyjątek w czasie wykonywania. Jeśli **jest** używana w kompilacji, ta instrukcja nie powoduje wyjątku w czasie wykonywania.  
  
 Wartość domyślna dla tej opcji to **-Checked-**; Sprawdzanie przepełnienia jest wyłączone.

 Czasami zautomatyzowane narzędzia, które są używane do kompilowania zestawu dużych aplikacji, są sprawdzane w programie +. Jednym z scenariuszy użycia-checked-jest zastąpienie globalnego domyślnego narzędzia przez określenie-checked-.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu. Aby uzyskać więcej informacji, zobacz [stronę Kompilacja, Projektant projektu (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2. Kliknij stronę właściwości **kompilacja** .  
  
3. Kliknij przycisk **Zaawansowane** .  
  
4. Zmodyfikuj właściwość **sprawdzania przepełnienia arytmetycznego** .  
  
 Aby programowo uzyskać dostęp do tej opcji kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A> .  
  
## <a name="example"></a>Przykład  

 Następujące polecenie kompiluje `t2.cs` . Użycie `-checked` w poleceniu określa, że jakakolwiek instrukcja arytmetyczna liczb całkowitych w pliku, który nie jest w zakresie `checked` `unchecked` słowa kluczowego or, i powoduje, że wartość jest spoza zakresu typu danych, powoduje wyjątek w czasie wykonywania.  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
