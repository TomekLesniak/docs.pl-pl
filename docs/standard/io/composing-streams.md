---
title: Tworzenie strumieni
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
ms.openlocfilehash: d848a989378ed40df794554f3a0a9a7f135fbd4e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732193"
---
# <a name="compose-streams"></a><span data-ttu-id="a3167-102">Tworzenie strumieni</span><span class="sxs-lookup"><span data-stu-id="a3167-102">Compose streams</span></span>

<span data-ttu-id="a3167-103">*Magazyn zapasowy* jest nośnikiem magazynującym, takim jak dysk lub pamięć.</span><span class="sxs-lookup"><span data-stu-id="a3167-103">A *backing store* is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="a3167-104">Każdy inny magazyn zapasowy implementuje swój własny strumień jako implementację <xref:System.IO.Stream> klasy.</span><span class="sxs-lookup"><span data-stu-id="a3167-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span>

<span data-ttu-id="a3167-105">Każdy typ strumienia odczytuje i zapisuje bajty z i do danego magazynu zapasowego.</span><span class="sxs-lookup"><span data-stu-id="a3167-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="a3167-106">Strumienie łączące się z magazynami zapasowymi są nazywane *strumieniami podstawowymi*.</span><span class="sxs-lookup"><span data-stu-id="a3167-106">Streams that connect to backing stores are called *base streams*.</span></span> <span data-ttu-id="a3167-107">Strumienie podstawowe mają konstruktory z parametrami niezbędnymi do połączenia strumienia z magazynem zapasowym.</span><span class="sxs-lookup"><span data-stu-id="a3167-107">Base streams have constructors with the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="a3167-108">Na przykład <xref:System.IO.FileStream> ma konstruktory, które określają parametr path, który określa sposób, w jaki plik będzie współużytkowany przez procesy.</span><span class="sxs-lookup"><span data-stu-id="a3167-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes.</span></span>  

<span data-ttu-id="a3167-109">Projekt <xref:System.IO> klas zawiera uproszczoną kompozycję strumienia.</span><span class="sxs-lookup"><span data-stu-id="a3167-109">The design of the <xref:System.IO> classes provides simplified stream composition.</span></span> <span data-ttu-id="a3167-110">Można dołączyć strumienie podstawowe do co najmniej jednego strumienia przekazującego, który zapewnia odpowiednie funkcje.</span><span class="sxs-lookup"><span data-stu-id="a3167-110">You can attach base streams to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="a3167-111">Do końca łańcucha można dołączyć czytelnika lub moduł zapisujący, dzięki czemu preferowane typy mogą być łatwo odczytywane lub zapisywane.</span><span class="sxs-lookup"><span data-stu-id="a3167-111">You can attach a reader or writer to the end of the chain, so the preferred types can be read or written easily.</span></span>  

<span data-ttu-id="a3167-112">Poniższy przykład kodu tworzy element **FILESTREAM** wokół istniejącego *MyFile.txt* w celu buforowania *MyFile.txt*.</span><span class="sxs-lookup"><span data-stu-id="a3167-112">The following code examples create a **FileStream** around the existing *MyFile.txt* in order to buffer *MyFile.txt*.</span></span> <span data-ttu-id="a3167-113">Należy pamiętać, że **FILESTREAM** domyślnie są buforowane.</span><span class="sxs-lookup"><span data-stu-id="a3167-113">Note that **FileStreams** are buffered by default.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a3167-114">W przykładach założono, że plik o nazwie *MyFile.txt* już istnieje w tym samym folderze, w którym znajduje się aplikacja.</span><span class="sxs-lookup"><span data-stu-id="a3167-114">The examples assume that a file named *MyFile.txt* already exists in the same folder as the app.</span></span>  

## <a name="example-use-streamreader"></a><span data-ttu-id="a3167-115">Przykład: Użyj StreamReader</span><span class="sxs-lookup"><span data-stu-id="a3167-115">Example: Use StreamReader</span></span>

<span data-ttu-id="a3167-116">Poniższy przykład tworzy <xref:System.IO.StreamReader> do odczytu znaki z **FILESTREAM**, które są przesyłane do **StreamReader** jako argument konstruktora.</span><span class="sxs-lookup"><span data-stu-id="a3167-116">The following example creates a <xref:System.IO.StreamReader> to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="a3167-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> następnie odczytuje do momentu <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> znalezienia nie więcej znaków.</span><span class="sxs-lookup"><span data-stu-id="a3167-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> then reads until <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> finds no more characters.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a><span data-ttu-id="a3167-118">Przykład: Użyj BinaryReader</span><span class="sxs-lookup"><span data-stu-id="a3167-118">Example: Use BinaryReader</span></span>

<span data-ttu-id="a3167-119">Poniższy przykład tworzy <xref:System.IO.BinaryReader> do odczytu bajtów z **FILESTREAM**, który jest przesyłany do **BinaryReader** jako argument konstruktora.</span><span class="sxs-lookup"><span data-stu-id="a3167-119">The following example creates a <xref:System.IO.BinaryReader> to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="a3167-120"><xref:System.IO.BinaryReader.ReadByte%2A> następnie odczytuje do momentu <xref:System.IO.BinaryReader.PeekChar%2A> znalezienia braku więcej bajtów.</span><span class="sxs-lookup"><span data-stu-id="a3167-120"><xref:System.IO.BinaryReader.ReadByte%2A> then reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="a3167-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a3167-121">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
