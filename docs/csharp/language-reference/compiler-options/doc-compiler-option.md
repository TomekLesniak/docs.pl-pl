---
description: -doc (opcje kompilatora C#)
title: -doc (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: 366bad1029904b3571be0a76d827ff0213d776bb
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125751"
---
# <a name="-doc-c-compiler-options"></a>-doc (opcje kompilatora C#)
Opcja **-doc** umożliwia umieszczenie komentarzy do dokumentacji w pliku XML.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a>Argumenty  
 `file`  
 Plik wyjściowy dla XML, który jest wypełniony komentarzami w plikach kodu źródłowego kompilacji.  
  
## <a name="remarks"></a>Uwagi  
 W plikach kodu źródłowego Komentarze do dokumentacji, które poprzedzają następujące elementy, mogą być przetwarzane i dodawane do pliku XML:  
  
- Takie typy zdefiniowane przez użytkownika jako [Klasa](../keywords/class.md), [Delegat](../builtin-types/reference-types.md#the-delegate-type)lub [interfejs](../keywords/interface.md)  
  
- Takie elementy członkowskie jak pole, [zdarzenie](../keywords/event.md), [Właściwość](../../programming-guide/classes-and-structs/using-properties.md)lub metoda  
  
 Plik kodu źródłowego, który zawiera główny, jest wyprowadzany jako pierwszy w formacie XML.  
  
 Aby użyć wygenerowanego pliku XML do użycia z funkcją [IntelliSense](/visualstudio/ide/using-intellisense) , pozwól, aby nazwa pliku XML była taka sama jak zestaw, który ma być obsługiwany, a następnie upewnij się, że plik. XML znajduje się w tym samym katalogu, co zestaw. Z tego względu, gdy zestaw jest przywoływany w projekcie programu Visual Studio, można również znaleźć plik. XML. Zobacz [dostarczanie komentarzy do kodu](/visualstudio/ide/reference/generate-xml-documentation-comments) i aby uzyskać więcej informacji.  
  
 O ile nie zostanie skompilowany [element-target: module](./target-module-compiler-option.md), `file` program będzie zawierać \<assembly> \</assembly> Tagi określające nazwę pliku zawierającego manifest zestawu dla pliku wyjściowego kompilacji.  
  
> [!NOTE]
> Opcja-doc dotyczy wszystkich plików wejściowych; lub, jeśli jest ustawiony w ustawieniach projektu, wszystkie pliki w projekcie. Aby wyłączyć ostrzeżenia związane z komentarzami do dokumentacji dla określonego pliku lub sekcji kodu, użyj [#pragma ostrzeżenie](../preprocessor-directives/preprocessor-pragma-warning.md).  
  
 Zapoznaj się z [polecanymi tagami komentarzy do dokumentacji](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) , aby poznać sposoby generowania dokumentacji z komentarzy w kodzie.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij kartę **kompilacja** .  
  
3. Zmodyfikuj właściwość **pliku dokumentacji XML** .  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A> .  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
