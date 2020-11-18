---
title: 'Instrukcje: zapisywanie i odczytywanie wiadomości z bloku przepływu danych'
ms.date: 09/10/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
ms.openlocfilehash: be0e78989105cc59bd041ceb8c6f31073a702f83
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820790"
---
# <a name="how-to-write-and-read-messages-from-a-dataflow-block"></a>Instrukcje: zapisywanie i odczytywanie wiadomości z bloku przepływu danych

W tym artykule opisano sposób używania biblioteki TPL (Task Parallel Library) przepływu danych do zapisywania komunikatów do i odczytywania wiadomości z bloku przepływu danych. Biblioteka TPL przepływu danych zapewnia metody synchroniczne i asynchroniczne do pisania komunikatów i odczytywania komunikatów z bloku przepływu danych. W tym artykule pokazano, jak używać <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> klasy. <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>Klasa buforuje komunikaty i zachowuje się zarówno jako źródło komunikatu, jak i obiekt docelowy wiadomości.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-and-reading-synchronously"></a>Zapisywanie i odczytywanie synchroniczne

Poniższy przykład używa <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> metody do zapisu w <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> bloku przepływu danych i <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> metody odczytu z tego samego obiektu.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="2":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="2":::

Można również użyć <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> metody do odczytu z bloku przepływu danych, jak pokazano w poniższym przykładzie. <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>Metoda nie blokuje bieżącego wątku i jest przydatna, gdy okresowo sondowasz o dane.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="3":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="3":::

Ponieważ <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> Metoda działa synchronicznie, <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> obiekt w poprzednich przykładach odbiera wszystkie dane, zanim Druga pętla odczytuje dane. Poniższy przykład rozszerza pierwszy przykład przy użyciu, <xref:System.Threading.Tasks.Task.WhenAll(System.Threading.Tasks.Task[])?displayProperty=nameWithType> aby odczytywać i zapisywać w bloku komunikatów współbieżnie. Ponieważ <xref:System.Threading.Tasks.Task.WhenAll%2A> wykonuje akcje współbieżnie, wartości nie są zapisywane do <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> obiektu w żadnej określonej kolejności.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="4":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="4":::

## <a name="writing-and-reading-asynchronously"></a>Zapisywanie i odczytywanie asynchronicznie

Poniższy przykład używa <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> metody do asynchronicznego zapisu do <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> obiektu i <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> metody do asynchronicznego odczytu z tego samego obiektu. W tym przykładzie zastosowano operatory [Async](../../csharp/language-reference/keywords/async.md) i [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) i [await](../../visual-basic/language-reference/operators/await-operator.md) w Visual Basic), aby asynchronicznie wysyłać dane do i odczytywać dane z bloku docelowego. <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A>Metoda jest przydatna, gdy konieczne jest włączenie bloku przepływu danych w celu odłożenia komunikatów. <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A>Metoda jest przydatna, gdy chcesz działać na danych, gdy dane staną się dostępne. Aby uzyskać więcej informacji na temat sposobu propagowania komunikatów między blokami komunikatów, zobacz sekcję przekazywanie komunikatu w [przepływu danych](dataflow-task-parallel-library.md).

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="5":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="5":::

## <a name="a-complete-example"></a>Kompletny przykład

Poniższy przykład pokazuje cały kod dla tego artykułu.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="1":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="1":::

## <a name="next-steps"></a>Następne kroki

Ten przykład pokazuje, jak odczytywać i zapisywać bezpośrednio w bloku komunikatów. Można również połączyć bloki przepływu danych z *potokami*, które są sekwencjami liniowymi bloków przepływu danych lub *sieci*, które są wykresami bloków przepływu danych. W potoku lub sieci źródła asynchronicznie propagują dane do obiektów docelowych, ponieważ te dane staną się dostępne. Aby uzyskać przykład, który tworzy podstawowy potok przepływu danych, zobacz [Przewodnik: Tworzenie potoku przepływu danych](walkthrough-creating-a-dataflow-pipeline.md). Aby uzyskać przykład, który tworzy bardziej złożoną sieć przepływu danych, zobacz [Przewodnik: używanie przepływu danych w aplikacji Windows Forms](walkthrough-using-dataflow-in-a-windows-forms-application.md).

## <a name="see-also"></a>Zobacz także

- [Przepływ danych (Biblioteka zadań równoległych)](dataflow-task-parallel-library.md)
