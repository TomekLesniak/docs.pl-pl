---
title: 'Instrukcje: inicjowanie zmiennej tablicy'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 1add054a6cb6468f4581f92ca3a258c5b0cdc77d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058862"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a><span data-ttu-id="f5ac3-102">Porady: inicjowanie zmiennej tablicy w języku Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5ac3-102">How to: Initialize an Array Variable in Visual Basic</span></span>

<span data-ttu-id="f5ac3-103">Można zainicjować zmienną tablicową przez uwzględnienie literału tablicy w `New` klauzuli i określenie wartości początkowych tablicy.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-103">You initialize an array variable by including an array literal in a `New` clause and specifying the initial values of the array.</span></span> <span data-ttu-id="f5ac3-104">Można określić typ lub zezwolić na wywnioskowanie go na podstawie wartości w literale tablicy.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-104">You can either specify the type or allow it to be inferred from the values in the array literal.</span></span> <span data-ttu-id="f5ac3-105">Aby uzyskać więcej informacji na temat sposobu wywnioskowania typu, zobacz "zapełnianie tablicy wartościami początkowymi" w [tablicach](index.md).</span><span class="sxs-lookup"><span data-stu-id="f5ac3-105">For more information about how the type is inferred, see "Populating an Array with Initial Values" in [Arrays](index.md).</span></span>  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a><span data-ttu-id="f5ac3-106">Aby zainicjować zmienną tablicową przy użyciu literału tablicowego</span><span class="sxs-lookup"><span data-stu-id="f5ac3-106">To initialize an array variable by using an array literal</span></span>  
  
- <span data-ttu-id="f5ac3-107">W `New` klauzuli lub po przypisaniu wartości tablicy podaj wartości elementów w nawiasach klamrowych ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="f5ac3-107">Either in the `New` clause, or when you assign the array value, supply the element values inside braces (`{}`).</span></span> <span data-ttu-id="f5ac3-108">W poniższym przykładzie przedstawiono kilka sposobów deklarowania, tworzenia i inicjowania zmiennej, która zawiera tablicę z elementami typu `Char` .</span><span class="sxs-lookup"><span data-stu-id="f5ac3-108">The following example shows several ways to declare, create, and initialize a variable to contain an array that has elements of type `Char`.</span></span>  
  
     [!code-vb[VbVbalrArrays#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#16)]  
  
     <span data-ttu-id="f5ac3-109">Po wykonaniu każdej instrukcji Utworzona tablica ma długość 3, z elementami w indeksie od 0 do indeksu 2 zawierającego wartości początkowe.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-109">After each statement executes, the array that's created has a length of 3, with elements at index 0 through index 2 containing the initial values.</span></span> <span data-ttu-id="f5ac3-110">Jeśli podasz górną granicę i wartości, musisz dołączyć wartość dla każdego elementu z indeksu od 0 do górnej granicy.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-110">If you supply both the upper bound and the values, you must include a value for every element from index 0 through the upper bound.</span></span>  
  
     <span data-ttu-id="f5ac3-111">Należy zauważyć, że nie ma potrzeby określania górnej granicy indeksu, jeśli podasz wartości elementów w literale tablicowym.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-111">Notice that you do not have to specify the index upper bound if you supply element values in an array literal.</span></span> <span data-ttu-id="f5ac3-112">Jeśli nie określono górnej granicy, rozmiar tablicy jest wywnioskowany na podstawie liczby wartości w literale tablicy.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-112">If no upper bound is specified, the size of the array is inferred based on the number of values in the array literal.</span></span>  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a><span data-ttu-id="f5ac3-113">Aby zainicjować wielowymiarową zmienną tablicową przy użyciu literałów tablicy</span><span class="sxs-lookup"><span data-stu-id="f5ac3-113">To initialize a multidimensional array variable by using array literals</span></span>  
  
- <span data-ttu-id="f5ac3-114">Zagnieżdżaj wartości w nawiasach klamrowych ( `{}` ) w nawiasach klamrowych.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-114">Nest values inside braces (`{}`) within braces.</span></span> <span data-ttu-id="f5ac3-115">Upewnij się, że zagnieżdżona tablica literałów wszystkie wnioskowanie jako tablice tego samego typu i długości.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-115">Ensure that the nested array literals all infer as arrays of the same type and length.</span></span> <span data-ttu-id="f5ac3-116">Poniższy przykład kodu pokazuje kilka przykładów inicjalizacji tablicy wielowymiarowej.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-116">The following code example shows several examples of multidimensional array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#17)]  
  
- <span data-ttu-id="f5ac3-117">Można jawnie określić granice tablicy lub pozostawić je, a kompilator wywnioskuje granice tablicy na podstawie wartości w literale tablicy.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-117">You can explicitly specify the array bounds, or leave them out and have the compiler infer the array bounds based on the values in the array literal.</span></span> <span data-ttu-id="f5ac3-118">Jeśli podasz górną granicę i wartości, musisz dołączyć wartość dla każdego elementu z indeksu od 0 do górnej granicy w każdym wymiarze.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-118">If you supply both the upper bounds and the values, you must include a value for every element from index 0 through the upper bound in every dimension.</span></span> <span data-ttu-id="f5ac3-119">W poniższym przykładzie przedstawiono kilka sposobów deklarowania, tworzenia i inicjowania zmiennej, która zawiera dwuwymiarową tablicę, która zawiera elementy typu `Short`</span><span class="sxs-lookup"><span data-stu-id="f5ac3-119">The following example shows several ways to declare, create, and initialize a variable to contain a two-dimensional array that has elements of type `Short`</span></span>  
  
     [!code-vb[VbVbalrArrays#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#18)]  
  
     <span data-ttu-id="f5ac3-120">Po wykonaniu każdej instrukcji Utworzona tablica zawiera sześć zainicjowanych elementów, które mają indeksy `(0,0)` , `(0,1)` , `(0,2)` ,, `(1,0)` `(1,1)` i `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="f5ac3-120">After each statement executes, the created array contains six initialized elements that have indexes `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, and `(1,2)`.</span></span> <span data-ttu-id="f5ac3-121">Każda lokalizacja tablicy zawiera wartość `10` .</span><span class="sxs-lookup"><span data-stu-id="f5ac3-121">Each array location contains the value `10`.</span></span>  
  
- <span data-ttu-id="f5ac3-122">Poniższy przykład wykonuje iterację przez tablicę wielowymiarową.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-122">The following example iterates through a multidimensional array.</span></span> <span data-ttu-id="f5ac3-123">W aplikacji konsolowej systemu Windows, która jest zapisywana w Visual Basic, wklej kod wewnątrz `Sub Main()` metody.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-123">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span> <span data-ttu-id="f5ac3-124">Ostatnie komentarze zawierają dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-124">The last comments show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#31)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a><span data-ttu-id="f5ac3-125">Aby zainicjować nieregularną zmienną tablicową przy użyciu literałów tablicy</span><span class="sxs-lookup"><span data-stu-id="f5ac3-125">To initialize a jagged array variable by using array literals</span></span>  
  
- <span data-ttu-id="f5ac3-126">Zagnieżdżaj wartości obiektów wewnątrz nawiasów klamrowych ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="f5ac3-126">Nest object values inside braces (`{}`).</span></span> <span data-ttu-id="f5ac3-127">Chociaż można zagnieżdżać literały tablicowe, które określają tablice o różnych długościach, w przypadku tablicy nieregularnej, należy się upewnić, że zagnieżdżone literały tablicowe są ujęte w nawiasy ( `()` ).</span><span class="sxs-lookup"><span data-stu-id="f5ac3-127">Although you can also nest array literals that specify arrays of different lengths, in the case of a jagged array, make sure that the nested array literals are enclosed in parentheses (`()`).</span></span> <span data-ttu-id="f5ac3-128">Nawiasy wymuszają Obliczanie zagnieżdżonych literałów tablicowych, a wyniki tablic są używane jako początkowe wartości tablicy nieregularnej.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-128">The parentheses force the evaluation of the nested array literals, and the resulting arrays are used as the initial values of the jagged array.</span></span> <span data-ttu-id="f5ac3-129">Poniższy przykład kodu przedstawia dwa przykłady inicjalizacji tablicy nieregularnej.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-129">The following code example shows two examples of jagged array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#19)]  
  
- <span data-ttu-id="f5ac3-130">Poniższy przykład wykonuje iterację przez tablicę nieregularną.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-130">The following example iterates through a jagged array.</span></span> <span data-ttu-id="f5ac3-131">W aplikacji konsolowej systemu Windows, która jest zapisywana w Visual Basic, wklej kod wewnątrz `Sub Main()` metody.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-131">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span>  <span data-ttu-id="f5ac3-132">Ostatnie komentarze w kodzie przedstawiają dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="f5ac3-132">The last comments in the code show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="f5ac3-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f5ac3-133">See also</span></span>

- [<span data-ttu-id="f5ac3-134">Tablice</span><span class="sxs-lookup"><span data-stu-id="f5ac3-134">Arrays</span></span>](index.md)
- [<span data-ttu-id="f5ac3-135">Rozwiązywanie problemów związanych z tablicami</span><span class="sxs-lookup"><span data-stu-id="f5ac3-135">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
