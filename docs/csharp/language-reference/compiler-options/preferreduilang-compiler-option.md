---
description: -preferreduilang (opcje kompilatora C#)
title: -preferreduilang (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 490f5926fb50cfdae740b7749d72ea6c9a1f8cc9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193819"
---
# <a name="-preferreduilang-c-compiler-options"></a>-preferreduilang (opcje kompilatora C#)

Korzystając z `-preferreduilang` opcji kompilatora, można określić język, w którym kompilator języka C# wyświetla dane wyjściowe, takie jak komunikaty o błędach.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a>Argumenty  

 `language`  
 [Nazwa języka](/windows/desktop/Intl/language-names) języka do użycia dla danych wyjściowych kompilatora.  
  
## <a name="remarks"></a>Uwagi  

 Możesz użyć `-preferreduilang` opcji kompilatora, aby określić język, który ma być używany przez kompilator C# do komunikatów o błędach i innych danych wyjściowych wiersza polecenia. Jeśli nie zainstalowano pakietu językowego dla tego języka, zamiast niego zostanie użyte ustawienie język systemu operacyjnego i nie zostanie zgłoszony żaden błąd.  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>Wymagania  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
