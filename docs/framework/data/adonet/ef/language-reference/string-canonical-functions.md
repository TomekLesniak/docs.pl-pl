---
title: Funkcje ciągów Canonical
ms.date: 03/30/2017
ms.assetid: 5e2cbebd-5df3-47c7-b0e2-49a17ab22bfb
ms.openlocfilehash: 5a7889511d9e8e276ba026c37f4cd8a4aeba156c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173656"
---
# <a name="string-canonical-functions"></a>Funkcje ciągów Canonical

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] zawiera funkcje w postaci kanonicznej.  
  
## <a name="remarks"></a>Uwagi  

 W poniższej tabeli przedstawiono [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funkcje kanoniczne ciągu.  
  
|Funkcja|Opis|  
|--------------|-----------------|  
|`Concat(string1, string2)`|Zwraca ciąg, który zawiera `string2` dołączone do `string1` .<br /><br /> **Argumenty**<br /><br /> `string1`: Ciąg, do którego `string2` jest dołączany.<br /><br /> `string2`: Ciąg, który jest dołączany do `string1` .<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`. Wystąpi błąd, jeśli długość ciągu wartości zwracanej jest większa niż maksymalna dozwolona długość.<br /><br /> **Przykład**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Contains(string, target)`|Zwraca wartość, `true` Jeśli `target` jest zawarta w `string` .<br /><br /> **Argumenty**<br /><br /> `string`: Przeszukiwany ciąg.<br /><br /> `target`: Docelowy ciąg, który jest wyszukiwany.<br /><br /> **Wartość zwracana**<br /><br /> `true` Jeśli `target` jest zawarta w `string` ; w przeciwnym razie `false` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns true.`<br /><br /> `Contains('abc', 'bc')`|  
|`EndsWith(string, target)`|Zwraca wartość, jeśli kończyć się znakiem `true` `target` `string` .<br /><br /> **Argumenty**<br /><br /> `string`: Przeszukiwany ciąg.<br /><br /> `target`: Przeszukiwany ciąg docelowy na końcu `string` .<br /><br /> **Wartość zwracana**<br /><br /> `True``string`w przypadku zakończenia z `target` ; w przeciwnym razie `false` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns true.`<br /><br /> `EndsWith('abc', 'bc')`**Uwaga:**  Jeśli używasz dostawcy danych SQL Server, ta funkcja zwraca wartość, `false` Jeśli ciąg jest przechowywany w kolumnie ciągu o stałej długości i `target` jest stałą. W takim przypadku przeszukiwany jest cały ciąg, w tym wszystkie spacje końcowe uzupełniania. Możliwym obejściem jest przycinanie danych w ciągu o stałej długości, jak w poniższym przykładzie: `EndsWith(TRIM(string), target)`|  
|`IndexOf(target, string)`|Zwraca pozycję `target` wewnątrz `string` lub wartość 0, jeśli nie można jej odnaleźć. Zwraca wartość 1, aby wskazać początek `string` . Numerowanie indeksu rozpoczyna się od 1.<br /><br /> **Argumenty**<br /><br /> `target`: Ciąg, który jest wyszukiwany.<br /><br /> `string`: Przeszukiwany ciąg.<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 4.`<br /><br /> `IndexOf('xyz', 'abcxyz')`|  
|`Left(string, length)`|Zwraca pierwsze `length` znaki z lewej strony `string` . Jeśli długość `string` jest mniejsza niż `length` , zwracany jest cały ciąg.<br /><br /> **Argumenty**<br /><br /> `string`: A `String` .<br /><br /> `length`: `Int16` , `Int32` , `Int64` , Lub `Byte` . `length` nie może być mniejsza od zera.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns abc.`<br /><br /> `Left('abcxyz', 3)`|  
|`Length(string)`|Zwraca ( `Int32` ) Długość ciągu znaków.<br /><br /> **Argumenty**<br /><br /> `string`: A `String` .<br /><br /> **Wartość zwracana**<br /><br /> A `Int32` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns 6.`<br /><br /> `Legth('abcxyz')`|  
|`LTrim(string)`|Zwraca `string` bez wiodącego odstępu.<br /><br /> **Argumenty**<br /><br /> Klasa `String`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns abc.`<br /><br /> `LTrim('   abc')`|  
|`Replace(string1, string2, string3)`|Zwraca `string1` , ze wszystkimi wystąpieniami `string2` zamienionymi przez `string3` .<br /><br /> **Argumenty**<br /><br /> Klasa `String`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Reverse(string)`|Zwraca `string` z kolejnością znaków odwróconych.<br /><br /> **Argumenty**<br /><br /> Klasa `String`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns dcba.`<br /><br /> `Reverse('abcd')`|  
|`Right(string, length)`|Zwraca ostatnie `length` znaki z `string` . Jeśli długość `string` jest mniejsza niż `length` , zwracany jest cały ciąg.<br /><br /> **Argumenty**<br /><br /> `string`: A `String` .<br /><br /> `length`: `Int16` , `Int32` , `Int64` , Lub `Byte` . `length` nie może być mniejsza od zera.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Right('abcxyz', 3)`|  
|`RTrim(string)`|Zwraca `string` bez końcowego odstępu.<br /><br /> **Argumenty**<br /><br /> Klasa `String`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.|  
|`Substring(string, start, length)`|Zwraca podciąg ciągu zaczynający się na pozycji `start` o długości `length` znaków. Początek 1 wskazuje pierwszy znak ciągu. Numerowanie indeksu rozpoczyna się od 1.<br /><br /> **Argumenty**<br /><br /> `string`: A `String` .<br /><br /> `start`: `Int16` , `Int32` , `Int64` I `Byte` . `start` nie może być mniejsze niż jeden.<br /><br /> `length`: `Int16` , `Int32` , `Int64` I `Byte` . `length` nie może być mniejsza od zera.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Substring('abcxyz', 4, 3)`|  
|`StartsWith(string, target)`|Zwraca wartość, `true` Jeśli `string` zaczyna się od `target` .<br /><br /> **Argumenty**<br /><br /> `string`: Przeszukiwany ciąg.<br /><br /> `target`: Przeszukiwany ciąg docelowy na początku `string` .<br /><br /> **Wartość zwracana**<br /><br /> `True` Jeśli `string` zaczyna się od `target` ; w przeciwnym razie `false` .<br /><br /> **Przykład**<br /><br /> `-- The following example returns true.`<br /><br /> `StartsWith('abc', 'ab')`|  
|`ToLower(string)`|Zwraca `string` z dużymi znakami przekonwertowanymi na małe litery.<br /><br /> **Argumenty**<br /><br /> Klasa `String`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns abc.`<br /><br /> `ToLower('ABC')`|  
|`ToUpper(string)`|Zwraca `string` małe litery konwertowane na wielkie litery.<br /><br /> **Argumenty**<br /><br /> Klasa `String`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns ABC.`<br /><br /> `ToUpper('abc')`|  
|`Trim(string)`|Zwraca `string` bez odstępów wiodących i końcowych.<br /><br /> **Argumenty**<br /><br /> Klasa `String`.<br /><br /> **Wartość zwracana**<br /><br /> Klasa `String`.<br /><br /> **Przykład**<br /><br /> `-- The following example returns abc.`<br /><br /> `Trim('      abc   ')`|  
  
 Te funkcje zostaną zwrócone, `null` Jeśli dane `null` wejściowe.  
  
 Równoważne funkcje są dostępne w dostawcy zarządzanym przez klienta programu Microsoft SQL. Aby uzyskać więcej informacji, zobacz temat [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Zobacz też

- [Funkcje Canonical](canonical-functions.md)
