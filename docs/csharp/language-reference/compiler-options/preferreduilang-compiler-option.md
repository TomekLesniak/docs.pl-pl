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
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="2d0a6-103">-preferreduilang (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="2d0a6-103">-preferreduilang (C# Compiler Options)</span></span>

<span data-ttu-id="2d0a6-104">Korzystając z `-preferreduilang` opcji kompilatora, można określić język, w którym kompilator języka C# wyświetla dane wyjściowe, takie jak komunikaty o błędach.</span><span class="sxs-lookup"><span data-stu-id="2d0a6-104">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d0a6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2d0a6-105">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d0a6-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="2d0a6-106">Arguments</span></span>  

 `language`  
 <span data-ttu-id="2d0a6-107">[Nazwa języka](/windows/desktop/Intl/language-names) języka do użycia dla danych wyjściowych kompilatora.</span><span class="sxs-lookup"><span data-stu-id="2d0a6-107">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d0a6-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2d0a6-108">Remarks</span></span>  

 <span data-ttu-id="2d0a6-109">Możesz użyć `-preferreduilang` opcji kompilatora, aby określić język, który ma być używany przez kompilator C# do komunikatów o błędach i innych danych wyjściowych wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="2d0a6-109">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="2d0a6-110">Jeśli nie zainstalowano pakietu językowego dla tego języka, zamiast niego zostanie użyte ustawienie język systemu operacyjnego i nie zostanie zgłoszony żaden błąd.</span><span class="sxs-lookup"><span data-stu-id="2d0a6-110">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="2d0a6-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2d0a6-111">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d0a6-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2d0a6-112">See also</span></span>

- [<span data-ttu-id="2d0a6-113">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="2d0a6-113">C# Compiler Options</span></span>](./index.md)
