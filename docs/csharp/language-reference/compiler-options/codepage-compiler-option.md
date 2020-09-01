---
description: -CodePage (opcje kompilatora C#)
title: -CodePage (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 4c812314ed9c1abcd7d2f34b2281140175621312
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125959"
---
# <a name="-codepage-c-compiler-options"></a>-CodePage (opcje kompilatora C#)
Ta opcja określa, która strona kodowa ma być używana podczas kompilacji, jeśli wymagana Strona nie jest bieżącą domyślną stroną kodową systemu.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumenty  
 `id`  
 Identyfikator strony kodowej, który ma być używany dla wszystkich plików kodu źródłowego w kompilacji.  
  
## <a name="remarks"></a>Uwagi  
 Kompilator spróbuje najpierw zinterpretować wszystkie pliki źródłowe jako UTF-8. Jeśli pliki kodu źródłowego są w kodowaniu innym niż UTF-8 i są używane znaki inne niż 7-bitowe znaki ASCII, użyj opcji **-CodePage** , aby określić, która strona kodowa powinna być używana. **-CodePage** stosuje się do wszystkich plików kodu źródłowego w kompilacji.  

 Zobacz [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) , aby uzyskać informacje na temat sposobu znajdowania, które strony kodowe są obsługiwane w systemie.  
  
 Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
