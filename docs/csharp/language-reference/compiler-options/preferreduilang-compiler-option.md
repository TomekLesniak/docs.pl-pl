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
ms.openlocfilehash: f68652e910651ab5c4184376d9eb7729303382d9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124854"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="0530b-103">-preferreduilang (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="0530b-103">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="0530b-104">Korzystając z `-preferreduilang` opcji kompilatora, można określić język, w którym kompilator języka C# wyświetla dane wyjściowe, takie jak komunikaty o błędach.</span><span class="sxs-lookup"><span data-stu-id="0530b-104">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0530b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0530b-105">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="0530b-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="0530b-106">Arguments</span></span>  
 `language`  
 <span data-ttu-id="0530b-107">[Nazwa języka](/windows/desktop/Intl/language-names) języka do użycia dla danych wyjściowych kompilatora.</span><span class="sxs-lookup"><span data-stu-id="0530b-107">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0530b-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0530b-108">Remarks</span></span>  
 <span data-ttu-id="0530b-109">Możesz użyć `-preferreduilang` opcji kompilatora, aby określić język, który ma być używany przez kompilator C# do komunikatów o błędach i innych danych wyjściowych wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="0530b-109">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="0530b-110">Jeśli nie zainstalowano pakietu językowego dla tego języka, zamiast niego zostanie użyte ustawienie język systemu operacyjnego i nie zostanie zgłoszony żaden błąd.</span><span class="sxs-lookup"><span data-stu-id="0530b-110">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="0530b-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0530b-111">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0530b-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0530b-112">See also</span></span>

- [<span data-ttu-id="0530b-113">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="0530b-113">C# Compiler Options</span></span>](./index.md)
