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
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a><span data-ttu-id="7eee4-103">Korzystanie z wariancji dla delegatów funkcji Func i Action (C#)</span><span class="sxs-lookup"><span data-stu-id="7eee4-103">Using Variance for Func and Action Generic Delegates (C#)</span></span>

<span data-ttu-id="7eee4-104">W poniższych przykładach pokazano, jak używać kowariancji i kontrawariancja w `Func` i `Action` delegatów ogólnych, aby umożliwić ponowne użycie metod i zapewnić większą elastyczność w kodzie.</span><span class="sxs-lookup"><span data-stu-id="7eee4-104">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="7eee4-105">Aby uzyskać więcej informacji na temat kowariancji i kontrawariancja, zobacz [Wariancja w delegatach (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="7eee4-105">For more information about covariance and contravariance, see [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="7eee4-106">Używanie delegatów z parametrami typu współwariantowego</span><span class="sxs-lookup"><span data-stu-id="7eee4-106">Using Delegates with Covariant Type Parameters</span></span>  

 <span data-ttu-id="7eee4-107">Poniższy przykład ilustruje zalety obsługi kowariancji w `Func` delegatach ogólnych.</span><span class="sxs-lookup"><span data-stu-id="7eee4-107">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="7eee4-108">`FindByTitle`Metoda przyjmuje parametr `String` typu i zwraca obiekt `Employee` typu.</span><span class="sxs-lookup"><span data-stu-id="7eee4-108">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="7eee4-109">Można jednak przypisać tę metodę do `Func<String, Person>` delegata, ponieważ `Employee` dziedziczy `Person` .</span><span class="sxs-lookup"><span data-stu-id="7eee4-109">However, you can assign this method to the `Func<String, Person>` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="7eee4-110">Korzystanie z delegatów z parametrami typu kontrawariantne</span><span class="sxs-lookup"><span data-stu-id="7eee4-110">Using Delegates with Contravariant Type Parameters</span></span>  

 <span data-ttu-id="7eee4-111">Poniższy przykład ilustruje zalety obsługi kontrawariancja w `Action` delegatach ogólnych.</span><span class="sxs-lookup"><span data-stu-id="7eee4-111">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="7eee4-112">`AddToContacts`Metoda przyjmuje parametr `Person` typu.</span><span class="sxs-lookup"><span data-stu-id="7eee4-112">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="7eee4-113">Można jednak przypisać tę metodę do `Action<Employee>` delegata, ponieważ `Employee` dziedziczy `Person` .</span><span class="sxs-lookup"><span data-stu-id="7eee4-113">However, you can assign this method to the `Action<Employee>` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7eee4-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7eee4-114">See also</span></span>

- [<span data-ttu-id="7eee4-115">Kowariancja i kontrawariancja (C#)</span><span class="sxs-lookup"><span data-stu-id="7eee4-115">Covariance and Contravariance (C#)</span></span>](./index.md)
- [<span data-ttu-id="7eee4-116">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="7eee4-116">Generics</span></span>](../../../../standard/generics/index.md)
