---
title: 'Przewodnik: Tworzenie obiektów dynamicznych i posługiwanie się nimi (C# i Visual Basic)'
description: Dowiedz się, jak tworzyć i używać obiektów dynamicznych w tym instruktażu. Utwórz niestandardowy obiekt dynamiczny i projekt korzystający z biblioteki "IronPython".
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dynamic objects [Visual Basic]
- dynamic objects
- dynamic objects [C#]
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
ms.openlocfilehash: 8da8ba964a9f0721602b10a6258a4e85341a617f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716138"
---
# <a name="walkthrough-creating-and-using-dynamic-objects-c-and-visual-basic"></a>Przewodnik: Tworzenie obiektów dynamicznych i posługiwanie się nimi (C# i Visual Basic)

Obiekty dynamiczne uwidaczniają elementy członkowskie, takie jak właściwości i metody w czasie wykonywania, a nie w czasie kompilacji. Dzięki temu można tworzyć obiekty do pracy ze strukturami niezgodnymi z typem statycznym lub formatem. Na przykład można użyć obiektu dynamicznego do odwoływania się do Document Object Model HTML (DOM), który może zawierać dowolną kombinację prawidłowych elementów i atrybutów HTML znaczników. Ponieważ każdy dokument HTML jest unikatowy, elementy członkowskie określonego dokumentu HTML są określane w czasie wykonywania. Typową metodą odwoływania się do atrybutu elementu HTML jest przekazanie nazwy atrybutu do `GetProperty` metody elementu. Aby odwołać się do `id` atrybutu elementu HTML `<div id="Div1">` , należy najpierw uzyskać odwołanie do `<div>` elementu, a następnie użyć `divElement.GetProperty("id")` . Jeśli używasz obiektu dynamicznego, możesz odwołać się do `id` atrybutu jako `divElement.id` .

 Obiekty dynamiczne zapewniają również wygodny dostęp do języków dynamicznych, takich jak IronPython i IronRuby. Można użyć obiektu dynamicznego do odwoływania się do skryptu dynamicznego, który jest interpretowany w czasie wykonywania.

 Odwołanie do obiektu dynamicznego przy użyciu późnego wiązania. W języku C# należy określić typ obiektu z późnym wiązaniem jako `dynamic` . W Visual Basic należy określić typ obiektu z późnym wiązaniem jako `Object` . Aby uzyskać więcej informacji, zobacz [dynamiczne](../../language-reference/builtin-types/reference-types.md) i [wczesne i późne powiązania](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).

 Niestandardowe obiekty dynamiczne można utworzyć przy użyciu klas w <xref:System.Dynamic?displayProperty=nameWithType> przestrzeni nazw. Na przykład można utworzyć <xref:System.Dynamic.ExpandoObject> i określić elementy członkowskie tego obiektu w czasie wykonywania. Możesz również utworzyć własny typ, który dziedziczy <xref:System.Dynamic.DynamicObject> klasę. Następnie można zastąpić elementy członkowskie <xref:System.Dynamic.DynamicObject> klasy, aby zapewnić funkcje dynamiczne w czasie wykonywania.

 W tym instruktażu wykonasz następujące zadania:

- Utwórz niestandardowy obiekt, który dynamicznie ujawnia zawartość pliku tekstowego jako właściwości obiektu.

- Utwórz projekt, który używa `IronPython` biblioteki.

## <a name="prerequisites"></a>Wymagania wstępne

Aby ukończyć ten przewodnik, musisz mieć [IronPython](https://ironpython.net/) dla platformy .NET. Przejdź do [strony pobierania](https://ironpython.net/download/) , aby uzyskać najnowszą wersję.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-a-custom-dynamic-object"></a>Tworzenie niestandardowego obiektu dynamicznego

Pierwszy projekt tworzony w tym instruktażu definiuje niestandardowy obiekt dynamiczny, który przeszukuje zawartość pliku tekstowego. Tekst do wyszukania jest określany przez nazwę właściwości dynamicznej. Na przykład jeśli wywoływany jest kod `dynamicFile.Sample` , Klasa dynamiczna zwraca ogólną listę ciągów, które zawierają wszystkie wiersze z pliku rozpoczynającego się od "sample". W wyszukiwaniu nie jest rozróżniana wielkość liter. Klasa dynamiczna obsługuje również dwa opcjonalne argumenty. Pierwszy argument jest wartością wyliczenia opcji wyszukiwania, która określa, że Klasa dynamiczna powinna wyszukiwać dopasowania na początku wiersza, na końcu wiersza lub w dowolnym miejscu w wierszu. Drugi argument określa, że Klasa dynamiczna powinna przycinać wiodące i końcowe spacje z każdego wiersza przed wyszukiwaniem. Na przykład, jeśli wywołujesz kod `dynamicFile.Sample(StringSearchOption.Contains)` , Klasa dynamiczna wyszukuje "sample" w dowolnym miejscu w wierszu. Jeśli wywoływany jest kod `dynamicFile.Sample(StringSearchOption.StartsWith, false)` , Klasa dynamiczna wyszukuje "przykład" na początku każdego wiersza i nie usuwa spacji wiodących i końcowych. Domyślne zachowanie klasy dynamicznej polega na wyszukiwaniu dopasowania na początku każdego wiersza i usunięciu spacji wiodących i końcowych.

### <a name="to-create-a-custom-dynamic-class"></a>Aby utworzyć niestandardową klasę dynamiczną

1. Uruchom program Visual Studio.

2. W menu **plik** wskaż polecenie **Nowy** , a następnie kliknij pozycję **projekt**.

3. W oknie dialogowym **Nowy projekt** w okienku **typy projektów** upewnij się, że wybrano opcję **Windows** . Wybierz pozycję **Aplikacja konsolowa** w okienku **Szablony** . W polu **Nazwa** wpisz `DynamicSample` , a następnie kliknij przycisk **OK**. Zostanie utworzony nowy projekt.

4. Kliknij prawym przyciskiem myszy projekt DynamicSample i wskaż polecenie **Dodaj**, a następnie kliknij pozycję **Klasa**. W polu **Nazwa** wpisz `ReadOnlyFile` , a następnie kliknij przycisk **OK**. Dodano nowy plik, który zawiera klasę ReadOnlyFile.

5. W górnej części pliku ReadOnlyFile.cs lub ReadOnlyFile. vb Dodaj następujący kod, aby zaimportować <xref:System.IO?displayProperty=nameWithType> <xref:System.Dynamic?displayProperty=nameWithType> przestrzenie nazw i.

    [!code-csharp[VbDynamicWalkthrough#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#1)]
    [!code-vb[VbDynamicWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#1)]

6. Niestandardowy obiekt dynamiczny używa wyliczenia, aby określić kryteria wyszukiwania. Przed instrukcją klasy Dodaj następującą definicję wyliczenia.

    [!code-csharp[VbDynamicWalkthrough#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#2)]
    [!code-vb[VbDynamicWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#2)]

7. Zaktualizuj instrukcję Class, aby dziedziczyć `DynamicObject` klasę, jak pokazano w poniższym przykładzie kodu.

    [!code-csharp[VbDynamicWalkthrough#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#3)]
    [!code-vb[VbDynamicWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#3)]

8. Dodaj następujący kod do klasy, `ReadOnlyFile` Aby zdefiniować pole prywatne dla ścieżki pliku i konstruktora dla `ReadOnlyFile` klasy.

    [!code-csharp[VbDynamicWalkthrough#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#4)]
    [!code-vb[VbDynamicWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#4)]

9. Dodaj następującą metodę `GetPropertyValue` do klasy `ReadOnlyFile`. `GetPropertyValue`Metoda przyjmuje, jako dane wejściowe, kryteria wyszukiwania i zwraca wiersze z pliku tekstowego, który odpowiada tym kryteriom wyszukiwania. Metody dynamiczne dostarczone przez `ReadOnlyFile` klasę wywołują metodę, `GetPropertyValue` Aby pobrać odpowiednie wyniki.

    [!code-csharp[VbDynamicWalkthrough#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#5)]
    [!code-vb[VbDynamicWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#5)]

10. Po `GetPropertyValue` metodzie Dodaj następujący kod, aby zastąpić <xref:System.Dynamic.DynamicObject.TryGetMember%2A> metodę <xref:System.Dynamic.DynamicObject> klasy. <xref:System.Dynamic.DynamicObject.TryGetMember%2A>Metoda jest wywoływana, gdy wymagana jest składowa klasy dynamicznej i nie określono żadnych argumentów. `binder`Argument zawiera informacje o odwołanym elemencie członkowskim, a `result` argument odwołuje się do wyniku zwróconego dla określonego elementu członkowskiego. <xref:System.Dynamic.DynamicObject.TryGetMember%2A>Metoda zwraca wartość logiczną, która zwraca, `true` Jeśli żądany element członkowski istnieje; w przeciwnym razie zwraca `false` .

    [!code-csharp[VbDynamicWalkthrough#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#6)]
    [!code-vb[VbDynamicWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#6)]

11. Po `TryGetMember` metodzie Dodaj następujący kod, aby zastąpić <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> metodę <xref:System.Dynamic.DynamicObject> klasy. <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A>Metoda jest wywoływana, gdy element członkowski klasy dynamicznej jest wymagany z argumentami. `binder`Argument zawiera informacje o odwołanym elemencie członkowskim, a `result` argument odwołuje się do wyniku zwróconego dla określonego elementu członkowskiego. `args`Argument zawiera tablicę argumentów, które są przekazane do elementu członkowskiego. <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A>Metoda zwraca wartość logiczną, która zwraca, `true` Jeśli żądany element członkowski istnieje; w przeciwnym razie zwraca `false` .

    Niestandardowa wersja `TryInvokeMember` metody oczekuje, że pierwszy argument będzie wartością z `StringSearchOption` wyliczenia zdefiniowanego w poprzednim kroku. `TryInvokeMember`Metoda oczekuje, że drugi argument jest wartością logiczną. Jeśli jeden lub oba argumenty są prawidłowymi wartościami, są one przekazane do `GetPropertyValue` metody w celu pobrania wyników.

    [!code-csharp[VbDynamicWalkthrough#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/readonlyfile.cs#7)]
    [!code-vb[VbDynamicWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/readonlyfile.vb#7)]

12. Zapisz i zamknij plik.

#### <a name="to-create-a-sample-text-file"></a>Aby utworzyć przykładowy plik tekstowy

1. Kliknij prawym przyciskiem myszy projekt DynamicSample i wskaż polecenie **Dodaj**, a następnie kliknij pozycję **nowy element**. W okienku **zainstalowane szablony** wybierz pozycję **Ogólne**, a następnie wybierz szablon **plik tekstowy** . Pozostaw domyślną nazwę TextFile1.txt w polu **Nazwa** , a następnie kliknij przycisk **Dodaj**. Nowy plik tekstowy zostanie dodany do projektu.

2. Skopiuj poniższy tekst do pliku TextFile1.txt.

    ```text
    List of customers and suppliers

    Supplier: Lucerne Publishing (https://www.lucernepublishing.com/)
    Customer: Preston, Chris
    Customer: Hines, Patrick
    Customer: Cameron, Maria
    Supplier: Graphic Design Institute (https://www.graphicdesigninstitute.com/)
    Supplier: Fabrikam, Inc. (https://www.fabrikam.com/)
    Customer: Seubert, Roxanne
    Supplier: Proseware, Inc. (http://www.proseware.com/)
    Customer: Adolphi, Stephan
    Customer: Koch, Paul
    ```

3. Zapisz i zamknij plik.

#### <a name="to-create-a-sample-application-that-uses-the-custom-dynamic-object"></a>Aby utworzyć przykładową aplikację korzystającą z niestandardowego obiektu dynamicznego

1. W **Eksplorator rozwiązań**, kliknij dwukrotnie plik Module1. vb, jeśli używasz Visual Basic lub pliku program.cs, jeśli używasz języka Visual C#.

2. Dodaj następujący kod do głównej procedury, aby utworzyć wystąpienie `ReadOnlyFile` klasy dla pliku TextFile1.txt. Kod używa późnego wiązania, aby wywołać dynamiczne elementy członkowskie i pobrać wiersze tekstu, które zawierają ciąg "Customer".

     [!code-csharp[VbDynamicWalkthrough#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthrough/cs/program.cs#8)]
     [!code-vb[VbDynamicWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthrough/vb/module1.vb#8)]

3. Zapisz plik i naciśnij klawisze CTRL + F5, aby skompilować i uruchomić aplikację.

## <a name="calling-a-dynamic-language-library"></a>Wywoływanie biblioteki języka dynamicznego

Następny projekt tworzony w tym instruktażu uzyskuje dostęp do biblioteki, która jest zapisywana w IronPython języka dynamicznego.

### <a name="to-create-a-custom-dynamic-class"></a>Aby utworzyć niestandardową klasę dynamiczną

1. W programie Visual Studio w menu **plik** wskaż polecenie **Nowy** , a następnie kliknij pozycję **projekt**.

2. W oknie dialogowym **Nowy projekt** w okienku **typy projektów** upewnij się, że wybrano opcję **Windows** . Wybierz pozycję **Aplikacja konsolowa** w okienku **Szablony** . W polu **Nazwa** wpisz `DynamicIronPythonSample` , a następnie kliknij przycisk **OK**. Zostanie utworzony nowy projekt.

3. Jeśli używasz Visual Basic, kliknij prawym przyciskiem myszy projekt DynamicIronPythonSample, a następnie kliknij polecenie **Właściwości**. Kliknij kartę **odwołania** . Kliknij przycisk **Dodaj** . Jeśli używasz języka Visual C#, w **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy folder **odwołania** , a następnie kliknij polecenie **Dodaj odwołanie**.

4. Na karcie **przeglądanie** przejdź do folderu, w którym są zainstalowane biblioteki IronPython. Na przykład C:\Program Files\IronPython 2,6 dla .NET Framework 4,0. Wybierz biblioteki **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** i **Microsoft.Dynamic.dll** . Kliknij przycisk **OK**.

5. Jeśli używasz Visual Basic, edytuj plik Module1. vb. Jeśli używasz języka Visual C#, edytuj plik Program.cs.

6. W górnej części pliku Dodaj następujący kod, aby zaimportować `Microsoft.Scripting.Hosting` `IronPython.Hosting` przestrzenie nazw i z bibliotek IronPython.

    [!code-csharp[VbDynamicWalkthroughIronPython#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#1)]
    [!code-vb[VbDynamicWalkthroughIronPython#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#1)]

7. W metodzie Main Dodaj następujący kod, aby utworzyć nowy `Microsoft.Scripting.Hosting.ScriptRuntime` obiekt do hostowania bibliotek IronPython. `ScriptRuntime`Obiekt ładuje moduł biblioteki IronPython Random.py.

     [!code-csharp[VbDynamicWalkthroughIronPython#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#2)]
     [!code-vb[VbDynamicWalkthroughIronPython#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#2)]

8. Po kodzie do załadowania modułu random.py Dodaj następujący kod, aby utworzyć tablicę liczb całkowitych. Tablica jest przenoszona do `shuffle` metody modułu Random.py, co losowo sortuje wartości w tablicy.

     [!code-csharp[VbDynamicWalkthroughIronPython#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/cs/program.cs#3)]
     [!code-vb[VbDynamicWalkthroughIronPython#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython/vb/module1.vb#3)]

9. Zapisz plik i naciśnij klawisze CTRL + F5, aby skompilować i uruchomić aplikację.

## <a name="see-also"></a>Zobacz także

- <xref:System.Dynamic?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
- [Używanie typu dynamicznego](./using-type-dynamic.md)
- [Wczesne i późne powiązania](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [dynamiczna](../../language-reference/builtin-types/reference-types.md)
- [Implementowanie interfejsów dynamicznych (plik PDF do pobrania z witryny Microsoft TechNet)](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/implementing-dynamic-interfaces.pdf)
