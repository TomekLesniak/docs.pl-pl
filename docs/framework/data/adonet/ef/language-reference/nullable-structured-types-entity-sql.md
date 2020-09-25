---
title: Typy strukturalne dopuszczające wartość null (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: fc2230401ef98c005ab52a845de37482c0dcf698
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202267"
---
# <a name="nullable-structured-types-entity-sql"></a>Typy strukturalne dopuszczające wartość null (Entity SQL)

`null`Wystąpienie typu strukturalnego jest wystąpieniem, które nie istnieje. Różni się to od istniejącego wystąpienia, w którym wszystkie właściwości mają `null` wartości.  
  
 W tym temacie opisano typy strukturalne dopuszczające wartość null, w tym typy dopuszczające wartości null i które wzorce kodu tworzą `null` wystąpienia typów ze strukturą dopuszczającą wartość null.  
  
## <a name="kinds-of-nullable-structured-types"></a>Rodzaje typów strukturalnych dopuszczających wartość null  

 Istnieją trzy rodzaje typów struktur dopuszczających wartości null:  
  
- Typy wierszy.  
  
- Typy złożone.  
  
- Typy jednostek.  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a>Wzorce kodu generujące puste wystąpienia typów strukturalnych  

 Następujące scenariusze tworzą `null` wystąpienia:  
  
- Kształtowanie `null` jako typ strukturalny:  
  
    ```sql  
    TREAT (NULL AS StructuredType)  
    ```  
  
- Przerzutowanie typu podstawowego na typ pochodny:  
  
    ```sql  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- Sprzężenie zewnętrzne w przypadku wartości false:  
  
    ```sql  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --lub  
  
    ```sql  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --lub  
  
    ```sql  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- Odwołuje się do `null` odwołania:  
  
    ```sql  
    DEREF(NullRef)  
    ```  
  
- Uzyskiwanie ANYELEMENT z pustej kolekcji:  
  
    ```sql  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- Sprawdzanie `null` wystąpień typów strukturalnych:  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie jednostki SQL](entity-sql-overview.md)
