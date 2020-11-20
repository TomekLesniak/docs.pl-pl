---
title: Sprawdzanie, czy format poczty e-mail ciągów jest prawidłowy
description: Zapoznaj się z przykładem, jak wyrażenie regularne sprawdza, czy ciągi są w prawidłowym formacie poczty e-mail w programie .NET.
ms.date: 06/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET], examples [Visual Basic]
- email [.NET], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
ms.openlocfilehash: 88ff326e16ede6a422e9403b71905845014c4c25
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982495"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a><span data-ttu-id="38f5b-103">Sprawdzanie, czy format poczty e-mail ciągów jest prawidłowy</span><span class="sxs-lookup"><span data-stu-id="38f5b-103">How to verify that strings are in valid email format</span></span>

<span data-ttu-id="38f5b-104">Poniższy przykład używa wyrażenia regularnego, aby sprawdzić, czy ciąg jest w prawidłowym formacie poczty e-mail.</span><span class="sxs-lookup"><span data-stu-id="38f5b-104">The following example uses a regular expression to verify that a string is in valid email format.</span></span>

<span data-ttu-id="38f5b-105">To wyrażenie regularne jest proste względem tego, czego można używać jako wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="38f5b-105">This regular expression is comparatively simple to what can actually be used as an email.</span></span> <span data-ttu-id="38f5b-106">Użycie wyrażenia regularnego do weryfikacji wiadomości e-mail jest przydatne, aby upewnić się, że struktura poczty e-mail jest poprawna, ale nie jest to podstawienie w celu sprawdzenia, czy wiadomość e-mail rzeczywiście istnieje.</span><span class="sxs-lookup"><span data-stu-id="38f5b-106">Using a regular expression to validate an email is useful to make sure the structure of an email is correct, but it isn't a substitution for verifying the email actually exists.</span></span>

<span data-ttu-id="38f5b-107">✔️ Użyj małego wyrażenia regularnego, aby sprawdzić poprawność struktury wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="38f5b-107">✔️ DO use a small regular expression to check for the valid structure of an email.</span></span>

<span data-ttu-id="38f5b-108">✔️ wysłać testową wiadomość e-mail na adres podany przez użytkownika aplikacji.</span><span class="sxs-lookup"><span data-stu-id="38f5b-108">✔️ DO send a test email to the address provided by a user of your app.</span></span>

<span data-ttu-id="38f5b-109">❌ NIE używaj wyrażenia regularnego jako jedynego sposobu weryfikacji wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="38f5b-109">❌ DON'T use a regular expression as the only way you validate an email.</span></span>

<span data-ttu-id="38f5b-110">Jeśli spróbujesz utworzyć _idealne_ wyrażenie regularne, aby sprawdzić, czy struktura poczty e-mail jest poprawna, wyrażenie staje się bardziej skomplikowane, ponieważ niezwykle trudno debugować lub poprawić.</span><span class="sxs-lookup"><span data-stu-id="38f5b-110">If you try to create the _perfect_ regular expression to validate that the structure of an email is correct, the expression becomes so complex that it's incredibly difficult to debug or improve.</span></span> <span data-ttu-id="38f5b-111">Wyrażenia regularne nie mogą sprawdzić poprawności wiadomości e-mail, nawet jeśli struktura jest nieprawidłowa.</span><span class="sxs-lookup"><span data-stu-id="38f5b-111">Regular expressions can't validate an email exists, even if it's structured correctly.</span></span> <span data-ttu-id="38f5b-112">Najlepszym sposobem na zweryfikowanie wiadomości e-mail jest wysłanie testowej wiadomości e-mail na adres.</span><span class="sxs-lookup"><span data-stu-id="38f5b-112">The best way to validate an email is to send a test email to the address.</span></span>

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="38f5b-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="38f5b-113">Example</span></span>

<span data-ttu-id="38f5b-114">W przykładzie zdefiniowano `IsValidEmail` metodę, która zwraca wartość, `true` Jeśli ciąg zawiera prawidłowy adres e-mail `false` , a jeśli nie, ale nie przyjmuje żadnych innych akcji.</span><span class="sxs-lookup"><span data-stu-id="38f5b-114">The example defines an `IsValidEmail` method, which returns `true` if the string contains a valid email address and `false` if it doesn't, but takes no other action.</span></span>

<span data-ttu-id="38f5b-115">Aby sprawdzić, czy adres e-mail jest prawidłowy, `IsValidEmail` Metoda wywołuje <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> metodę ze `(@)(.+)$` wzorcem wyrażenia regularnego w celu oddzielenia nazwy domeny od adresu e-mail.</span><span class="sxs-lookup"><span data-stu-id="38f5b-115">To verify that the email address is valid, the `IsValidEmail` method calls the <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> method with the `(@)(.+)$` regular expression pattern to separate the domain name from the email address.</span></span> <span data-ttu-id="38f5b-116">Trzeci parametr jest <xref:System.Text.RegularExpressions.MatchEvaluator> delegatem, który reprezentuje metodę, która przetwarza i zastępuje dopasowany tekst.</span><span class="sxs-lookup"><span data-stu-id="38f5b-116">The third parameter is a <xref:System.Text.RegularExpressions.MatchEvaluator> delegate that represents the method that processes and replaces the matched text.</span></span> <span data-ttu-id="38f5b-117">Wzorzec wyrażenia regularnego jest interpretowany w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="38f5b-117">The regular expression pattern is interpreted as follows.</span></span>

| <span data-ttu-id="38f5b-118">Wzorce</span><span class="sxs-lookup"><span data-stu-id="38f5b-118">Pattern</span></span> | <span data-ttu-id="38f5b-119">Opis</span><span class="sxs-lookup"><span data-stu-id="38f5b-119">Description</span></span>                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | <span data-ttu-id="38f5b-120">Dopasowuje znak @.</span><span class="sxs-lookup"><span data-stu-id="38f5b-120">Match the @ character.</span></span> <span data-ttu-id="38f5b-121">Ta część jest pierwszą grupą przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="38f5b-121">This part is the first capturing group.</span></span>                           |
| `(.+)`  | <span data-ttu-id="38f5b-122">Dopasowuje jedno lub więcej wystąpień dowolnego znaku.</span><span class="sxs-lookup"><span data-stu-id="38f5b-122">Match one or more occurrences of any character.</span></span> <span data-ttu-id="38f5b-123">Ta część jest drugą grupą przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="38f5b-123">This part is the second capturing group.</span></span> |
| `$`     | <span data-ttu-id="38f5b-124">Zakończ dopasowanie na końcu ciągu.</span><span class="sxs-lookup"><span data-stu-id="38f5b-124">End the match at the end of the string.</span></span>                                             |

<span data-ttu-id="38f5b-125">Nazwa domeny wraz ze znakiem @ jest przenoszona do `DomainMapper` metody, która używa <xref:System.Globalization.IdnMapping> klasy do translacji znaków Unicode, które są spoza zakresu znaków US-ASCII do formacie Punycode.</span><span class="sxs-lookup"><span data-stu-id="38f5b-125">The domain name along with the @ character is passed to the `DomainMapper` method, which uses the <xref:System.Globalization.IdnMapping> class to translate Unicode characters that are outside the US-ASCII character range to Punycode.</span></span> <span data-ttu-id="38f5b-126">Metoda ustawia również `invalid` flagę na, `True` Jeśli <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> Metoda wykryje nieprawidłowe znaki w nazwie domeny.</span><span class="sxs-lookup"><span data-stu-id="38f5b-126">The method also sets the `invalid` flag to `True` if the <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> method detects any invalid characters in the domain name.</span></span> <span data-ttu-id="38f5b-127">Metoda zwraca nazwę domeny formacie Punycode poprzedzoną symbolem @ do `IsValidEmail` metody.</span><span class="sxs-lookup"><span data-stu-id="38f5b-127">The method returns the Punycode domain name preceded by the @ symbol to the `IsValidEmail` method.</span></span>

> [!TIP]
> <span data-ttu-id="38f5b-128">Zaleca się użycie prostego `(@)(.+)$` wzorca wyrażenia regularnego, aby znormalizować domenę, a następnie zwrócić wartość wskazującą, że została zakończona lub nie powiodła się.</span><span class="sxs-lookup"><span data-stu-id="38f5b-128">It's recommended that you use the simple `(@)(.+)$` regular expression pattern to normalize the domain and then return a value indicating that it passed or failed.</span></span> <span data-ttu-id="38f5b-129">Jednak w przykładzie w tym artykule opisano sposób dalszej weryfikacji wiadomości e-mail przy użyciu wyrażenia regularnego.</span><span class="sxs-lookup"><span data-stu-id="38f5b-129">However, the example in this article describes how to further use a regular expression to validate the email.</span></span> <span data-ttu-id="38f5b-130">Bez względu na to, jak sprawdzasz poprawność wiadomości e-mail, należy zawsze wysyłać testową wiadomość e-mail na adres, aby upewnić się, że istnieje.</span><span class="sxs-lookup"><span data-stu-id="38f5b-130">Regardless of how you validate an email, you should always send a test email to the address to make sure it exists.</span></span>

<span data-ttu-id="38f5b-131">`IsValidEmail`Metoda następnie wywołuje metodę, <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> Aby sprawdzić, czy adres jest zgodny ze wzorcem wyrażenia regularnego.</span><span class="sxs-lookup"><span data-stu-id="38f5b-131">The `IsValidEmail` method then calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> method to verify that the address conforms to a regular expression pattern.</span></span>

<span data-ttu-id="38f5b-132">`IsValidEmail`Metoda określa jedynie, czy format wiadomości e-mail jest prawidłowy dla adresu e-mail, a nie sprawdza poprawność wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="38f5b-132">The `IsValidEmail` method merely determines whether the email format is valid for an email address, it doesn't validate that the email exists.</span></span> <span data-ttu-id="38f5b-133">Ponadto `IsValidEmail` Metoda nie sprawdza, czy nazwa domeny najwyższego poziomu jest prawidłową nazwą domeny wymienioną w [bazie danych strefy głównej Iana](https://www.iana.org/domains/root/db), co wymagałoby operacji wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="38f5b-133">Also, the `IsValidEmail` method doesn't verify that the top-level domain name is a valid domain name listed at the [IANA Root Zone Database](https://www.iana.org/domains/root/db), which would require a look-up operation.</span></span>

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

<span data-ttu-id="38f5b-134">W tym przykładzie wzorzec wyrażenia regularnego `^[^@\s]+@[^@\s]+\.[^@\s]+$` jest interpretowany jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="38f5b-134">In this example, the regular expression pattern `^[^@\s]+@[^@\s]+\.[^@\s]+$` is interpreted as shown in the following table.</span></span> <span data-ttu-id="38f5b-135">Wyrażenie regularne jest kompilowane przy użyciu <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> flagi.</span><span class="sxs-lookup"><span data-stu-id="38f5b-135">The regular expression is compiled using the <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> flag.</span></span>

| <span data-ttu-id="38f5b-136">Wzorce</span><span class="sxs-lookup"><span data-stu-id="38f5b-136">Pattern</span></span>   | <span data-ttu-id="38f5b-137">Opis</span><span class="sxs-lookup"><span data-stu-id="38f5b-137">Description</span></span>                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | <span data-ttu-id="38f5b-138">Rozpocznij dopasowanie na początku ciągu.</span><span class="sxs-lookup"><span data-stu-id="38f5b-138">Begin the match at the start of the string.</span></span>                                              |
| `[^@\s]+` | <span data-ttu-id="38f5b-139">Dopasowuje jedno lub więcej wystąpień dowolnego znaku innego niż znak @ lub odstęp.</span><span class="sxs-lookup"><span data-stu-id="38f5b-139">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `@`       | <span data-ttu-id="38f5b-140">Dopasowuje znak @.</span><span class="sxs-lookup"><span data-stu-id="38f5b-140">Match the @ character.</span></span>                                                                   |
| `[^@\s]+` | <span data-ttu-id="38f5b-141">Dopasowuje jedno lub więcej wystąpień dowolnego znaku innego niż znak @ lub odstęp.</span><span class="sxs-lookup"><span data-stu-id="38f5b-141">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `\.`      | <span data-ttu-id="38f5b-142">Dopasowuje pojedynczy odstęp czasu.</span><span class="sxs-lookup"><span data-stu-id="38f5b-142">Match a single period character.</span></span>                                                         |
| `[^@\s]+` | <span data-ttu-id="38f5b-143">Dopasowuje jedno lub więcej wystąpień dowolnego znaku innego niż znak @ lub odstęp.</span><span class="sxs-lookup"><span data-stu-id="38f5b-143">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `$`       | <span data-ttu-id="38f5b-144">Zakończ dopasowanie na końcu ciągu.</span><span class="sxs-lookup"><span data-stu-id="38f5b-144">End the match at the end of the string.</span></span>                                                  |

> [!IMPORTANT]
> <span data-ttu-id="38f5b-145">To wyrażenie regularne nie obejmuje każdego aspektu prawidłowego adresu e-mail.</span><span class="sxs-lookup"><span data-stu-id="38f5b-145">This regular expression is not intended to cover every aspect of a valid email address.</span></span> <span data-ttu-id="38f5b-146">Jest on dostępny jako przykład do rozbudowania w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="38f5b-146">It's provided as an example for you to extend as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="38f5b-147">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="38f5b-147">See also</span></span>

- [<span data-ttu-id="38f5b-148">Wyrażenia regularne .NET</span><span class="sxs-lookup"><span data-stu-id="38f5b-148">.NET Regular Expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="38f5b-149">Jak daleko powinna zostać przesunięta Weryfikacja adresu e-mail?</span><span class="sxs-lookup"><span data-stu-id="38f5b-149">How far should one take e-mail address validation?</span></span>](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
