---
title: Podstawowe operacje na ciągach w programie .NET
description: Zapoznaj się z podstawowymi operacjami, które można wykonywać na ciągach.
ms.date: 03/30/2017
helpviewer_keywords:
- strings [.NET], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 30f325a414e0912086b5d36630e77ea754db4956
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825133"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="de078-103">Podstawowe operacje na ciągach w programie .NET</span><span class="sxs-lookup"><span data-stu-id="de078-103">Basic string operations in .NET</span></span>

<span data-ttu-id="de078-104">Aplikacje często odpowiadają użytkownikom przez konstruowanie komunikatów na podstawie danych wejściowych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="de078-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="de078-105">Na przykład nie jest to zdarza się, aby witryny sieci Web odpowiadały nowo zalogowanemu użytkownikowi z wyspecjalizowanym powitaniem zawierającym nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="de078-105">For example, it is not uncommon for websites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span>

<span data-ttu-id="de078-106">Kilka metod w <xref:System.String?displayProperty=nameWithType> <xref:System.Text.StringBuilder?displayProperty=nameWithType> klasach i pozwala na dynamiczne konstruowanie ciągów niestandardowych do wyświetlania w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="de078-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="de078-107">Te metody ułatwiają również wykonywanie wielu podstawowych operacji na ciągach, takich jak tworzenie nowych ciągów z tablic bajtów, porównywanie wartości ciągów i modyfikowanie istniejących ciągów.</span><span class="sxs-lookup"><span data-stu-id="de078-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="related-sections"></a><span data-ttu-id="de078-108">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="de078-108">Related sections</span></span>

<span data-ttu-id="de078-109">[Konwersja typów w programie .NET](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="de078-109">[Type Conversion in .NET](type-conversion.md)</span></span>\
<span data-ttu-id="de078-110">Opisuje sposób konwersji jednego typu na inny typ.</span><span class="sxs-lookup"><span data-stu-id="de078-110">Describes how to convert one type into another type.</span></span>

<span data-ttu-id="de078-111">[Formatowanie typów](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="de078-111">[Formatting Types](formatting-types.md)</span></span>\
<span data-ttu-id="de078-112">Opisuje sposób formatowania ciągów przy użyciu specyfikatorów formatu.</span><span class="sxs-lookup"><span data-stu-id="de078-112">Describes how to format strings using format specifiers.</span></span>
