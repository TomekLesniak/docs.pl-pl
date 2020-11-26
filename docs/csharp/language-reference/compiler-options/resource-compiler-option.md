---
description: -Resource (opcje kompilatora C#)
title: -Resource (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: 6f90ce6c1590784cefbd5f15ca8a36941aad77ed
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193780"
---
# <a name="-resource-c-compiler-options"></a>-Resource (opcje kompilatora C#)

Osadza określony zasób w pliku wyjściowym.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argumenty  

 `filename`  
 Plik zasobów platformy .NET, który ma zostać osadzony w pliku wyjściowym.  
  
 `identifier` (opcjonalnie)  
 Nazwa logiczna zasobu; Nazwa, która jest używana do ładowania zasobu. Wartość domyślna to nazwa pliku.  
  
 `accessibility-modifier` (opcjonalnie)  
 Dostępność zasobu: Public lub Private. Wartość domyślna to Public.  
  
## <a name="remarks"></a>Uwagi  

 Użyj polecenia [-linkresource —](./linkresource-compiler-option.md) , aby połączyć zasób z zestawem, a nie dodać pliku zasobów do pliku wyjściowego.  
  
 Domyślnie zasoby są publiczne w zestawie, gdy są tworzone przy użyciu kompilatora języka C#. Aby udostępnić zasoby jako prywatne, określ `private` jako modyfikator dostępności. Żadna inna dostępność jest inna niż `public` lub `private` niedozwolona.  
  
 Jeśli `filename` plik zasobów platformy .NET został utworzony na przykład przez [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) lub w środowisku programistycznym, dostęp do niego można uzyskać za pomocą elementów członkowskich w <xref:System.Resources> przestrzeni nazw. Aby uzyskać więcej informacji, zobacz <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. W przypadku wszystkich innych zasobów Użyj `GetManifestResource` metod w klasie, <xref:System.Reflection.Assembly> Aby uzyskać dostęp do zasobu w czasie wykonywania.  
  
 **-res** to krótka forma **zasobu**.  
  
 Kolejność zasobów w pliku wyjściowym jest określana na podstawie kolejności określonej w wierszu polecenia.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Dodaj plik zasobów do projektu.  
  
2. Wybierz plik, który ma zostać osadzony w **Eksplorator rozwiązań**.  
  
3. Wybierz pozycję **Akcja kompilacji** dla pliku w oknie **Właściwości** .  
  
4. Ustaw **akcję kompilacji** na **zasób osadzony**.  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.FileProperties2.BuildAction%2A> .  
  
## <a name="example"></a>Przykład  

 Kompiluj `in.cs` i Dołącz plik zasobu `rf.resource` :  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
