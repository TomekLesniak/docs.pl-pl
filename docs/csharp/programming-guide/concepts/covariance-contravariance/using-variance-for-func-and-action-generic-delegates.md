---
title: Korzystanie z wariancji dla delegatów funkcji Func i Action (C#)
description: Dowiedz się więcej o używaniu kowariancji i kontrawariancja w delegatach elementów Func i Action, aby zapewnić większą elastyczność w kodzie.
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: 613470d7870aa6a917d19904a92e56f0e61f1ed9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176347"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a>Korzystanie z wariancji dla delegatów funkcji Func i Action (C#)

W poniższych przykładach pokazano, jak używać kowariancji i kontrawariancja w `Func` i `Action` delegatów ogólnych, aby umożliwić ponowne użycie metod i zapewnić większą elastyczność w kodzie.  
  
 Aby uzyskać więcej informacji na temat kowariancji i kontrawariancja, zobacz [Wariancja w delegatach (C#)](./variance-in-delegates.md).  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>Używanie delegatów z parametrami typu współwariantowego  

 Poniższy przykład ilustruje zalety obsługi kowariancji w `Func` delegatach ogólnych. `FindByTitle`Metoda przyjmuje parametr `String` typu i zwraca obiekt `Employee` typu. Można jednak przypisać tę metodę do `Func<String, Person>` delegata, ponieważ `Employee` dziedziczy `Person` .  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate
        // that returns a more derived type
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>Korzystanie z delegatów z parametrami typu kontrawariantne  

 Poniższy przykład ilustruje zalety obsługi kontrawariancja w `Action` delegatach ogólnych. `AddToContacts`Metoda przyjmuje parametr `Person` typu. Można jednak przypisać tę metodę do `Action<Employee>` delegata, ponieważ `Employee` dziedziczy `Person` .  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate
        // that accepts a less derived parameter to a delegate
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [Kowariancja i kontrawariancja (C#)](./index.md)
- [Typy ogólne](../../../../standard/generics/index.md)
