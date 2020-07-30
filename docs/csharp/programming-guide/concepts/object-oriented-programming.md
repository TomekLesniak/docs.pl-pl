---
title: Programowanie zorientowane obiektowo (C#)
description: Język C# zapewnia pełną obsługę programowania zorientowanego obiektowo, w tym abstrakcję, hermetyzację, dziedziczenie i polimorfizm.
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 0c5495aefad73a2916ad6e2bd2bf3701d0868f24
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302818"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="dd25a-103">Programowanie zorientowane obiektowo (C#)</span><span class="sxs-lookup"><span data-stu-id="dd25a-103">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="dd25a-104">Język C# zapewnia pełną obsługę programowania zorientowanego obiektowo, w tym abstrakcję, hermetyzację, dziedziczenie i polimorfizm.</span><span class="sxs-lookup"><span data-stu-id="dd25a-104">C# provides full support for object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="dd25a-105">*Abstrakcja* oznacza ukrycie niepotrzebnych informacji od odbiorców typu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-105">*Abstraction* means hiding the unnecessary details from type consumers.</span></span>
- <span data-ttu-id="dd25a-106">*Hermetyzacja* oznacza, że grupa powiązanych właściwości, metod i innych elementów członkowskich jest traktowana jako pojedyncza jednostka lub obiekt.</span><span class="sxs-lookup"><span data-stu-id="dd25a-106">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="dd25a-107">*Dziedziczenie* opisuje możliwość tworzenia nowych klas na podstawie istniejącej klasy.</span><span class="sxs-lookup"><span data-stu-id="dd25a-107">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="dd25a-108">*Polimorfizm* oznacza, że można mieć wiele klas, które mogą być używane zamiennie, nawet jeśli każda klasa implementuje te same właściwości lub metody na różne sposoby.</span><span class="sxs-lookup"><span data-stu-id="dd25a-108">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="dd25a-109">Klasy i obiekty</span><span class="sxs-lookup"><span data-stu-id="dd25a-109">Classes and objects</span></span>

<span data-ttu-id="dd25a-110">*Kategoria warunki i* *obiekt* opisują *Typ* obiektów i *wystąpienia* klas odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="dd25a-110">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="dd25a-111">W związku z tym czynność tworzenia obiektu jest nazywana *tworzeniem wystąpień*.</span><span class="sxs-lookup"><span data-stu-id="dd25a-111">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="dd25a-112">Korzystając z strategii analogowej, Klasa jest planem, a obiekt jest kompilacją utworzoną z tego planu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-112">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="dd25a-113">Aby zdefiniować klasę:</span><span class="sxs-lookup"><span data-stu-id="dd25a-113">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="dd25a-114">Język C# udostępnia również typy nazywane *strukturami* , które są przydatne, gdy nie potrzebujesz obsługi dziedziczenia lub polimorfizmu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-114">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span> <span data-ttu-id="dd25a-115">Aby uzyskać więcej informacji, zobacz [Wybieranie między klasą i strukturą](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-115">For more information, see [Choosing between class and struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span></span>

<span data-ttu-id="dd25a-116">Aby zdefiniować strukturę:</span><span class="sxs-lookup"><span data-stu-id="dd25a-116">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="dd25a-117">Aby uzyskać więcej informacji, zobacz artykuły w słowach kluczowych [klasy](../../language-reference/keywords/class.md) i [struktury](../../language-reference/builtin-types/struct.md) .</span><span class="sxs-lookup"><span data-stu-id="dd25a-117">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="dd25a-118">Elementy członkowskie klasy</span><span class="sxs-lookup"><span data-stu-id="dd25a-118">Class members</span></span>

<span data-ttu-id="dd25a-119">Każda klasa może mieć różne *składowe klasy* , które zawierają właściwości opisujące dane klasy, metody definiujące zachowanie klasy oraz zdarzenia, które zapewniają komunikację między różnymi klasami i obiektami.</span><span class="sxs-lookup"><span data-stu-id="dd25a-119">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="dd25a-120">Właściwości i pola</span><span class="sxs-lookup"><span data-stu-id="dd25a-120">Properties and fields</span></span>

<span data-ttu-id="dd25a-121">Pola i właściwości reprezentują informacje, które zawiera obiekt.</span><span class="sxs-lookup"><span data-stu-id="dd25a-121">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="dd25a-122">Pola są podobne do zmiennych, ponieważ mogą być odczytywane lub ustawiane bezpośrednio, zgodnie z odpowiednimi modyfikatorami dostępu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-122">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="dd25a-123">Aby zdefiniować pole, do którego można uzyskać dostęp z wystąpień klasy:</span><span class="sxs-lookup"><span data-stu-id="dd25a-123">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="dd25a-124">Właściwości mają `get` i `set` metody dostępu, które zapewniają większą kontrolę nad sposobem ustawiania lub zwracania wartości.</span><span class="sxs-lookup"><span data-stu-id="dd25a-124">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="dd25a-125">Język C# umożliwia utworzenie prywatnego pola do przechowywania wartości właściwości lub użycie automatycznie wdrożonych właściwości, które tworzą to pole automatycznie w tle i zapewniają podstawową logikę dla procedur właściwości.</span><span class="sxs-lookup"><span data-stu-id="dd25a-125">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="dd25a-126">Aby zdefiniować zaimplementowaną Właściwość:</span><span class="sxs-lookup"><span data-stu-id="dd25a-126">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="dd25a-127">Jeśli trzeba wykonać pewne dodatkowe operacje odczytu i zapisu wartości właściwości, Zdefiniuj pole do przechowywania wartości właściwości i podaj podstawową logikę do przechowywania i pobierania:</span><span class="sxs-lookup"><span data-stu-id="dd25a-127">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

<span data-ttu-id="dd25a-128">Większość właściwości ma metody lub procedury ustawiające i pobierające wartość właściwości.</span><span class="sxs-lookup"><span data-stu-id="dd25a-128">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="dd25a-129">Można jednak utworzyć właściwości tylko do odczytu lub tylko do zapisu, aby uniemożliwić ich modyfikację lub odczytanie.</span><span class="sxs-lookup"><span data-stu-id="dd25a-129">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="dd25a-130">W języku C# można pominąć `get` `set` metodę lub właściwość.</span><span class="sxs-lookup"><span data-stu-id="dd25a-130">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="dd25a-131">Jednak właściwości zaimplementowane domyślnie nie mogą być tylko do zapisu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-131">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="dd25a-132">Właściwości, które są implementowane w trybie tylko do odczytu, można ustawić w konstruktorach klasy zawierającej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-132">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="dd25a-133">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="dd25a-133">For more information, see:</span></span>

- [<span data-ttu-id="dd25a-134">Pobierz</span><span class="sxs-lookup"><span data-stu-id="dd25a-134">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="dd25a-135">zbiór</span><span class="sxs-lookup"><span data-stu-id="dd25a-135">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="dd25a-136">Metody</span><span class="sxs-lookup"><span data-stu-id="dd25a-136">Methods</span></span>

<span data-ttu-id="dd25a-137">*Metoda* jest akcją, którą obiekt może wykonać.</span><span class="sxs-lookup"><span data-stu-id="dd25a-137">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="dd25a-138">Aby zdefiniować metodę klasy:</span><span class="sxs-lookup"><span data-stu-id="dd25a-138">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="dd25a-139">Klasa może mieć kilka implementacji lub *przeciążenia*tej samej metody, które różnią się liczbą parametrów lub typów parametrów.</span><span class="sxs-lookup"><span data-stu-id="dd25a-139">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="dd25a-140">Aby przeciążyć metodę:</span><span class="sxs-lookup"><span data-stu-id="dd25a-140">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="dd25a-141">W większości przypadków deklaruje metodę w ramach definicji klasy.</span><span class="sxs-lookup"><span data-stu-id="dd25a-141">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="dd25a-142">Jednak w języku C# obsługiwane są również *metody rozszerzające* , które umożliwiają dodawanie metod do istniejącej klasy poza rzeczywistą definicją klasy.</span><span class="sxs-lookup"><span data-stu-id="dd25a-142">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="dd25a-143">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="dd25a-143">For more information, see:</span></span>

- [<span data-ttu-id="dd25a-144">Metody</span><span class="sxs-lookup"><span data-stu-id="dd25a-144">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="dd25a-145">Metody rozszerzania</span><span class="sxs-lookup"><span data-stu-id="dd25a-145">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="dd25a-146">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="dd25a-146">Constructors</span></span>

<span data-ttu-id="dd25a-147">Konstruktory są metodami klasy, które są wykonywane automatycznie po utworzeniu obiektu danego typu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-147">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="dd25a-148">Konstruktory zazwyczaj inicjują elementy członkowskie danych nowego obiektu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-148">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="dd25a-149">Konstruktor można uruchomić tylko raz podczas tworzenia klasy.</span><span class="sxs-lookup"><span data-stu-id="dd25a-149">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="dd25a-150">Ponadto kod w konstruktorze zawsze jest uruchamiany przed jakimkolwiek innym kodem w klasie.</span><span class="sxs-lookup"><span data-stu-id="dd25a-150">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="dd25a-151">Można jednak utworzyć wiele przeciążeń konstruktora w taki sam sposób jak w przypadku innych metod.</span><span class="sxs-lookup"><span data-stu-id="dd25a-151">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="dd25a-152">Aby zdefiniować konstruktora dla klasy:</span><span class="sxs-lookup"><span data-stu-id="dd25a-152">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="dd25a-153">Aby uzyskać więcej informacji, zobacz [konstruktory](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-153">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="dd25a-154">Finalizatory</span><span class="sxs-lookup"><span data-stu-id="dd25a-154">Finalizers</span></span>

<span data-ttu-id="dd25a-155">Finalizator jest używany do destruktora wystąpień klas.</span><span class="sxs-lookup"><span data-stu-id="dd25a-155">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="dd25a-156">W programie .NET moduł zbierający elementy bezużyteczne automatycznie zarządza alokacją i ilością pamięci dla zarządzanych obiektów w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="dd25a-156">In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="dd25a-157">Jednak nadal mogą być potrzebne finalizatory do czyszczenia wszystkich niezarządzanych zasobów tworzonych przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="dd25a-157">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="dd25a-158">Może istnieć tylko jeden finalizator dla klasy.</span><span class="sxs-lookup"><span data-stu-id="dd25a-158">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="dd25a-159">Aby uzyskać więcej informacji na temat finalizatorów i wyrzucania elementów bezużytecznych w programie .NET, zobacz [odzyskiwanie pamięci](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-159">For more information about finalizers and garbage collection in .NET, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="dd25a-160">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="dd25a-160">Events</span></span>

<span data-ttu-id="dd25a-161">Zdarzenia umożliwiają klasie lub obiektowi powiadamianie innych klas lub obiektów w przypadku wystąpienia czegoś zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="dd25a-161">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="dd25a-162">Klasa, która wysyła (lub podnosi) zdarzenie, jest nazywana *wydawcą* i klasy, które odbierają (lub obsługują) zdarzenie są nazywane *subskrybentami*.</span><span class="sxs-lookup"><span data-stu-id="dd25a-162">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="dd25a-163">Aby uzyskać więcej informacji o zdarzeniach, sposobie ich podniesienia i obsłudze, zobacz [zdarzenia](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-163">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="dd25a-164">Aby zadeklarować zdarzenie w klasie, użyj słowa kluczowego [zdarzenia](../../language-reference/keywords/event.md) .</span><span class="sxs-lookup"><span data-stu-id="dd25a-164">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="dd25a-165">Aby zgłosić zdarzenie, wywołaj delegata zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="dd25a-165">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="dd25a-166">Aby subskrybować zdarzenie, użyj `+=` operatora; aby anulować subskrypcję zdarzenia, użyj `-=` operatora.</span><span class="sxs-lookup"><span data-stu-id="dd25a-166">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="dd25a-167">Klasy zagnieżdżone</span><span class="sxs-lookup"><span data-stu-id="dd25a-167">Nested classes</span></span>

<span data-ttu-id="dd25a-168">Klasa zdefiniowana w innej klasie jest nazywana *zagnieżdżoną*.</span><span class="sxs-lookup"><span data-stu-id="dd25a-168">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="dd25a-169">Domyślnie Klasa zagnieżdżona jest prywatna.</span><span class="sxs-lookup"><span data-stu-id="dd25a-169">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="dd25a-170">Aby utworzyć wystąpienie klasy zagnieżdżonej, użyj nazwy klasy kontenera, po której następuje kropka, a następnie po której następuje nazwa klasy zagnieżdżonej:</span><span class="sxs-lookup"><span data-stu-id="dd25a-170">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="dd25a-171">Modyfikatory dostępu i poziomy dostępu</span><span class="sxs-lookup"><span data-stu-id="dd25a-171">Access modifiers and access levels</span></span>

<span data-ttu-id="dd25a-172">Wszystkie klasy i elementy członkowskie klasy mogą określać poziom dostępu udostępniany innym klasom przy użyciu *modyfikatorów dostępu*.</span><span class="sxs-lookup"><span data-stu-id="dd25a-172">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="dd25a-173">Dostępne są następujące Modyfikatory dostępu:</span><span class="sxs-lookup"><span data-stu-id="dd25a-173">The following access modifiers are available:</span></span>

| <span data-ttu-id="dd25a-174">Modyfikator języka C#</span><span class="sxs-lookup"><span data-stu-id="dd25a-174">C# Modifier</span></span> | <span data-ttu-id="dd25a-175">Definicja</span><span class="sxs-lookup"><span data-stu-id="dd25a-175">Definition</span></span> |
|--|--|
| [<span data-ttu-id="dd25a-176">public</span><span class="sxs-lookup"><span data-stu-id="dd25a-176">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="dd25a-177">Do typu lub elementu członkowskiego można uzyskać dostęp za pomocą dowolnego innego kodu w tym samym zestawie lub innym zestawie, który odwołuje się do niego.</span><span class="sxs-lookup"><span data-stu-id="dd25a-177">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="dd25a-178">użytek</span><span class="sxs-lookup"><span data-stu-id="dd25a-178">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="dd25a-179">Do typu lub elementu członkowskiego można uzyskać dostęp tylko w kodzie w tej samej klasie.</span><span class="sxs-lookup"><span data-stu-id="dd25a-179">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="dd25a-180">protected</span><span class="sxs-lookup"><span data-stu-id="dd25a-180">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="dd25a-181">Do typu lub elementu członkowskiego można uzyskać dostęp tylko za pomocą kodu w tej samej klasie lub w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-181">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="dd25a-182">internal</span><span class="sxs-lookup"><span data-stu-id="dd25a-182">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="dd25a-183">Do typu lub elementu członkowskiego można uzyskać dostęp za pomocą dowolnego kodu w tym samym zestawie, ale nie z innego zestawu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-183">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="dd25a-184">protected internal</span><span class="sxs-lookup"><span data-stu-id="dd25a-184">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="dd25a-185">Do typu lub elementu członkowskiego można uzyskać dostęp za pomocą dowolnego kodu w tym samym zestawie lub przez dowolną klasę pochodną w innym zestawie.</span><span class="sxs-lookup"><span data-stu-id="dd25a-185">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="dd25a-186">private protected</span><span class="sxs-lookup"><span data-stu-id="dd25a-186">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="dd25a-187">Do typu lub elementu członkowskiego można uzyskać dostęp za pomocą kodu w tej samej klasie lub w klasie pochodnej w ramach zestawu klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-187">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="dd25a-188">Aby uzyskać więcej informacji, zobacz [Modyfikatory dostępu](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-188">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="dd25a-189">Tworzenie wystąpień klas</span><span class="sxs-lookup"><span data-stu-id="dd25a-189">Instantiating classes</span></span>

<span data-ttu-id="dd25a-190">Aby utworzyć obiekt, należy utworzyć wystąpienie klasy, lub stworzyć wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="dd25a-190">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="dd25a-191">Po utworzeniu wystąpienia klasy można przypisać wartości do właściwości i pól wystąpienia oraz wywołać metody klasy.</span><span class="sxs-lookup"><span data-stu-id="dd25a-191">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="dd25a-192">Aby przypisać wartości do właściwości podczas procesu tworzenia wystąpienia klasy, należy użyć inicjatorów obiektów:</span><span class="sxs-lookup"><span data-stu-id="dd25a-192">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="dd25a-193">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="dd25a-193">For more information, see:</span></span>

- [<span data-ttu-id="dd25a-194">Operator new</span><span class="sxs-lookup"><span data-stu-id="dd25a-194">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="dd25a-195">Inicjatory obiektów i kolekcji</span><span class="sxs-lookup"><span data-stu-id="dd25a-195">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="dd25a-196">Klasy statyczne i składowe</span><span class="sxs-lookup"><span data-stu-id="dd25a-196">Static Classes and Members</span></span>

<span data-ttu-id="dd25a-197">Statyczny element członkowski klasy jest właściwością, procedurą lub polem, które są współużytkowane przez wszystkie wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="dd25a-197">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="dd25a-198">Aby zdefiniować statyczną składową:</span><span class="sxs-lookup"><span data-stu-id="dd25a-198">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="dd25a-199">Aby uzyskać dostęp do statycznego elementu członkowskiego, należy użyć nazwy klasy bez tworzenia obiektu tej klasy:</span><span class="sxs-lookup"><span data-stu-id="dd25a-199">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="dd25a-200">Klasy statyczne w języku C# mają tylko statyczne elementy członkowskie i nie można tworzyć wystąpień.</span><span class="sxs-lookup"><span data-stu-id="dd25a-200">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="dd25a-201">Statyczne elementy członkowskie również nie mogą uzyskać dostępu do właściwości niestatycznych, pól ani metod</span><span class="sxs-lookup"><span data-stu-id="dd25a-201">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="dd25a-202">Aby uzyskać więcej informacji, zobacz: [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-202">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="dd25a-203">Typy anonimowe</span><span class="sxs-lookup"><span data-stu-id="dd25a-203">Anonymous types</span></span>

<span data-ttu-id="dd25a-204">Typy anonimowe umożliwiają tworzenie obiektów bez konieczności pisania definicji klasy dla typu danych.</span><span class="sxs-lookup"><span data-stu-id="dd25a-204">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="dd25a-205">Zamiast tego kompilator generuje klasę dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="dd25a-205">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="dd25a-206">Klasa nie ma użytecznej nazwy i zawiera właściwości określone w deklaracji obiektu.</span><span class="sxs-lookup"><span data-stu-id="dd25a-206">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="dd25a-207">Aby utworzyć wystąpienie typu anonimowego:</span><span class="sxs-lookup"><span data-stu-id="dd25a-207">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="dd25a-208">Aby uzyskać więcej informacji, zobacz: [Typy anonimowe](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-208">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="dd25a-209">Dziedziczenie</span><span class="sxs-lookup"><span data-stu-id="dd25a-209">Inheritance</span></span>

<span data-ttu-id="dd25a-210">Dziedziczenie umożliwia utworzenie nowej klasy, która ponownie używa, rozszerza i modyfikuje zachowanie zdefiniowane w innej klasie.</span><span class="sxs-lookup"><span data-stu-id="dd25a-210">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="dd25a-211">Klasa, której członkowie są dziedziczone jest nazywana *klasą bazową*, a Klasa, która dziedziczy tych członków, nosi nazwę *klasy pochodnej*.</span><span class="sxs-lookup"><span data-stu-id="dd25a-211">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="dd25a-212">Jednak wszystkie klasy w języku C# niejawnie dziedziczą z <xref:System.Object> klasy, która obsługuje hierarchię klas .NET i zapewnia usługi niskiego poziomu dla wszystkich klas.</span><span class="sxs-lookup"><span data-stu-id="dd25a-212">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="dd25a-213">Język C# nie obsługuje dziedziczenia wielokrotnego.</span><span class="sxs-lookup"><span data-stu-id="dd25a-213">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="dd25a-214">Oznacza to, że można określić tylko jedną klasę bazową dla klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-214">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="dd25a-215">Aby dziedziczyć z klasy bazowej:</span><span class="sxs-lookup"><span data-stu-id="dd25a-215">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="dd25a-216">Domyślnie wszystkie klasy mogą być dziedziczone.</span><span class="sxs-lookup"><span data-stu-id="dd25a-216">By default all classes can be inherited.</span></span> <span data-ttu-id="dd25a-217">Można jednak określić, czy Klasa nie może być używana jako klasa bazowa, ani utworzyć klasy, która może być używana tylko jako klasa bazowa.</span><span class="sxs-lookup"><span data-stu-id="dd25a-217">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="dd25a-218">Aby określić, że Klasa nie może być używana jako klasa bazowa:</span><span class="sxs-lookup"><span data-stu-id="dd25a-218">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="dd25a-219">Aby określić, że Klasa może być używana tylko jako klasa bazowa i nie można utworzyć wystąpienia:</span><span class="sxs-lookup"><span data-stu-id="dd25a-219">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="dd25a-220">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="dd25a-220">For more information, see:</span></span>

- [<span data-ttu-id="dd25a-221">sealed</span><span class="sxs-lookup"><span data-stu-id="dd25a-221">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="dd25a-222">streszczeń</span><span class="sxs-lookup"><span data-stu-id="dd25a-222">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="dd25a-223">Zastępowanie elementów członkowskich</span><span class="sxs-lookup"><span data-stu-id="dd25a-223">Overriding Members</span></span>

<span data-ttu-id="dd25a-224">Domyślnie Klasa pochodna dziedziczy wszystkich członków z jej klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-224">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="dd25a-225">Jeśli chcesz zmienić zachowanie dziedziczonego elementu członkowskiego, musisz go zastąpić.</span><span class="sxs-lookup"><span data-stu-id="dd25a-225">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="dd25a-226">Oznacza to, że można zdefiniować nową implementację metody, właściwości lub zdarzenia w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-226">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="dd25a-227">Poniższe Modyfikatory służą do kontrolowania sposobu przesłania właściwości i metod:</span><span class="sxs-lookup"><span data-stu-id="dd25a-227">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="dd25a-228">Modyfikator języka C#</span><span class="sxs-lookup"><span data-stu-id="dd25a-228">C# Modifier</span></span> | <span data-ttu-id="dd25a-229">Definicja</span><span class="sxs-lookup"><span data-stu-id="dd25a-229">Definition</span></span> |
|--|--|
| [<span data-ttu-id="dd25a-230">wirtualnej</span><span class="sxs-lookup"><span data-stu-id="dd25a-230">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="dd25a-231">Zezwala na przesłanianie składowej klasy w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-231">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="dd25a-232">override</span><span class="sxs-lookup"><span data-stu-id="dd25a-232">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="dd25a-233">Przesłania element członkowski wirtualny (zastępujący) zdefiniowany w klasie bazowej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-233">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="dd25a-234">streszczeń</span><span class="sxs-lookup"><span data-stu-id="dd25a-234">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="dd25a-235">Wymaga, aby element członkowski klasy był zastępowany w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="dd25a-235">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="dd25a-236">new, modyfikator</span><span class="sxs-lookup"><span data-stu-id="dd25a-236">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="dd25a-237">Ukrywa składową dziedziczoną z klasy bazowej</span><span class="sxs-lookup"><span data-stu-id="dd25a-237">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="dd25a-238">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="dd25a-238">Interfaces</span></span>

<span data-ttu-id="dd25a-239">Interfejsy, takie jak klasy, definiują zestaw właściwości, metod i zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="dd25a-239">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="dd25a-240">Ale w przeciwieństwie do klas, interfejsy nie zapewniają implementacji.</span><span class="sxs-lookup"><span data-stu-id="dd25a-240">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="dd25a-241">Są one implementowane przez klasy i zdefiniowane jako osobne jednostki z klas.</span><span class="sxs-lookup"><span data-stu-id="dd25a-241">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="dd25a-242">Interfejs reprezentuje kontrakt, w którym Klasa implementująca interfejs musi implementować każdy aspekt tego interfejsu dokładnie tak, jak jest zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="dd25a-242">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="dd25a-243">Aby zdefiniować interfejs:</span><span class="sxs-lookup"><span data-stu-id="dd25a-243">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="dd25a-244">Aby zaimplementować interfejs w klasie:</span><span class="sxs-lookup"><span data-stu-id="dd25a-244">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="dd25a-245">Aby uzyskać więcej informacji, zobacz artykuł Przewodnik programowania dotyczący [interfejsów](../interfaces/index.md) i artykułu referencyjnego języka dla słowa kluczowego [Interface](../../language-reference/keywords/interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dd25a-245">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="dd25a-246">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="dd25a-246">Generics</span></span>

<span data-ttu-id="dd25a-247">Klasy, struktury, interfejsy i metody w programie .NET mogą zawierać *parametry typu* , które definiują typy obiektów, które mogą być przechowywane lub używane.</span><span class="sxs-lookup"><span data-stu-id="dd25a-247">Classes, structures, interfaces, and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="dd25a-248">Najbardziej typowym przykładem typów ogólnych jest kolekcja, w której można określić typ obiektów, które mają być przechowywane w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="dd25a-248">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="dd25a-249">Aby zdefiniować klasę generyczną:</span><span class="sxs-lookup"><span data-stu-id="dd25a-249">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="dd25a-250">Aby utworzyć wystąpienie klasy generycznej:</span><span class="sxs-lookup"><span data-stu-id="dd25a-250">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="dd25a-251">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="dd25a-251">For more information, see:</span></span>

- [<span data-ttu-id="dd25a-252">Typy ogólne w .NET</span><span class="sxs-lookup"><span data-stu-id="dd25a-252">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="dd25a-253">Typy ogólne — Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="dd25a-253">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="dd25a-254">Delegaci</span><span class="sxs-lookup"><span data-stu-id="dd25a-254">Delegates</span></span>

<span data-ttu-id="dd25a-255">*Delegat* jest typem, który definiuje sygnaturę metody i może podać odwołanie do dowolnej metody ze zgodną sygnaturą.</span><span class="sxs-lookup"><span data-stu-id="dd25a-255">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="dd25a-256">Metodę można wywołać (lub wywołać) za pomocą delegata.</span><span class="sxs-lookup"><span data-stu-id="dd25a-256">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="dd25a-257">Delegaty służą do przekazywania metod jako argumentów do innych metod.</span><span class="sxs-lookup"><span data-stu-id="dd25a-257">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="dd25a-258">Programy obsługi zdarzeń to po prostu metody, które są wywoływane za pośrednictwem delegatów.</span><span class="sxs-lookup"><span data-stu-id="dd25a-258">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="dd25a-259">Aby uzyskać więcej informacji o używaniu delegatów w obsłudze zdarzeń, zobacz [zdarzenia](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-259">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="dd25a-260">Aby utworzyć delegata:</span><span class="sxs-lookup"><span data-stu-id="dd25a-260">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="dd25a-261">Aby utworzyć odwołanie do metody, która jest zgodna z sygnaturą określoną przez delegata:</span><span class="sxs-lookup"><span data-stu-id="dd25a-261">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void SampleMethod(string message)
    {
        // Add code here.
    }

    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="dd25a-262">Aby uzyskać więcej informacji, zobacz artykuł Przewodnik programowania dotyczący [delegatów](../delegates/index.md) i artykuł referencyjny języka w słowie kluczowym [delegata](../../language-reference/builtin-types/reference-types.md) .</span><span class="sxs-lookup"><span data-stu-id="dd25a-262">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd25a-263">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dd25a-263">See also</span></span>

- [<span data-ttu-id="dd25a-264">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="dd25a-264">C# Programming Guide</span></span>](../index.md)
