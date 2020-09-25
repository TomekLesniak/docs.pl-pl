---
title: 'Porada: definiowanie stałych w języku C#'
description: Dowiedz się, jak definiować stałe w języku C#, które są polami, których wartości są ustawiane w czasie kompilacji. Użyj stałych, aby podać znaczące nazwy dla specjalnych wartości.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: dd8c6469c4d72da5588f0dce5314308bcc7e3b95
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91199123"
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="42b60-104">Jak definiować stałe w języku C\#</span><span class="sxs-lookup"><span data-stu-id="42b60-104">How to define constants in C\#</span></span>

<span data-ttu-id="42b60-105">Stałe są polami, których wartości są ustawiane w czasie kompilacji i nigdy nie mogą być zmieniane.</span><span class="sxs-lookup"><span data-stu-id="42b60-105">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="42b60-106">Użyj stałych, aby podać znaczące nazwy zamiast literałów liczbowych ("liczby magiczne") dla specjalnych wartości.</span><span class="sxs-lookup"><span data-stu-id="42b60-106">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42b60-107">W języku C# dyrektywa preprocesora [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) nie może służyć do definiowania stałych w sposób, który jest zazwyczaj używany w C i C++.</span><span class="sxs-lookup"><span data-stu-id="42b60-107">In C# the [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="42b60-108">Aby zdefiniować stałe wartości typów całkowitych ( `int` , `byte` , i tak dalej), użyj typu wyliczeniowego.</span><span class="sxs-lookup"><span data-stu-id="42b60-108">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="42b60-109">Aby uzyskać więcej informacji, zobacz [Wyliczenie](../../language-reference/builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="42b60-109">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="42b60-110">Aby zdefiniować niecałkowite stałe, jedno podejście polega na pogrupowania ich w pojedynczej klasie statycznej o nazwie `Constants` .</span><span class="sxs-lookup"><span data-stu-id="42b60-110">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="42b60-111">To wymaga, aby wszystkie odwołania do stałych były poprzedzone nazwą klasy, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="42b60-111">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42b60-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="42b60-112">Example</span></span>  

 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 <span data-ttu-id="42b60-113">Użycie kwalifikatora nazwy klasy pomaga upewnić się, że i inne osoby, które używają stałej, wiedzą, że jest stała i nie mogą być modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="42b60-113">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b60-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="42b60-114">See also</span></span>

- [<span data-ttu-id="42b60-115">Klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="42b60-115">Classes and Structs</span></span>](./index.md)
