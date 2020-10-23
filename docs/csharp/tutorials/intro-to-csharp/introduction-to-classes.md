---
title: Klasy i obiekty — wprowadzenie do samouczka języka C#
description: Utwórz pierwszy program w języku C# i Eksploruj koncepcje zorientowane obiektowo
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 0955b0ac33b346b9880c8af70bd73cb458120f35
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434895"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="9a2a7-103">Eksploruj programowanie zorientowane obiektowo przy użyciu klas i obiektów</span><span class="sxs-lookup"><span data-stu-id="9a2a7-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="9a2a7-104">Ten samouczek oczekuje, że masz maszynę, której możesz użyć do programowania.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="9a2a7-105">Samouczek platformy .NET [Hello World w ciągu 10 minut](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) zawiera instrukcje dotyczące konfigurowania lokalnego środowiska deweloperskiego w systemie Windows, Linux lub macOS.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="9a2a7-106">Krótkie omówienie poleceń, z których będziesz korzystać, znajduje się w zapoznanie [z narzędziami programistycznymi](local-environment.md) zawierającymi linki do dalszych szczegółów.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="9a2a7-107">Tworzenie aplikacji</span><span class="sxs-lookup"><span data-stu-id="9a2a7-107">Create your application</span></span>

<span data-ttu-id="9a2a7-108">Za pomocą okna terminalu Utwórz katalog o nazwie *Classes*.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-108">Using a terminal window, create a directory named *classes*.</span></span> <span data-ttu-id="9a2a7-109">W tym miejscu utworzysz aplikację.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-109">You'll build your application there.</span></span> <span data-ttu-id="9a2a7-110">Przejdź do tego katalogu i wpisz `dotnet new console` w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="9a2a7-111">To polecenie tworzy aplikację.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-111">This command creates your application.</span></span> <span data-ttu-id="9a2a7-112">Otwórz *program.cs*.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-112">Open *Program.cs*.</span></span> <span data-ttu-id="9a2a7-113">Powinien on wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-113">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="9a2a7-114">W tym samouczku utworzysz nowe typy reprezentujące konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="9a2a7-115">Zazwyczaj deweloperzy definiują każdą klasę w innym pliku tekstowym.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="9a2a7-116">Ułatwia to zarządzanie w miarę zwiększania się rozmiaru programu.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-116">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="9a2a7-117">Utwórz nowy plik o nazwie *BankAccount.cs* w katalogu *Classes* .</span><span class="sxs-lookup"><span data-stu-id="9a2a7-117">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span>

<span data-ttu-id="9a2a7-118">Ten plik będzie zawierać definicję \***konta bankowego**_.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-118">This file will contain the definition of a \***bank account**_.</span></span> <span data-ttu-id="9a2a7-119">Programowanie zorientowane obiektowo organizuje kod przez tworzenie typów w postaci _*_klas_*_.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-119">Object Oriented programming organizes code by creating types in the form of _*_classes_*_.</span></span> <span data-ttu-id="9a2a7-120">Klasy te zawierają kod, który reprezentuje konkretną jednostkę.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="9a2a7-121">`BankAccount`Klasa reprezentuje konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="9a2a7-122">Kod implementuje określone operacje za pomocą metod i właściwości.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="9a2a7-123">W tym samouczku konto bankowe obsługuje takie zachowanie:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="9a2a7-124">Ma 10-cyfrowy numer, który jednoznacznie identyfikuje konto bankowe.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="9a2a7-125">Zawiera on ciąg przechowujący nazwę lub nazwy właścicieli.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="9a2a7-126">Można pobrać saldo.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="9a2a7-127">Akceptuje ona depozyty.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-127">It accepts deposits.</span></span>
1. <span data-ttu-id="9a2a7-128">Akceptuje on wycofania.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="9a2a7-129">Saldo początkowe musi mieć wartość dodatnią.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="9a2a7-130">Wycofanie nie może spowodować negatywnego salda.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="9a2a7-131">Definiowanie typu konta bankowego</span><span class="sxs-lookup"><span data-stu-id="9a2a7-131">Define the bank account type</span></span>

<span data-ttu-id="9a2a7-132">Można rozpocząć od utworzenia podstawowych podstaw klasy, które definiują takie zachowanie.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="9a2a7-133">Utwórz nowy plik przy użyciu _*pliku: New*\* polecenie.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-133">Create a new file using the _*File:New*\* command.</span></span> <span data-ttu-id="9a2a7-134">Nadaj mu nazwę *BankAccount.cs*.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-134">Name it *BankAccount.cs*.</span></span> <span data-ttu-id="9a2a7-135">Dodaj następujący kod do pliku *BankAccount.cs* :</span><span class="sxs-lookup"><span data-stu-id="9a2a7-135">Add the following code to your *BankAccount.cs* file:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="9a2a7-136">Przed rozpoczęciem przejdźmy do tego, co zostało skompilowane.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-136">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="9a2a7-137">`namespace`Deklaracja umożliwia logicznie organizowanie kodu.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-137">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="9a2a7-138">Ten samouczek jest stosunkowo mały, więc umieścisz cały kod w jednej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-138">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span>

<span data-ttu-id="9a2a7-139">`public class BankAccount` definiuje klasę lub typ, który tworzysz.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-139">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="9a2a7-140">Wszystko wewnątrz `{` i `}` , które następuje po deklaracji klasy, definiuje stan i zachowanie klasy.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-140">Everything inside the `{` and `}` that follows the class declaration defines the state and behavior of the class.</span></span> <span data-ttu-id="9a2a7-141">Istnieje pięć \***członków**_ `BankAccount` klasy.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-141">There are five \***members**_ of the `BankAccount` class.</span></span> <span data-ttu-id="9a2a7-142">Pierwsze trzy są _*_właściwościami_*_.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-142">The first three are _*_properties_*_.</span></span> <span data-ttu-id="9a2a7-143">Właściwości są elementami danych i mogą mieć kod, który wymusza walidację lub inne reguły.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-143">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="9a2a7-144">Ostatnie dwa są _*_metodami_*_.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-144">The last two are _*_methods_*_.</span></span> <span data-ttu-id="9a2a7-145">Metody to bloki kodu, które wykonują pojedynczą funkcję.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-145">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="9a2a7-146">Odczytywanie nazw każdego z członków powinno zapewnić wystarczającą ilość informacji dla Ciebie lub innego dewelopera, aby zrozumieć, co robi Klasa.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-146">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="9a2a7-147">Otwórz nowe konto</span><span class="sxs-lookup"><span data-stu-id="9a2a7-147">Open a new account</span></span>

<span data-ttu-id="9a2a7-148">Pierwsza funkcja do wdrożenia polega na otwarciu konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-148">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="9a2a7-149">Gdy klient otworzy konto, musi podać początkowe saldo i informacje o właścicielu lub właściciele tego konta.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-149">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span>

<span data-ttu-id="9a2a7-150">Tworzenie nowego obiektu `BankAccount` typu oznacza zdefiniowanie _*_konstruktora_*_ , który przypisuje te wartości.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-150">Creating a new object of the `BankAccount` type means defining a _*_constructor_*_ that assigns those values.</span></span> <span data-ttu-id="9a2a7-151">_*_Konstruktor_*_ jest członkiem, który ma taką samą nazwę jak Klasa.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-151">A _*_constructor_*_ is a member that has the same name as the class.</span></span> <span data-ttu-id="9a2a7-152">Służy do inicjowania obiektów tego typu klasy.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-152">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="9a2a7-153">Dodaj do typu następujący Konstruktor `BankAccount` .</span><span class="sxs-lookup"><span data-stu-id="9a2a7-153">Add the following constructor to the `BankAccount` type.</span></span> <span data-ttu-id="9a2a7-154">Umieść poniższy kod powyżej deklaracji `MakeDeposit` :</span><span class="sxs-lookup"><span data-stu-id="9a2a7-154">Place the following code above the declaration of `MakeDeposit`:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="9a2a7-155">Konstruktory są wywoływane podczas tworzenia obiektu za pomocą [`new`](../../language-reference/operators/new-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="9a2a7-155">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="9a2a7-156">Zastąp wiersz `Console.WriteLine("Hello World!");` w _Program. cs \* następującym kodem (Zastąp `<name>` nazwą):</span><span class="sxs-lookup"><span data-stu-id="9a2a7-156">Replace the line `Console.WriteLine("Hello World!");` in _Program.cs\* with the following code (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="9a2a7-157">Uruchommy te, które zostały już skompilowane.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-157">Let's run what you've built so far.</span></span> <span data-ttu-id="9a2a7-158">Jeśli używasz programu Visual Studio, wybierz pozycję **Uruchom bez debugowania** z menu **Uruchom** .</span><span class="sxs-lookup"><span data-stu-id="9a2a7-158">If you're using Visual Studio, Select **Start without debugging** from the **Run** menu.</span></span> <span data-ttu-id="9a2a7-159">Jeśli używasz wiersza polecenia, wpisz `dotnet run` w katalogu, w którym został utworzony projekt.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-159">If you're using a command line, type `dotnet run` in the directory where you've created your project.</span></span>

<span data-ttu-id="9a2a7-160">Czy na pewno numer konta jest pusty?</span><span class="sxs-lookup"><span data-stu-id="9a2a7-160">Did you notice that the account number is blank?</span></span> <span data-ttu-id="9a2a7-161">Czas na rozwiązanie tego problemu.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-161">It's time to fix that.</span></span> <span data-ttu-id="9a2a7-162">Numer konta powinien być przypisany podczas konstruowania obiektu.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-162">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="9a2a7-163">Ale nie powinien być odpowiedzialny za utworzenie go przez obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-163">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="9a2a7-164">`BankAccount`Kod klasy powinien wiedzieć, jak przypisać nowe numery kont.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-164">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="9a2a7-165">Prostym sposobem, aby to zrobić, jest rozpoczęcie z 10-cyfrową liczbą.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-165">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="9a2a7-166">Zwiększ ją po utworzeniu każdego nowego konta.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-166">Increment it when each new account is created.</span></span> <span data-ttu-id="9a2a7-167">Na koniec Zapisz bieżący numer konta w przypadku konstruowania obiektu.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-167">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="9a2a7-168">Dodaj deklarację elementu członkowskiego do `BankAccount` klasy.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-168">Add a member declaration to the `BankAccount` class.</span></span> <span data-ttu-id="9a2a7-169">Umieść następujący wiersz kodu po nawiasie otwierającym `{` na początku `BankAccount` klasy:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-169">Place the following line of code after the opening brace `{` at the beginning of the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="9a2a7-170">To jest element członkowski danych.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-170">This is a data member.</span></span> <span data-ttu-id="9a2a7-171">Oznacza to `private` , że można uzyskać do niego dostęp tylko przez kod wewnątrz `BankAccount` klasy.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-171">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="9a2a7-172">Jest to sposób oddzielenia publicznych obowiązków (na przykład numeru konta) od implementacji prywatnej (jak są generowane numery kont).</span><span class="sxs-lookup"><span data-stu-id="9a2a7-172">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated).</span></span> <span data-ttu-id="9a2a7-173">Jest to również `static` , co oznacza, że jest ono współużytkowane przez wszystkie `BankAccount` obiekty.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-173">It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="9a2a7-174">Wartość zmiennej niestatycznej jest unikatowa dla każdego wystąpienia `BankAccount` obiektu.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-174">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="9a2a7-175">Dodaj następujące dwa wiersze do konstruktora, aby przypisać numer konta.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-175">Add the following two lines to the constructor to assign the account number.</span></span> <span data-ttu-id="9a2a7-176">Umieść je po wierszu, który brzmi `this.Balance = initialBalance` :</span><span class="sxs-lookup"><span data-stu-id="9a2a7-176">Place them after the line that says `this.Balance = initialBalance`:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="9a2a7-177">Wpisz `dotnet run` , aby wyświetlić wyniki.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-177">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="9a2a7-178">Utwórz depozyty i Wycofaj</span><span class="sxs-lookup"><span data-stu-id="9a2a7-178">Create deposits and withdrawals</span></span>

<span data-ttu-id="9a2a7-179">Twoja Klasa konta bankowego musi akceptować depozyty i wycofywania, aby działały prawidłowo.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-179">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="9a2a7-180">Zaimplementujmy depozyty i wycofania, tworząc arkusz każdej transakcji dla konta.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-180">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="9a2a7-181">Ma kilka korzyści w porównaniu do zwykłego aktualizowania salda każdej transakcji.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-181">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="9a2a7-182">Historia może służyć do inspekcji wszystkich transakcji i zarządzania bilansami dziennymi.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-182">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="9a2a7-183">Dzięki wykorzystaniu salda z historii wszystkich transakcji, gdy jest to potrzebne, wszelkie błędy w pojedynczej transakcji, które są stałe, zostaną prawidłowo odzwierciedlone w saldzie następnego obliczenia.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-183">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="9a2a7-184">Zacznijmy od utworzenia nowego typu do reprezentowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-184">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="9a2a7-185">Jest to prosty typ, który nie ma żadnych obowiązków.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-185">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="9a2a7-186">Potrzebuje on kilku właściwości.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-186">It needs a few properties.</span></span> <span data-ttu-id="9a2a7-187">Utwórz nowy plik o nazwie *Transaction.cs*.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-187">Create a new file named *Transaction.cs*.</span></span> <span data-ttu-id="9a2a7-188">Dodaj do niej następujący kod:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-188">Add the following code to it:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/Transaction.cs":::

<span data-ttu-id="9a2a7-189">Teraz Dodajmy <xref:System.Collections.Generic.List%601> `Transaction` obiekty do `BankAccount` klasy.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-189">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="9a2a7-190">Dodaj następującą deklarację po konstruktorze w pliku *BankAccount.cs* :</span><span class="sxs-lookup"><span data-stu-id="9a2a7-190">Add the following declaration after the constructor in your *BankAccount.cs* file:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="TransactionDeclaration":::

<span data-ttu-id="9a2a7-191"><xref:System.Collections.Generic.List%601>Klasa wymaga zaimportowania innej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-191">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="9a2a7-192">Dodaj następujące elementy na początku *BankAccount.cs*:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-192">Add the following at the beginning of *BankAccount.cs*:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="9a2a7-193">Teraz poprawnie Obliczmy `Balance` .</span><span class="sxs-lookup"><span data-stu-id="9a2a7-193">Now, let's correctly compute the `Balance`.</span></span> <span data-ttu-id="9a2a7-194">Bieżące saldo można znaleźć, sumując wartości wszystkich transakcji.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-194">The current balance can be found by summing the values of all transactions.</span></span> <span data-ttu-id="9a2a7-195">Ponieważ kod jest obecnie, możesz uzyskać tylko początkowe saldo konta, więc musisz zaktualizować `Balance` Właściwość.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-195">As the code is currently, you can only get the initial balance of the account, so you'll have to update the `Balance` property.</span></span> <span data-ttu-id="9a2a7-196">Zastąp wiersz `public decimal Balance { get; }` w *BankAccount.cs* następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-196">Replace the line `public decimal Balance { get; }` in *BankAccount.cs* with the following code:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="BalanceComputation":::

<span data-ttu-id="9a2a7-197">Ten przykład pokazuje istotny aspekt \***Właściwości**_.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-197">This example shows an important aspect of \***properties**_.</span></span> <span data-ttu-id="9a2a7-198">Teraz trwa obliczanie salda, gdy inny programista pyta o wartość.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-198">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="9a2a7-199">Wyliczenie wylicza wszystkie transakcje i zawiera sumę jako bieżące saldo.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-199">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="9a2a7-200">Następnie Zaimplementuj `MakeDeposit` metody i `MakeWithdrawal` .</span><span class="sxs-lookup"><span data-stu-id="9a2a7-200">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="9a2a7-201">Te metody wymuszą dwie ostatnie reguły: początkowe saldo musi być dodatnie i że każde wycofanie nie może utworzyć salda ujemnego.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-201">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span>

<span data-ttu-id="9a2a7-202">Wprowadza to koncepcję _*_wyjątków_*_.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-202">This introduces the concept of _*_exceptions_*_.</span></span> <span data-ttu-id="9a2a7-203">Standardowy sposób wskazujący, że metoda nie może zakończyć pracy, to zgłosić wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-203">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="9a2a7-204">Typ wyjątku i komunikat skojarzony z nim opisują błąd.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-204">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="9a2a7-205">W tym miejscu `MakeDeposit` Metoda zgłasza wyjątek, jeśli kwota depozytu jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-205">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="9a2a7-206">`MakeWithdrawal`Metoda zgłasza wyjątek, jeśli kwota wycofania jest ujemna lub jeśli zastosowanie wycofania powoduje ujemne saldo.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-206">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance.</span></span> <span data-ttu-id="9a2a7-207">Dodaj następujący kod po deklaracji `allTransactions` listy:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-207">Add the following code after the declaration of the `allTransactions` list:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="DepositAndWithdrawal":::

<span data-ttu-id="9a2a7-208">[`throw`](../../language-reference/keywords/throw.md)Instrukcja _*zwraca*wyjątek.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-208">The [`throw`](../../language-reference/keywords/throw.md) statement _*throws*\* an exception.</span></span> <span data-ttu-id="9a2a7-209">Wykonanie bieżącego bloku i sterowanie transferami do pierwszego zgodnego `catch` bloku znalezionego w stosie wywołań.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-209">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="9a2a7-210">Dodasz blok, `catch` Aby przetestować ten kod nieco później.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-210">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="9a2a7-211">Konstruktor powinien otrzymać jedną zmianę, aby dodać początkową transakcję zamiast bezpośrednio aktualizować saldo.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-211">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="9a2a7-212">Ponieważ już zapisano `MakeDeposit` metodę, wywołaj ją z konstruktora.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-212">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="9a2a7-213">Gotowy Konstruktor powinien wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-213">The finished constructor should look like this:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="Constructor":::

<span data-ttu-id="9a2a7-214"><xref:System.DateTime.Now?displayProperty=nameWithType> jest właściwością zwracającą bieżącą datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-214"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="9a2a7-215">Przetestuj to poprzez dodanie kilku depozytów i wycofań w `Main` metodzie, po kodzie, który tworzy nowy `BankAccount` :</span><span class="sxs-lookup"><span data-stu-id="9a2a7-215">Test this by adding a few deposits and withdrawals in your `Main` method, following the code that creates a new `BankAccount`:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="9a2a7-216">Następnie należy sprawdzić, czy są przechwytywane warunki błędów, próbując utworzyć konto z równoważeniem minus.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-216">Next, test that you are catching error conditions by trying to create an account with a negative balance.</span></span> <span data-ttu-id="9a2a7-217">Dodaj następujący kod po właśnie powyższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-217">Add the following code after the preceding code you just added:</span></span>

```csharp
// Test that the initial balances must be positive.
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="9a2a7-218">Za pomocą [ `try` `catch` instrukcji i](../../language-reference/keywords/try-catch.md) można oznaczyć blok kodu, który może generować wyjątki i przechwytywać te błędy, których oczekujesz.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-218">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="9a2a7-219">Możesz użyć tej samej techniki, aby przetestować kod, który zgłasza wyjątek dla salda ujemnego.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-219">You can use the same technique to test the code that throws an exception for a negative balance.</span></span> <span data-ttu-id="9a2a7-220">Dodaj następujący kod na końcu `Main` metody:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-220">Add the following code at the end of your `Main` method:</span></span>

```csharp
// Test for a negative balance.
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="9a2a7-221">Zapisz plik i wpisz, `dotnet run` Aby go wypróbować.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-221">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="9a2a7-222">Wyzwanie — Rejestruj wszystkie transakcje</span><span class="sxs-lookup"><span data-stu-id="9a2a7-222">Challenge - log all transactions</span></span>

<span data-ttu-id="9a2a7-223">Aby ukończyć ten samouczek, można napisać `GetAccountHistory` metodę, która tworzy `string` dla historii transakcji.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-223">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="9a2a7-224">Dodaj tę metodę do `BankAccount` typu:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-224">Add this method to the `BankAccount` type:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="History":::

<span data-ttu-id="9a2a7-225">Używa <xref:System.Text.StringBuilder> klasy do formatowania ciągu, który zawiera jeden wiersz dla każdej transakcji.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-225">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="9a2a7-226">W tych samouczkach pojawił się kod formatowania ciągu.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-226">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="9a2a7-227">Jeden nowy znak to `\t` .</span><span class="sxs-lookup"><span data-stu-id="9a2a7-227">One new character is `\t`.</span></span> <span data-ttu-id="9a2a7-228">Spowoduje to wstawienie karty w celu sformatowania danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-228">That inserts a tab to format the output.</span></span>

<span data-ttu-id="9a2a7-229">Dodaj ten wiersz, aby przetestować go w *program.cs*:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-229">Add this line to test it in *Program.cs*:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="9a2a7-230">Uruchom program, aby zobaczyć wyniki.</span><span class="sxs-lookup"><span data-stu-id="9a2a7-230">Run your program to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9a2a7-231">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="9a2a7-231">Next steps</span></span>

<span data-ttu-id="9a2a7-232">Jeśli zawiesz, że możesz zobaczyć źródło tego samouczka [w naszym repozytorium GitHub](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes).</span><span class="sxs-lookup"><span data-stu-id="9a2a7-232">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes).</span></span>

<span data-ttu-id="9a2a7-233">Możesz kontynuować pracę z samouczkiem [programowanie zorientowane obiektowo](object-oriented-programming.md) .</span><span class="sxs-lookup"><span data-stu-id="9a2a7-233">You can continue with the [object oriented programming](object-oriented-programming.md) tutorial.</span></span>

<span data-ttu-id="9a2a7-234">Więcej informacji na temat tych pojęć można znaleźć w następujących artykułach:</span><span class="sxs-lookup"><span data-stu-id="9a2a7-234">You can learn more about these concepts in these articles:</span></span>

- [<span data-ttu-id="9a2a7-235">if i else, instrukcje</span><span class="sxs-lookup"><span data-stu-id="9a2a7-235">If and else statement</span></span>](../../language-reference/keywords/if-else.md)
- [<span data-ttu-id="9a2a7-236">While, instrukcja</span><span class="sxs-lookup"><span data-stu-id="9a2a7-236">While statement</span></span>](../../language-reference/keywords/while.md)
- [<span data-ttu-id="9a2a7-237">do, instrukcja</span><span class="sxs-lookup"><span data-stu-id="9a2a7-237">Do statement</span></span>](../../language-reference/keywords/do.md)
- [<span data-ttu-id="9a2a7-238">For — instrukcja</span><span class="sxs-lookup"><span data-stu-id="9a2a7-238">For statement</span></span>](../../language-reference/keywords/for.md)
