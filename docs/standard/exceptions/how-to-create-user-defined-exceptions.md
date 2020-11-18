---
title: 'Porady: tworzenie wyjątków zdefiniowanych przez użytkownika'
description: Dowiedz się, jak utworzyć wyjątki zdefiniowane przez użytkownika, które są alternatywą dla hierarchii klas wyjątków pochodzących z klasy podstawowej wyjątku w programie .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
ms.openlocfilehash: b0a8549c9bacf322a0685c7b505185ab1d1101f6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828130"
---
# <a name="how-to-create-user-defined-exceptions"></a>Jak utworzyć wyjątki zdefiniowane przez użytkownika

Platforma .NET udostępnia hierarchię klas wyjątków ostatecznie pochodnych od klasy bazowej <xref:System.Exception> . Jeśli jednak żaden ze wstępnie zdefiniowanych wyjątków nie spełnia Twoich potrzeb, można utworzyć własne klasy wyjątków, wyprowadzając je z <xref:System.Exception> klasy.

Podczas tworzenia własnych wyjątków, należy zakończyć nazwę klasy wyjątku zdefiniowanego przez użytkownika z wyrazem "Exception" i zaimplementować trzy typowe konstruktory, jak pokazano w poniższym przykładzie. W przykładzie zdefiniowano nową klasę wyjątku o nazwie `EmployeeListNotFoundException` . Klasa pochodzi od <xref:System.Exception> i zawiera trzy konstruktory.

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> W sytuacjach, gdy używasz komunikacji zdalnej, należy upewnić się, że metadane dla wszystkich wyjątków zdefiniowanych przez użytkownika są dostępne na serwerze (wywoływanym) i na kliencie (obiekt serwera proxy lub wywołujący). Aby uzyskać więcej informacji, zobacz [najlepsze rozwiązania dotyczące wyjątków](best-practices-for-exceptions.md).

## <a name="see-also"></a>Zobacz także

- [Wyjątki](index.md)
