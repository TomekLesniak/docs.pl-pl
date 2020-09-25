---
title: Korzystanie z wariancji w interfejsach dla kolekcji ogólnych (C#)
description: Dowiedz się, jak używać interfejsów współvariant i kontrawariantne dla kolekcji ogólnych. Zobacz przykłady konwersji i porównywania kolekcji ogólnych.
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: a896fe8fda3d9ad08de9a09c6a172f7d75335e7d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176308"
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a>Korzystanie z wariancji w interfejsach dla kolekcji ogólnych (C#)

Interfejs współdzielny umożliwia metodom Zwracanie większej liczby typów pochodnych niż określone w interfejsie. Interfejs kontrawariantne umożliwia jej metodom akceptowanie parametrów o mniejszych typach pochodnych niż określone w interfejsie.  
  
 W .NET Framework 4, kilka istniejących interfejsów stał się współwariantem i kontrawariantne. Obejmują one <xref:System.Collections.Generic.IEnumerable%601> i <xref:System.IComparable%601> . Dzięki temu można ponownie użyć metod, które działają z ogólnymi kolekcjami typów podstawowych dla kolekcji typów pochodnych.  
  
 Aby uzyskać listę interfejsów wariantów w programie .NET, zobacz [Wariancja w interfejsach ogólnych (C#)](./variance-in-generic-interfaces.md).  
  
## <a name="converting-generic-collections"></a>Konwertowanie kolekcji ogólnych  

 Poniższy przykład ilustruje zalety obsługi kowariancji w <xref:System.Collections.Generic.IEnumerable%601> interfejsie. `PrintFullName`Metoda akceptuje kolekcję `IEnumerable<Person>` typu jako parametr. Można jednak ponownie użyć go dla kolekcji `IEnumerable<Employee>` typu, ponieważ `Employee` dziedziczy `Person` .  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a>Porównywanie kolekcji ogólnych  

 Poniższy przykład ilustruje zalety obsługi kontrawariancja w <xref:System.Collections.Generic.IComparer%601> interfejsie. Klasa `PersonComparer` implementuje interfejs `IComparer<Person>`. Można jednak ponownie użyć tej klasy do porównania sekwencji obiektów `Employee` typu, ponieważ `Employee` dziedziczy `Person` .  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [Wariancja w interfejsach ogólnych (C#)](./variance-in-generic-interfaces.md)
