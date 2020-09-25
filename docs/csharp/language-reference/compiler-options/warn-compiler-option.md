---
description: -warn (opcje kompilatora C#)
title: -warn (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: d59274423e6f9844d3ab22f3ac513ba1a05d7f07
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171354"
---
# <a name="-warn-c-compiler-options"></a>-warn (opcje kompilatora C#)

Opcja **-warn** określa poziom ostrzeżeń dla kompilatora, który ma być wyświetlany.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a>Argumenty  

 `option`  
 Poziom ostrzeżeń, który ma być wyświetlany dla kompilacji: niższe numery zawierają tylko ostrzeżenia o wysokiej ważności; wyższe liczby zawierają więcej ostrzeżeń. Wartość musi być równa zero lub dodatnia liczba całkowita:

|Poziom ostrzeżeń|Znaczenie|
|-------------------|-------------|
|0|Wyłącza emisję wszystkich komunikatów ostrzegawczych.|
|1|Wyświetla poważne komunikaty ostrzegawcze.|  
|2|Wyświetla ostrzeżenia poziomu 1 i pewne mniej surowe ostrzeżenia, takie jak ostrzeżenia dotyczące ukrywania elementów członkowskich klasy.|  
|3|Wyświetla ostrzeżenia poziomu 2 oraz pewne mniej surowe ostrzeżenia, takie jak ostrzeżenia dotyczące wyrażeń, które zawsze są oceniane do `true` lub `false` .|  
|4 (wartość domyślna)|Wyświetla wszystkie ostrzeżenia poziomu 3 i ostrzeżenia informacyjne.|
|5|Wyświetla ostrzeżenia poziomu 4 oraz [dodatkowe ostrzeżenia](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) z kompilatora dostarczonego z C# 9,0.|
|Większe niż 5|Każda wartość większa niż 5 będzie traktowana jako 5. Zwykle umieszcza się dowolne duże wartości (na przykład `9999` ), aby zawsze były wyświetlane ostrzeżenia, jeśli kompilator jest aktualizowany przy użyciu nowych poziomów ostrzeżeń.|
  
## <a name="remarks"></a>Uwagi  

 Aby uzyskać informacje o błędzie lub ostrzeżeniu, można wyszukać kod błędu w indeksie pomocy. Aby uzyskać informacje dotyczące błędu lub ostrzeżenia, zobacz [Błędy kompilatora języka C#](../compiler-messages/index.md).  
  
 Użyj opcji [-warnaserror —](./warnaserror-compiler-option.md) , aby traktować wszystkie ostrzeżenia jako błędy. Użyj [-nowarn](./nowarn-compiler-option.md) , aby wyłączyć niektóre ostrzeżenia.  
  
 **-w** jest krótką formą **-warn**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **kompilacja** .  
  
3. Zmodyfikuj właściwość **poziom ostrzeżeń** .  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A> .  
  
## <a name="example"></a>Przykład  

 Kompiluj `in.cs` i czy kompilator wyświetla tylko ostrzeżenia poziomu 1:  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
