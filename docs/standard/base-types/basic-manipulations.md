---
title: Podstawowe operacje na ciągach w programie .NET
description: Zobacz przykład, który wywołuje wiele metod String.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: e3e969520e068bde234c13d45ad790b76ecf8fdb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825160"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a><span data-ttu-id="1ce85-103">Instrukcje: wykonywanie podstawowych operacji na ciągach w programie .NET</span><span class="sxs-lookup"><span data-stu-id="1ce85-103">How to: Perform Basic String Manipulations in .NET</span></span>

<span data-ttu-id="1ce85-104">W poniższym przykładzie zastosowano niektóre metody omówione w temacie [podstawowe operacje na ciągach](basic-string-operations.md) w celu skonstruowania klasy służącej do manipulowania ciągami w sposób, który może znajdować się w rzeczywistej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1ce85-104">The following example uses some of the methods discussed in the [Basic String Operations](basic-string-operations.md) topics to construct a class that performs string manipulations in a manner that might be found in a real-world application.</span></span> <span data-ttu-id="1ce85-105">`MailToData`Klasa przechowuje nazwę i adres osoby w osobnych właściwościach i umożliwia łączenie `City` `State` pól, i w postaci `Zip` pojedynczego ciągu do wyświetlania użytkownikowi.</span><span class="sxs-lookup"><span data-stu-id="1ce85-105">The `MailToData` class stores the name and address of an individual in separate properties and provides a way to combine the `City`, `State`, and `Zip` fields into a single string for display to the user.</span></span> <span data-ttu-id="1ce85-106">Ponadto Klasa umożliwia użytkownikowi wprowadzanie informacji o miejscowości, stanie i kodzie pocztowym jako jednego ciągu.</span><span class="sxs-lookup"><span data-stu-id="1ce85-106">Furthermore, the class allows the user to enter the city, state, and zip code information as a single string.</span></span> <span data-ttu-id="1ce85-107">Aplikacja automatycznie analizuje pojedynczy ciąg i wprowadza odpowiednie informacje do odpowiedniej właściwości.</span><span class="sxs-lookup"><span data-stu-id="1ce85-107">The application automatically parses the single string and enters the proper information into the corresponding property.</span></span>

<span data-ttu-id="1ce85-108">Dla uproszczenia w tym przykładzie użyto aplikacji konsolowej z interfejsem wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="1ce85-108">For simplicity, this example uses a console application with a command-line interface.</span></span>

## <a name="example"></a><span data-ttu-id="1ce85-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="1ce85-109">Example</span></span>

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]

<span data-ttu-id="1ce85-110">Gdy poprzedni kod jest wykonywany, użytkownik zostanie poproszony o wprowadzenie nazwy i adresu.</span><span class="sxs-lookup"><span data-stu-id="1ce85-110">When the preceding code is executed, the user is asked to enter their name and address.</span></span> <span data-ttu-id="1ce85-111">Aplikacja umieszcza informacje w odpowiednich właściwościach i wyświetla informacje z powrotem do użytkownika, tworząc pojedynczy ciąg, który wyświetla miasto, Województwo i informacje o kodzie pocztowym.</span><span class="sxs-lookup"><span data-stu-id="1ce85-111">The application places the information in the appropriate properties and displays the information back to the user, creating a single string that displays the city, state, and zip code information.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ce85-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1ce85-112">See also</span></span>

- [<span data-ttu-id="1ce85-113">Podstawowe operacje na ciągach</span><span class="sxs-lookup"><span data-stu-id="1ce85-113">Basic String Operations</span></span>](basic-string-operations.md)
