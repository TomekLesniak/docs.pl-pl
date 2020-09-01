---
description: -bugreport (opcje kompilatora C#)
title: -bugreport (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 2c358b2dda400f6077ffb5ba1dfc8e6e1127fa52
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125998"
---
# <a name="-bugreport-c-compiler-options"></a>-bugreport (opcje kompilatora C#)
Określa, że informacje debugowania należy umieścić w pliku do późniejszej analizy.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a>Argumenty  
 `file`  
 Nazwa pliku, który ma zawierać raport o błędach.  
  
## <a name="remarks"></a>Uwagi  
 Opcja **-bugreport** określa, że należy umieścić następujące informacje `file` :  
  
- Kopia wszystkich plików kodu źródłowego w kompilacji.  
  
- Lista opcji kompilatora używanych w kompilacji.  
  
- Informacje o wersji dotyczące kompilatora, czasu wykonywania i systemu operacyjnego.  
  
- Przywoływane zestawy i moduły, zapisane w postaci cyfr szesnastkowych, z wyjątkiem zestawów, które są dostarczane z .NET Framework i zestawem SDK.  
  
- Dane wyjściowe kompilatora, jeśli istnieją.  
  
- Opis problemu, dla którego zostanie wyświetlony monit.  
  
- Opis sposobu, w jaki sądzisz, że problem powinien zostać naprawiony, zostanie wyświetlony monit.  
  
 Jeśli ta opcja jest używana z poleceniem **-errorReport: Prompt** lub **-errorReport: Send**, informacje w pliku będą wysyłane do firmy Microsoft Corporation.  
  
 Ze względu na to, że kopia wszystkich plików kodu źródłowego zostanie umieszczona w programie `file` , może być konieczne odtworzenie podejrzanej wady kodu w najkrótszym możliwym programie.  
  
 Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.  
  
 Zauważ, że zawartość wygenerowanego pliku uwidacznia kod źródłowy, który może spowodować nieumyślne ujawnienie informacji.  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [-errorreport (opcje kompilatora C#)](./errorreport-compiler-option.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
