---
title: Jak wywołać procedurę obsługi zdarzeń
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
no-loc:
- WithEvents
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3762c79dd3d883ae2ccfe76b335cf98ac87d4246
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89464964"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Jak wywołać procedurę obsługi zdarzeń w Visual Basic

*Zdarzenie* jest akcją lub wystąpieniem, takim jak kliknięcie myszą lub Przekroczono limit środków, który jest rozpoznawany przez jakiś składnik programu i dla którego można napisać kod, aby odpowiedzieć. *Program obsługi zdarzeń* to kod, który można napisać, aby odpowiedzieć na zdarzenie.

Procedura obsługi zdarzeń w Visual Basic jest `Sub` procedurą. Nie jest to jednak zazwyczaj wywoływana w taki sam sposób jak w przypadku innych `Sub` procedur. Zamiast tego należy zidentyfikować procedurę jako program obsługi zdarzenia. Można to zrobić za pomocą [`Handles`](../../../language-reference/statements/handles-clause.md) klauzuli i [`WithEvents`](../../../language-reference/modifiers/withevents.md) zmiennej lub z [instrukcją AddHandler](../../../language-reference/statements/addhandler-statement.md). Użycie `Handles` klauzuli jest domyślnym sposobem deklarowania procedury obsługi zdarzeń w Visual Basic. Jest to sposób, w jaki programy obsługi zdarzeń są zapisywane przez projektantów podczas programowania w zintegrowanym środowisku programistycznym (IDE). `AddHandler`Instrukcja jest odpowiednia do dynamicznego wywoływania zdarzeń w czasie wykonywania.

Gdy wystąpi zdarzenie, Visual Basic automatycznie wywołuje procedurę obsługi zdarzeń. Każdy kod, który ma dostęp do zdarzenia może być spowodowany przez wykonanie [instrukcji RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).

Można skojarzyć więcej niż jeden program obsługi zdarzeń z tym samym zdarzeniem. W niektórych przypadkach można usunąć skojarzenie procedury obsługi ze zdarzenia. Aby uzyskać więcej informacji, zobacz [zdarzenia](../events/index.md).

## <a name="call-an-event-handler-using-no-loc-texthandles-and-no-locwithevents"></a>Wywoływanie procedury obsługi zdarzeń przy użyciu :::no-loc text="Handles"::: i WithEvents

1. Upewnij się, że zdarzenie jest zadeklarowane za pomocą [instrukcji zdarzenia](../../../language-reference/statements/event-statement.md).

2. Zadeklaruj zmienną obiektu na poziomie modułu lub klasy przy użyciu [`WithEvents`](../../../language-reference/modifiers/withevents.md) słowa kluczowego. `As`Klauzula dla tej zmiennej musi określać klasę, która wywołuje zdarzenie.

3. W deklaracji procedury obsługi zdarzeń `Sub` Dodaj [`Handles`](../../../language-reference/statements/handles-clause.md) klauzulę, która określa `WithEvents` zmienną i nazwę zdarzenia.

4. Gdy wystąpi zdarzenie, Visual Basic automatycznie wywoła `Sub` procedurę. Kod może użyć instrukcji, `RaiseEvent` aby wystąpiło zdarzenie.

    W poniższym przykładzie zdefiniowano zdarzenie i `WithEvents` zmienną, która odwołuje się do klasy, która wywołuje zdarzenie. Procedura obsługi zdarzeń `Sub` używa `Handles` klauzuli do określenia klasy i zdarzenia, które obsługuje.

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="4":::

## <a name="call-an-event-handler-using-addhandler"></a>Wywoływanie procedury obsługi zdarzeń przy użyciu elementu AddHandler

1. Upewnij się, że zdarzenie jest zadeklarowane za pomocą `Event` instrukcji.

2. Wykonaj [instrukcję AddHandler](../../../language-reference/statements/addhandler-statement.md) , aby dynamicznie połączyć procedurę obsługi zdarzeń `Sub` ze zdarzeniem.

3. Gdy wystąpi zdarzenie, Visual Basic automatycznie wywoła `Sub` procedurę. Kod może użyć instrukcji, `RaiseEvent` aby wystąpiło zdarzenie.

    Poniższy przykład używa [instrukcji AddHandler](../../../language-reference/statements/addhandler-statement.md) w konstruktorze, aby skojarzyć `OnFormClosing` procedurę jako procedurę obsługi zdarzeń dla <xref:System.Windows.Forms.Form.FormClosing> .

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="5":::

    Można usunąć skojarzenie programu obsługi zdarzeń ze zdarzenia przez wykonanie [instrukcji RemoveHandler](../../../language-reference/statements/removehandler-statement.md).

## <a name="see-also"></a>Zobacz także

- [Procedury](index.md)
- [Sub, procedury](sub-procedures.md)
- [Sub, instrukcja](../../../language-reference/statements/sub-statement.md)
- [AddressOf, operator](../../../language-reference/operators/addressof-operator.md)
- [Porady: tworzenie procedury](how-to-create-a-procedure.md)
- [Porady: wywoływanie procedury, która nie zwraca wartości](how-to-call-a-procedure-that-does-not-return-a-value.md)
