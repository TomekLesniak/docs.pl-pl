---
title: Programowanie zorientowane obiektowo (C#)
description: Język C# zapewnia pełną obsługę programowania zorientowanego obiektowo, w tym abstrakcję, hermetyzację, dziedziczenie i polimorfizm.
ms.date: 09/30/2020
ms.openlocfilehash: 8a8dc8dc6d40c539b988ea203654d994e88c357a
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91614797"
---
# <a name="object-oriented-programming-c"></a>Programowanie zorientowane obiektowo (C#)

C# to język zorientowany obiektowo. Cztery z kluczowych technik używanych w programowaniu zorientowanym na obiektach są następujące:

- *Abstrakcja* oznacza ukrycie niepotrzebnych informacji od odbiorców typu.
- *Hermetyzacja* oznacza, że grupa powiązanych właściwości, metod i innych elementów członkowskich jest traktowana jako pojedyncza jednostka lub obiekt.
- *Dziedziczenie* opisuje możliwość tworzenia nowych klas na podstawie istniejącej klasy.
- *Polimorfizm* oznacza, że można mieć wiele klas, które mogą być używane zamiennie, nawet jeśli każda klasa implementuje te same właściwości lub metody na różne sposoby.

W poprzednim samouczku przedstawiono [wprowadzenie do klas](introduction-to-classes.md) , w których zawarto zarówno *abstrakcję* , jak i *hermetyzację*. `BankAccount`Klasa dostarczyła streszczenie dla koncepcji konta bankowego. Można zmodyfikować jego implementację bez wpływu na żaden kod, który używał `BankAccount` klasy. Obie `BankAccount` klasy i `Transaction` zapewniają hermetyzację składników niezbędnych do opisywania koncepcji w kodzie.

W tym samouczku zostanie rozbudowana aplikacja w celu użycia *dziedziczenia* i *polimorfizmu* w celu dodania nowych funkcji. Dodasz również funkcje do `BankAccount` klasy, wykorzystując metody *abstrakcji* i *hermetyzacji* , które zostały uzyskane w poprzednim samouczku.

## <a name="create-different-types-of-accounts"></a>Tworzenie różnych typów kont

Po skompilowaniu tego programu uzyskasz żądania dodania do niego funkcji. Jest to doskonałe rozwiązanie w sytuacji, gdy istnieje tylko jeden typ konta bankowego. W miarę upływu czasu wymagane zmiany i powiązane typy kont są wymagane:

- Konto zdobywania odsetek, które naliczane są odsetki na końcu każdego miesiąca.
- Linia kredytowa, która może mieć wartość ujemną, ale w przypadku bilansu jest naliczana opłata miesięczna.
- Wstępnie płatne konto karty upominkowej, które rozpoczyna się od jednego depozytu i można je tylko wypłacić. Można je ponownie wypełnić na początku każdego miesiąca.

Wszystkie te różne konta są podobne do `BankAccount` klasy zdefiniowanej w poprzednim samouczku. Można skopiować ten kod, zmienić nazwy klas i wprowadzić modyfikacje. Ta technika będzie działać w krótkim okresie, ale będzie bardziej wydajna w czasie. Wszystkie zmiany byłyby kopiowane do wszystkich klas, których to dotyczy.

Zamiast tego można utworzyć nowe typy kont bankowych, które dziedziczą metody i dane z `BankAccount` klasy utworzonej w poprzednim samouczku. Te nowe klasy mogą zwiększyć `BankAccount` klasę z określonym zachowaniem wymaganym dla każdego typu:

```csharp
public class InterestEarningAccount : BankAccount
{
}

public class LineOfCreditAccount : BankAccount
{
}

public class GiftCardAccount : BankAccount
{
}
```

Każda z tych klas *dziedziczy* zachowanie udostępnione ze swojej udostępnionej *klasy bazowej*, `BankAccount` klasy. Napisz implementacje dla nowych i różnych funkcji w każdej *klasie pochodnej*.  Te klasy pochodne mają już wszystkie zachowania zdefiniowane w `BankAccount` klasie.

Dobrym sposobem jest utworzenie każdej nowej klasy w innym pliku źródłowym. W programie [Visual Studio](https://visualstudio.com)kliknij prawym przyciskiem myszy projekt, a następnie wybierz polecenie *Dodaj klasę* , aby dodać nową klasę do nowego pliku. W [Visual Studio Code](https://code.visualstudio.com)wybierz opcję *plik* , a następnie pozycję *Nowy* , aby utworzyć nowy plik źródłowy. W każdym z tych narzędzi Nazwij plik, aby odpowiadał klasie: *InterestEarningAccount.cs*, *LineOfCreditAccount.cs*i *GiftCardAccount.cs*.

Podczas tworzenia klas, jak pokazano w poprzednim przykładzie, zobaczysz, że żadna z klas pochodnych nie zostanie skompilowana. Konstruktor jest odpowiedzialny za inicjowanie obiektu. Konstruktor klasy pochodnej musi inicjować klasę pochodną i dostarczać instrukcje dotyczące inicjowania obiektu klasy bazowej zawartego w klasie pochodnej. Odpowiednie inicjowanie zwykle odbywa się bez żadnych dodatkowych kodów. `BankAccount`Klasa deklaruje jeden konstruktor publiczny z następującym podpisem:

```csharp
public BankAccount(string name, decimal initialBalance)
```

Kompilator nie generuje domyślnego konstruktora podczas definiowania konstruktora. Oznacza to, że każda klasa pochodna musi jawnie wywołać ten Konstruktor. Deklaruj konstruktora, który może przekazywać argumenty do konstruktora klasy bazowej.  Poniższy kod pokazuje Konstruktor dla `InterestEarningAccount` :

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="DerivedConstructor":::

Parametry tego nowego konstruktora pasują do typu parametru i nazw konstruktora klasy bazowej. Użyj składni, `: base()` Aby wskazać wywołanie konstruktora klasy bazowej. Niektóre klasy definiują wiele konstruktorów, a ta składnia umożliwia wybranie konstruktora klasy bazowej, który jest wywoływany. Po zaktualizowaniu konstruktorów można opracowywać kod dla każdej klasy pochodnej. Wymagania dotyczące nowych klas można określić w następujący sposób:

- Konto zdobywania zainteresowania:
  - Otrzymasz środki w wysokości 2% salda końcowego miesiąca.
- Linia kredytowa:
  - Może mieć ujemny bilans, ale nie większy niż wartość bezwzględna limitu kredytowego.
  - Pociąga za sobą opłaty oprocentowane miesięcznie, gdy saldo końca miesiąca nie jest równe 0.
  - Nastąpi naliczenie opłaty za każde wycofanie, które przekracza limit kredytowy.
- Konto karty upominkowej:
  - Może zostać uzupełniona o określoną ilość raz w miesiącu w ostatnim dniu miesiąca.

Można zobaczyć, że wszystkie trzy typy kont mają akcję, która ma miejsce na koniec każdego miesiąca. Jednak każdy typ konta wykonuje różne zadania. Aby zaimplementować ten kod, należy użyć *polimorfizmu* . Utwórz pojedynczą `virtual` metodę w `BankAccount` klasie:

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="DeclareMonthEndTransactions":::

Poprzedni kod pokazuje, jak użyć `virtual` słowa kluczowego, aby zadeklarować metodę w klasie bazowej, która Klasa pochodna może zapewnić inną implementację. `virtual`Metoda jest metodą, w której każda klasa pochodna może zostać zaimplementowana. Klasy pochodne używają `override` słowa kluczowego, aby zdefiniować nową implementację. Zwykle Przywołujesz się do tego jako "zastępowanie implementacji klasy podstawowej". `virtual`Słowo kluczowe Określa, że klasy pochodne mogą zastąpić zachowanie. Można również deklarować `abstract` metody, w których klasy pochodne muszą przesłaniać zachowanie. Klasa bazowa nie zapewnia implementacji dla `abstract` metody. Następnie należy zdefiniować implementację dla dwóch nowych klas, które zostały utworzone. Zacznij od `InterestEarningAccount` :

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="ApplyMonthendInterest":::

Dodaj następujący kod do `LineOfCreditAccount` . Kod negacji salda w celu obliczenia dodatniej stopy oprocentowania wycofywanej z konta:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ApplyMonthendInterest":::

`GiftCardAccount`Aby można było zaimplementować swoją funkcję miesiąca, Klasa musi mieć dwie zmiany. Najpierw zmodyfikuj konstruktora, aby zawierał opcjonalną kwotę do dodania w każdym miesiącu:

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="GiftCardAccountConstruction":::

Konstruktor udostępnia wartość domyślną dla `monthlyDeposit` wartości, dzięki czemu obiekty wywołujące mogą pominąć `0` niemiesięczny depozyt. Następnie zastąp `PerformMonthEndTransactions` metodę w celu dodania miesięcznego depozytu, jeśli została ustawiona na wartość różną od zera w konstruktorze:

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="AddMonthlyDeposit":::

Zastąpienie obejmuje miesięczny zestaw depozytu w konstruktorze. Dodaj następujący kod do metody, `Main` Aby przetestować te zmiany dla `GiftCardAccount` i `InterestEarningAccount` :

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="FirstTests":::

Sprawdź wyniki. Teraz Dodaj podobny zestaw kodu testu dla `LineOfCreditAccount` :

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="TestLineOfCredit":::

Gdy dodasz poprzedni kod i uruchomisz program, zobaczysz coś podobne do następującego błędu:

```console
Unhandled exception. System.ArgumentOutOfRangeException: Amount of deposit must be positive (Parameter 'amount')
   at OOProgramming.BankAccount.MakeDeposit(Decimal amount, DateTime date, String note) in BankAccount.cs:line 42
   at OOProgramming.BankAccount..ctor(String name, Decimal initialBalance) in BankAccount.cs:line 31
   at OOProgramming.LineOfCreditAccount..ctor(String name, Decimal initialBalance) in LineOfCreditAccount.cs:line 9
   at OOProgramming.Program.Main(String[] args) in Program.cs:line 29
```

> [!NOTE]
> Rzeczywiste dane wyjściowe zawierają pełną ścieżkę do folderu z projektem. Nazwy folderów zostały pominięte dla zwięzłości. Ponadto, w zależności od formatu kodu, numery wierszy mogą się nieco różnić.

Ten kod kończy się niepowodzeniem, ponieważ `BankAccount` zakłada się, że saldo początkowe musi być większe niż 0. Inna rozszerzania założeń do `BankAccount` klasy polega na tym, że saldo nie może przekroczyć wartości ujemnej. Zamiast tego wszelkie wycofanie, które nastąpi, zostanie odrzucone. Należy zmienić oba te założenia. Wiersz konta kredytowego zaczyna się od 0 i ogólnie będzie miało ujemny bilans. Ponadto, jeśli klient zażyczy zbyt dużej ilości pieniędzy, naliczy opłaty. Transakcja zostanie zaakceptowana, a jedynie będzie kosztować więcej. Pierwszą regułę można zaimplementować przez dodanie opcjonalnego argumentu do `BankAccount` konstruktora, który określa minimalny bilans. Wartość domyślna to `0`. Druga reguła wymaga mechanizmu, który umożliwia klasom pochodnym modyfikowanie algorytmu domyślnego. W sensie Klasa bazowa "pyta" typ pochodny, co powinno nastąpić w przypadku przekroczenia projektu. Domyślnym zachowaniem jest odrzucanie transakcji przez wyrzucanie wyjątku.

Zacznijmy od dodania drugiego konstruktora zawierającego opcjonalny `minimumBalance` parametr. Ten nowy Konstruktor wykonuje wszystkie akcje wykonywane przez istniejącego konstruktora. Ponadto ustawia właściwość balansu minimalnego. Można skopiować treść istniejącego konstruktora. jednak oznacza to, że dwie lokalizacje zmieniają się w przyszłości. Zamiast tego można użyć *łańcucha konstruktorów* , aby jeden Konstruktor wywoływał inny. Poniższy kod przedstawia dwa konstruktory i nowe pole dodatkowe:

 :::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="ConstructorModifications":::

Poprzedni kod pokazuje dwie nowe techniki. Najpierw `minimumBalance` pole jest oznaczone jako `readonly` . Oznacza to, że nie można zmienić wartości po utworzeniu obiektu. Po `BankAccount` utworzeniu `minimumBalance` nie można zmienić. Drugi, Konstruktor, który przyjmuje dwa parametry używa `: this(name, initialBalance, 0) { }` jako implementacji. `: this()`Wyrażenie wywołuje innego konstruktora, a drugi z trzema parametrami. Ta technika umożliwia korzystanie z jednej implementacji do inicjowania obiektu, mimo że kod klienta może wybrać jeden z wielu konstruktorów.

Ta implementacja wywołuje `MakeDeposit` tylko wtedy, gdy saldo początkowe jest większe niż `0` . Pozwala to zachować regułę, która musi być wartością dodatnią, ale umożliwia otwarcie konta kredytowego z `0` saldem.

Teraz, gdy `BankAccount` Klasa ma pole tylko do odczytu dla minimalnego salda, końcowa zmiana polega na zmianie kodu twardego `0` na `minimumBalance` wartość w `MakeWithdrawal` metodzie:

```csharp
if (Balance - amount < minimumBalance)
```

Po rozszerzeniu `BankAccount` klasy można zmodyfikować `LineOfCreditAccount` konstruktora w taki sposób, aby wywoływał nowy Konstruktor podstawowy, jak pokazano w poniższym kodzie:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ConstructLineOfCredit":::

Zauważ, że `LineOfCreditAccount` Konstruktor zmienia znak `creditLimit` parametru, tak aby pasował do znaczenia `minimumBalance` parametru.

## <a name="different-overdraft-rules"></a>Różne reguły przekroczenia

Ostatnia funkcja do dodania umożliwia `LineOfCreditAccount` naliczenie opłaty za przekroczenie limitu kredytowego zamiast odmowy transakcji.

Jedną z technik jest zdefiniowanie funkcji wirtualnej, w której implementowane jest wymagane zachowanie. `Bank Account`Klasa refaktoryzacji `MakeWithdrawal` metody do dwóch metod. Nowa metoda wykonuje określoną akcję, gdy wycofanie ma saldo poniżej wartości minimalnej. Istniejąca `MakeWithdrawal` Metoda ma następujący kod:

```csharp
public void MakeWithdrawal(decimal amount, DateTime date, string note)
{
    if (amount <= 0)
    {
        throw new ArgumentOutOfRangeException(nameof(amount), "Amount of withdrawal must be positive");
    }
    if (Balance - amount < minimumBalance)
    {
        throw new InvalidOperationException("Not sufficient funds for this withdrawal");
    }
    var withdrawal = new Transaction(-amount, date, note);
    allTransactions.Add(withdrawal);
}
```

Zastąp go następującym kodem:

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="RefactoredMakeWithdrawal":::

Dodana Metoda to, co oznacza, że może być wywoływana tylko z klas pochodnych. Ta deklaracja uniemożliwia innym klientom wywoływanie metody. Istnieje również `virtual` możliwość zmiany zachowania klas pochodnych. Zwracanym typem jest `Transaction?` . `?`Adnotacja wskazuje, że metoda może zwrócić `null` . Dodaj następującą implementację w programie, `LineOfCreditAccount` Aby obciążać opłatę w przypadku przekroczenia limitu wycofania:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="AddOverdraftFee":::

Zastąpienie zwraca transakcję opłaty po narysowaniu konta. Jeśli wycofanie nie przekracza limitu, metoda zwraca `null` transakcję. Oznacza to, że nie ma opłat. Przetestuj te zmiany, dodając następujący kod do `Main` metody w `Program` klasie:

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="TestLineOfCredit":::

Uruchom program i sprawdź wyniki.

## <a name="summary"></a>Podsumowanie

Ten samouczek przedstawia wiele technik używanych w programowaniu zorientowanym obiektowo:

- Wykorzystano *abstrakcję* , gdy przechowujesz wiele szczegółów `private` w każdej klasie.
- Użyto *hermetyzacji* podczas definiowania klas dla każdego z różnych typów kont. Te klasy zostały opisane zachowanie dla tego typu konta.
- Użyto *dziedziczenia* podczas korzystania z implementacji już utworzonej w `BankAccount` klasie w celu zapisania kodu.
- Używasz *polimorfizmu* podczas tworzenia `virtual` metod, które klasy pochodne mogą przesłonić, aby utworzyć określone zachowanie dla tego typu konta.

Gratulacje, udało Ci się ukończyć wszystkie nasze wprowadzenie do samouczków języka C#. Aby dowiedzieć się więcej, wypróbuj więcej naszych [samouczków](../index.md).
