---
title: Usługi kryptograficzne
description: Omówienie metod i praktyk szyfrowania obsługiwanych przez platformę .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography [.NET]
- pattern of derived class inheritance
- digital signatures
- asymmetric cryptographic algorithms
- digital signatures, public-key systems
- public keys
- decryption [.NET]
- private keys
- MAC algorithms
- cryptographic algorithms
- private keys, overview
- encryption [.NET]
- security [.NET], encryption
- cryptographic services
- symmetric cryptographic algorithms
- hash
- message authentication codes
- derived class inheritance
- cryptography [.NET], about
- random number generation
ms.assetid: f96284bc-7b73-44b5-ac59-fac613ad09f8
ms.openlocfilehash: 463ccec5f60ff10331d501d39144a979d95eff95
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281723"
---
# <a name="cryptographic-services"></a>Usługi kryptograficzne

Sieci publiczne, takie jak Internet, nie zapewniają metody bezpiecznej komunikacji między jednostkami. Komunikacja za pośrednictwem takich sieci jest podatna na odczytywanie, a nawet modyfikowanie przez nieautoryzowane strony trzecie. Kryptografia pomaga chronić dane przed wyświetlaniem, zapewnia sposoby wykrywania, czy dane zostały zmodyfikowane i pomaga zapewnić bezpieczny sposób komunikacji za pośrednictwem niezabezpieczonych kanałów. Na przykład dane mogą być szyfrowane przy użyciu algorytmu kryptograficznego, przesyłane w stanie zaszyfrowanym i później odszyfrowane przez zaznaczoną stronę. Jeśli strona trzecia przechwytuje zaszyfrowane dane, będzie trudne do odszyfrowania.

W programie .NET klasy w <xref:System.Security.Cryptography> przestrzeni nazw zarządzają wieloma informacjami o kryptografii. Niektóre z nich są otokami dla implementacji systemu operacyjnego, a inne są całkowicie zarządzanymi implementacjami. Nie musisz być ekspertem w kryptografii, aby używać tych klas. Podczas tworzenia nowego wystąpienia jednej z klas algorytmu szyfrowania klucze są generowane automatycznie w celu ułatwienia użycia, a właściwości domyślne są bezpieczne i bezpieczne, jak to możliwe.

To omówienie zawiera streszczenie metod szyfrowania i praktyki obsługiwane przez platformę .NET, w tym manifestów ClickOnce.

## <a name="cryptographic-primitives"></a>Kryptograficzne elementy pierwotne

W typowej sytuacji, w której jest używana Kryptografia, dwie strony (Alicja i Robert) komunikują się za pośrednictwem niezabezpieczonego kanału. Alicja i Robert chcą zapewnić, że ich komunikacja jest niezrozumiała dla każdego, kto może nasłuchiwać. Ponadto, ponieważ Alicja i Robert znajdują się w lokalizacjach zdalnych, Alicja musi upewnić się, że informacje otrzymane z Roberta nie zostały zmodyfikowane przez żadną osobę podczas transmisji. Ponadto należy się upewnić, że informacje są naprawdę pochodzące od Roberta, a nie od osoby, która personifikuje Robert.

Kryptografia służy do osiągnięcia następujących celów:

- Poufność: aby chronić tożsamość lub dane użytkownika przed ich odczytaniem.

- Integralność danych: pomaga chronić dane przed ich zmianą.

- Uwierzytelnianie: aby upewnić się, że dane pochodzą od określonej strony.

- Brak odrzucania: aby uniemożliwić określonej stronie odmowę wysłania wiadomości.

Aby osiągnąć te cele, można użyć kombinacji algorytmów i praktyk znanych jako kryptograficzne elementy pierwotne w celu utworzenia schematu kryptograficznego. Poniższa tabela zawiera listę podstawowych elementów kryptograficznych i ich użycia.

|Kryptografia kryptograficzna|Zastosowanie|
|-----------------------------|---------|
|Szyfrowanie klucza tajnego (Kryptografia symetryczna)|Wykonuje transformację danych, aby uniemożliwić ich odczytywanie przez inne osoby. Ten typ szyfrowania używa jednego udostępnionego klucza tajnego do szyfrowania i odszyfrowywania danych.|
|Szyfrowanie klucza publicznego (kryptografia asymetryczna)|Wykonuje transformację danych, aby uniemożliwić ich odczytywanie przez inne osoby. Ten typ szyfrowania używa pary kluczy publiczny/prywatny do szyfrowania i odszyfrowywania danych.|
|Podpisywanie kryptograficzne|Pomaga sprawdzić, czy dane pochodzą od określonej strony przez utworzenie podpisu cyfrowego, który jest unikatowy dla tej strony. Ten proces używa również funkcji skrótu.|
|Skróty kryptograficzne|Mapuje dane z dowolnej długości na sekwencję bajtów o stałej długości. Skróty są statystycznie unikatowe; inna sekwencja dwubajtowa nie będzie mieszać wartości z tą samą wartością.|

## <a name="secret-key-encryption"></a>Szyfrowanie Secret-Key

Algorytmy szyfrowania klucza tajnego używają jednego klucza tajnego do szyfrowania i odszyfrowywania danych. Należy zabezpieczyć klucz przed dostępem nieautoryzowanych agentów, ponieważ każda Strona, która ma klucz, może użyć jej do odszyfrowania danych lub zaszyfrowania własnych danych, ponieważ pochodzi od użytkownika.

Szyfrowanie klucza tajnego jest również określane jako szyfrowanie symetryczne, ponieważ ten sam klucz jest używany do szyfrowania i odszyfrowywania. Algorytmy szyfrowania klucza tajnego są bardzo szybkie (w porównaniu z algorytmami klucza publicznego) i są dobrze dostosowane do wykonywania transformacji kryptograficznych w dużych strumieniach danych. Algorytmy szyfrowania asymetrycznego, takie jak RSA, są ograniczone matematycznie w zakresie ilości danych, które mogą być szyfrowane. Algorytmy szyfrowania symetrycznego zazwyczaj nie mają tych problemów.

Typ algorytmu tajnego klucza o nazwie szyfr bloku służy do szyfrowania jednego bloku danych w danym momencie. Zablokuj szyfry, takie jak Data Encryption Standard (DES), TripleDES i Advanced Encryption Standard (AES), Przekształć kryptograficznie Blok wejściowy *n* bajtów do bloku wyjściowego zaszyfrowanych bajtów. Aby zaszyfrować lub odszyfrować sekwencję bajtów, należy ją zablokować za pomocą bloku. Ponieważ *n* jest mały (8 bajtów dla des i TripleDES; 16 bajtów [domyślna], 24 bajty lub 32 bajtów dla AES), wartości danych, które są większe niż *n* , muszą być szyfrowane po jednym bloku naraz. Wartości danych, które są mniejsze niż *n* , muszą być rozwinięte do *n* , aby można było je przetworzyć.

Jedna prosta forma szyfrowania bloku jest nazywana trybem elektronicznym trybu (EBC). Tryb EBC nie jest uważany za Bezpieczny, ponieważ nie używa wektora inicjalizacji do inicjowania pierwszego bloku zwykłego tekstu. W przypadku danego klucza tajnego *k* , prosty szyfr bloku, który nie używa wektora inicjalizacji, będzie szyfrować ten sam blok danych wejściowych w tym samym bloku wyjściowym tekstu szyfrowanego. W związku z tym, jeśli masz zduplikowane bloki w strumieniu danych wejściowych w formacie zwykłego tekstu, będziesz mieć zduplikowane bloki w strumieniu danych wyjściowych. Te zduplikowane bloki wyjściowe wyzwalają alert nieautoryzowanych użytkowników do słabego szyfrowania wykorzystujących algorytmy, które mogły zostać zastosowane, oraz możliwe tryby ataków. W związku z tym jest bardzo narażony na analizę, a ostatecznie odnajdywanie kluczy.

Blokowe klasy szyfrowe, które są dostępne w bibliotece klas bazowych, używają domyślnego trybu łańcucha nazywanego łańcuchem blokowym (CBC), chociaż można zmienić to ustawienie domyślne, jeśli chcesz.

Szyfry CBC przezwyciężyją problemy związane z szyframi EBC przy użyciu wektora inicjującego (IV) do szyfrowania pierwszego bloku zwykłego tekstu. Każdy kolejny blok zwykłego tekstu nie przeprowadzi bitowej operacji wykluczającej lub ( `XOR` ) z poprzednim blokiem tekstu szyfrowanego przed zaszyfrowaniem. Każdy blok tekstu jest zależny od wszystkich poprzednich bloków. Gdy ten system jest używany, do odtworzenia klucza nie można użyć popularnych nagłówków komunikatów, które mogą być znane nieautoryzowanemu użytkownikowi.

Jednym ze sposobów na złamanie danych szyfrowanych za pomocą szyfru CBC jest wykonanie pełnego wyszukiwania każdego możliwego klucza. W zależności od rozmiaru klucza, który jest używany do szyfrowania, ten rodzaj wyszukiwania jest bardzo czasochłonny przy użyciu nawet najszybszych komputerów i dlatego jest nieosiągalny. Większe rozmiary kluczy są trudniejsze do odszyfrowania. Chociaż szyfrowanie nie sprawia, że jest teoretycznie niemożliwe do pobrania zaszyfrowanych danych przez atakującej, zwiększa to koszt. Jeśli przeprowadzenie szczegółowego wyszukiwania w celu pobrania danych, które ma znaczenie tylko przez kilka dni, trwa przez trzy miesiące, pełna Metoda wyszukiwania jest nieprzydatna.

Wadą szyfrowania klucza tajnego jest założenie, że dwie strony zgodziły się na klucz i IV i komunikują się ich wartości. IV nie jest traktowany jako wpis tajny i może być przesyłany w postaci zwykłego tekstu z wiadomością. Klucz musi być jednak tajny dla nieautoryzowanych użytkowników. Ze względu na te problemy szyfrowanie klucza tajnego jest często używane razem z szyfrowaniem klucza publicznego do prywatnego przekazywania wartości klucza i IV.

Przy założeniu, że Alicja i Robert są dwiema stronami, którzy chcą komunikować się za pośrednictwem niezabezpieczonego kanału, mogą używać szyfrowania klucza tajnego w następujący sposób: Alicja i Robert zgadzają się używać jednego określonego algorytmu (na przykład AES) z określonym kluczem i IV. Alicja redaguje komunikat i utworzy strumień sieciowy (być może nazwany potok lub sieć e-mail), na którym ma być wysyłany komunikat. Następnie szyfruje tekst przy użyciu klucza i IV, a następnie przesyła zaszyfrowaną wiadomość i IV do Roberta za pośrednictwem intranetu. Robert odbiera zaszyfrowany tekst i odszyfrowuje go przy użyciu IV i wcześniej uzgodnionych kluczy. Jeśli transmisja zostanie przechwycona, Interceptor nie będzie mógł odzyskać oryginalnego komunikatu, ponieważ nie zna klucza. W tym scenariuszu tylko klucz musi pozostać tajny. W świecie rzeczywistym, Alicja lub Robert generuje klucz tajny i używa szyfrowania klucza publicznego (asymetrycznego) do transferowania klucza tajnego (symetrycznego) do drugiej strony. Aby uzyskać więcej informacji na temat szyfrowania kluczem publicznym, zobacz następną sekcję.

Platforma .NET udostępnia następujące klasy, które implementują algorytmy szyfrowania klucza tajnego:

- <xref:System.Security.Cryptography.Aes>

- <xref:System.Security.Cryptography.HMACSHA256><xref:System.Security.Cryptography.HMACSHA384>i <xref:System.Security.Cryptography.HMACSHA512> . (Są to techniczne algorytmy tajne klucza, ponieważ reprezentują kody uwierzytelniania wiadomości, które są obliczane przy użyciu funkcji skrótu kryptograficznego połączonej z kluczem tajnym. Zobacz [wartości skrótu](#hash-values)w dalszej części tego artykułu.)

## <a name="public-key-encryption"></a>Szyfrowanie Public-Key

Szyfrowanie klucza publicznego używa klucza prywatnego, który musi być tajny przez nieautoryzowanych użytkowników i klucz publiczny, który można udostępnić każdemu użytkownikowi. Klucz publiczny i klucz prywatny są powiązane matematycznie; dane zaszyfrowane za pomocą klucza publicznego mogą zostać odszyfrowane tylko przy użyciu klucza prywatnego, a dane podpisane przy użyciu klucza prywatnego mogą być weryfikowane tylko z kluczem publicznym. Klucz publiczny można udostępnić każdemu użytkownikowi; służy do szyfrowania danych wysyłanych do posiadacza klucza prywatnego. Algorytmy kryptograficzne klucza publicznego są również znane jako algorytmy asymetryczne, ponieważ jeden klucz jest wymagany do szyfrowania danych, a do odszyfrowania danych jest wymagany inny klucz. Podstawowa reguła kryptograficzna uniemożliwia ponowne użycie klucza, a oba klucze powinny być unikatowe dla każdej sesji komunikacji. Jednak w przypadku klucze asymetryczne są zwykle długotrwałe.

Dwie strony (Alicja i Robert) mogą używać szyfrowania klucza publicznego w następujący sposób: najpierw Alicja generuje parę kluczy publiczny/prywatny. Jeśli Robert chce wysłać zaszyfrowaną wiadomość, zażąda jej klucza publicznego. Alicja wysyła swój klucz publiczny za pośrednictwem niezabezpieczonej sieci, a Robert używa tego klucza do szyfrowania wiadomości. Robert wysyła zaszyfrowany komunikat do programu Alicja i odszyfrowuje go przy użyciu jego klucza prywatnego. Jeśli Robert otrzyma klucz Alicja za pośrednictwem niezabezpieczonego kanału, takiego jak sieć publiczna, Robert jest otwarty na ataki typu man-in-the-middle. W związku z tym Robert musi zweryfikować za pomocą Alicja, że ma poprawną kopię swojego klucza publicznego.

Podczas przesyłania klucza publicznego Alicja nieautoryzowany agent może przechwycić klucz. Ponadto ten sam Agent może przechwycić zaszyfrowany komunikat z Roberta. Jednak Agent nie może odszyfrować komunikatu przy użyciu klucza publicznego. Wiadomość można odszyfrować tylko za pomocą klucza prywatnego Alicja, który nie został przesłany. Alicja nie używa swojego klucza prywatnego do szyfrowania komunikatu odpowiedzi do Roberta, ponieważ każda osoba z kluczem publicznym może odszyfrować komunikat. Jeśli Alicja chce wysłać komunikat z powrotem do Roberta, prosi Roberta o jego klucz publiczny i szyfruje jego komunikat przy użyciu tego klucza publicznego. Robert następnie odszyfrowuje komunikat przy użyciu skojarzonego z nim klucza prywatnego.

W tym scenariuszu Alicja i Robert używają szyfrowania klucza publicznego (asymetrycznego) do transferowania klucza tajnego (symetrycznego) i korzystania z szyfrowania klucza tajnego w pozostałej części sesji.

Poniższa lista zawiera porównania między algorytmami kryptograficznymi klucza publicznego i klucza tajnego:

- Algorytmy kryptograficzne klucza publicznego używają stałego rozmiaru buforu, natomiast algorytmy kryptograficzne klucza tajnego używają bufora o zmiennej długości.

- Algorytmy klucza publicznego nie mogą być używane do łączenia danych ze strumieniami, tak jak algorytmy klucza tajnego, ponieważ mogą być szyfrowane tylko małe ilości danych. W związku z tym operacje asymetryczne nie używają tego samego modelu przesyłania strumieniowego jako operacji symetrycznych.

- Szyfrowanie klucza publicznego ma znacznie większe miejsce na klucz (zakres możliwych wartości klucza) niż szyfrowanie klucza tajnego. W związku z tym szyfrowanie klucza publicznego jest mniej podatne na pełne ataki, które Wypróbuj każdy możliwy klucz.

- Klucze publiczne są łatwe do dystrybucji, ponieważ nie muszą być zabezpieczone, pod warunkiem, że istnieje możliwość zweryfikowania tożsamości nadawcy.

- Niektóre algorytmy klucza publicznego (takie jak RSA i DSA, ale nie Diffie-Hellmana) mogą służyć do tworzenia podpisów cyfrowych w celu zweryfikowania tożsamości nadawcy danych.

- Algorytmy klucza publicznego są bardzo wolne w porównaniu z algorytmami tajnych kluczy i nie są przeznaczone do szyfrowania dużych ilości danych. Algorytmy klucza publicznego są przydatne tylko do przesyłania bardzo małych ilości danych. Zazwyczaj szyfrowanie klucza publicznego służy do szyfrowania klucza i IV, który ma być używany przez algorytm tajnego klucza. Po przeniesieniu klucza i IV, szyfrowanie klucza tajnego jest używane w pozostałej części sesji.

Platforma .NET udostępnia następujące klasy, które implementują algorytmy klucza publicznego:

- <xref:System.Security.Cryptography.RSA>

- <xref:System.Security.Cryptography.ECDsa>

- <xref:System.Security.Cryptography.ECDiffieHellman>

- <xref:System.Security.Cryptography.DSA>

Klucz RSA umożliwia szyfrowanie i podpisywanie, ale agenta DSA można używać tylko do podpisywania. Agent DSA nie jest zgodny z algorytmem RSA i zalecamy użycie algorytmu RSA. Diffie-Hellman można używać tylko na potrzeby generowania kluczy. Ogólnie rzecz biorąc, algorytmy klucza publicznego są bardziej ograniczone w porównaniu z algorytmami klucza prywatnego.

## <a name="digital-signatures"></a>Podpisy cyfrowe

Algorytmy klucza publicznego mogą również służyć do tworzenia podpisów cyfrowych. Podpisy cyfrowe uwierzytelniają tożsamość nadawcy (w przypadku zaufania klucza publicznego nadawcy) i pomagają chronić integralność danych. Przy użyciu klucza publicznego wygenerowanego przez Alicja, odbiorca danych Alicja może sprawdzić, czy Alicja je wysłała, porównując podpis cyfrowy z danymi i kluczem publicznym Alicja.

Aby użyć kryptografii klucza publicznego do cyfrowego podpisywania wiadomości, Alicja najpierw stosuje algorytm wyznaczania wartości skrótu do wiadomości, aby utworzyć skrót wiadomości. Skrót wiadomości jest zwartą i unikatową reprezentacją danych. Alicja szyfruje następnie skrót wiadomości przy użyciu klucza prywatnego w celu utworzenia podpisu osobistego. Po odebraniu wiadomości i sygnatury Robert odszyfrowuje podpis przy użyciu klucza publicznego Alicja, aby odzyskać skrót wiadomości i skrócić komunikat przy użyciu tego samego algorytmu wyznaczania wartości skrótu używanego przez Alicja. Jeśli skrót wiadomości, który jest obliczany przez Robert, dokładnie pasuje do skrótu wiadomości otrzymanego od Alicja, Robert ma pewność, że wiadomość pochodzi od posiadacza klucza prywatnego i że dane nie zostały zmodyfikowane. Jeśli Robert ufa, że Alicja jest posiadaczem klucza prywatnego, wie, że wiadomość pochodzi od Alicja.

> [!NOTE]
> Podpis może być zweryfikowany przez każdego użytkownika, ponieważ klucz publiczny nadawcy jest powszechną wiedzą i zazwyczaj jest uwzględniany w formacie podpisu cyfrowego. Ta metoda nie zachowuje tajemnicy wiadomości; Aby komunikat był tajny, musi również być zaszyfrowany.

Platforma .NET udostępnia następujące klasy, które implementują algorytmy podpisu cyfrowego:

- <xref:System.Security.Cryptography.RSA>

- <xref:System.Security.Cryptography.ECDsa>

- <xref:System.Security.Cryptography.DSA>

## <a name="hash-values"></a>Wartości skrótu

Algorytmy skrótu mapują wartości binarne dowolnej długości na mniejsze wartości binarne o stałej długości, znane jako wartości skrótu. Wartość skrótu jest cyfrową reprezentacją fragmentu danych. Jeśli Mieszasz akapit w postaci zwykłego tekstu i zmienisz nawet jedną literę akapitu, kolejny skrót będzie generował inną wartość. Jeśli skrót jest silnie silny, jego wartość zmieni się w istotny sposób. Na przykład jeśli zostanie zmieniony pojedynczy bit komunikatu, funkcja silnego skrótu może generować dane wyjściowe, które różnią się o 50 procent. Wiele wartości wejściowych może być zmieszanych z tą samą wartością wyjściową. Nie jest jednak możliwe obliczenie dwóch odrębnych wejść, które mieszają się z tą samą wartością.

Dwie strony (Alicja i Robert) mogą używać funkcji skrótu, aby zapewnić integralność komunikatów. Spowodują wybranie algorytmu wyznaczania wartości skrótu w celu podpisania swoich komunikatów. Alicja zapisze komunikat, a następnie utworzy skrót tego komunikatu przy użyciu wybranego algorytmu. Następnie zastosują jedną z następujących metod:

- Alicja wysyła wiadomość w postaci zwykłego tekstu oraz komunikat z mieszaniem (podpis cyfrowy) do Roberta. Robert odbiera i miesza komunikat i porównuje jego wartość skrótu z wartością skrótu uzyskaną od Alicja. Jeśli wartości skrótu są identyczne, komunikat nie został zmieniony. Jeśli wartości nie są identyczne, komunikat został zmieniony po jego zapisaniu przez Alicja.

  Niestety, ta metoda nie ustala autentyczności nadawcy. Każdy może personifikować Alicja i wysłać wiadomość do Roberta. Mogą używać tego samego algorytmu wyznaczania wartości skrótu do podpisywania wiadomości, a cała Robert może określić, że wiadomość pasuje do podpisu. Jest to jedna z form ataku typu man-in-the-middle. Aby uzyskać więcej informacji, zobacz [przykład bezpiecznej komunikacji Secure Generation (CNG)](/previous-versions/cc488018(v=vs.100)).

- Alicja wysyła wiadomość w postaci zwykłego tekstu do Roberta za pośrednictwem niezabezpieczonego kanału publicznego. Wysyła komunikat z mieszaniem do Roberta za pośrednictwem bezpiecznego kanału prywatnego. Robert odbiera komunikat w postaci zwykłego tekstu, miesza go i porównuje skrót z wymieniem prywatnym. Jeśli skróty są zgodne, Robert wie dwie rzeczy:

  - Komunikat nie został zmieniony.

  - Nadawca wiadomości (Alicja) jest autentyczny.

  Aby ten system działał, Alicja musi ukryć oryginalną wartość skrótu ze wszystkich stron oprócz Roberta.

- Alicja wysyła wiadomość w postaci zwykłego tekstu do Roberta za pośrednictwem niezabezpieczonego kanału publicznego i umieszcza komunikat o skrócie w swojej publicznej witrynie sieci Web.

  Ta metoda zapobiega manipulowaniu komunikatów przez uniemożliwianie innym użytkownikom modyfikowania wartości skrótu. Chociaż komunikat i jego wartość skrótu mogą być odczytywane przez każdego użytkownika, wartość skrótu można zmienić tylko przez Alicja. Osoba atakująca, która chce personifikować Alicja, będzie wymagać dostępu do witryny sieci Web Alicja.

Żadna z powyższych metod nie uniemożliwi osobie odczytywania wiadomości Alicja, ponieważ są one przesyłane w postaci zwykłego tekstu. Pełne zabezpieczenia zwykle wymagają podpisów cyfrowych (podpisywanie wiadomości) i szyfrowania.

Platforma .NET udostępnia następujące klasy, które implementują algorytmy wyznaczania wartości skrótu:

- <xref:System.Security.Cryptography.SHA256>.

- <xref:System.Security.Cryptography.SHA384>.

- <xref:System.Security.Cryptography.SHA512>.

Platforma .NET udostępnia również <xref:System.Security.Cryptography.MD5> i <xref:System.Security.Cryptography.SHA1> . Ale algorytmy MD5 i SHA-1 zostały uznane za niezabezpieczone, a w zamian zaleca się stosowanie algorytmu SHA-2. Algorytm SHA-2 zawiera SHA256, SHA384 i SHA512.

## <a name="random-number-generation"></a>Generowanie liczb losowych

Generowanie liczb losowych jest integralną częścią wielu operacji kryptograficznych. Na przykład klucze kryptograficzne muszą być tak losowo, jak to możliwe, aby było niemożliwe do odtworzenia. Kryptograficzne generatory liczb losowych muszą generować dane wyjściowe, które nie są obliczeniowe do przewidywania z prawdopodobieństwem, który jest lepszy niż jedna połowa. W związku z tym jakakolwiek metoda przewidywania następnego bitu wyjściowego nie może być większa niż losowe zgadywanie. Klasy w środowisku .NET używają losowych generatorów liczbowych do generowania kluczy kryptograficznych.

<xref:System.Security.Cryptography.RandomNumberGenerator>Klasa jest implementacją algorytmu generatora liczb losowych.

## <a name="clickonce-manifests"></a>Manifesty ClickOnce

Poniższe klasy kryptograficzne umożliwiają uzyskanie i zweryfikowanie informacji o sygnaturach manifestu dla aplikacji, które są wdrażane przy użyciu [technologii ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment):

- <xref:System.Security.Cryptography.ManifestSignatureInformation>Klasa uzyskuje informacje o sygnaturze manifestu w przypadku użycia <xref:System.Security.Cryptography.ManifestSignatureInformation.VerifySignature%2A> przeciążeń metody.

- Można użyć wyliczenia, <xref:System.Security.ManifestKinds> Aby określić, które manifesty należy zweryfikować. Wynik weryfikacji jest jedną z <xref:System.Security.Cryptography.SignatureVerificationResult> wartości wyliczenia.

- <xref:System.Security.Cryptography.ManifestSignatureInformationCollection>Klasa zawiera kolekcję <xref:System.Security.Cryptography.ManifestSignatureInformation> obiektów z zweryfikowanymi sygnaturami tylko do odczytu.

Ponadto następujące klasy zawierają określone informacje o podpisie:

- <xref:System.Security.Cryptography.StrongNameSignatureInformation> przechowuje informacje o sygnaturze silnej nazwy dla manifestu.

- <xref:System.Security.Cryptography.X509Certificates.AuthenticodeSignatureInformation> reprezentuje informacje o podpisie Authenticode dla manifestu.

- <xref:System.Security.Cryptography.X509Certificates.TimestampInformation> zawiera informacje o sygnaturze czasowej w podpisie Authenticode.

- <xref:System.Security.Cryptography.X509Certificates.TrustStatus> zapewnia prosty sposób sprawdzenia, czy podpis Authenticode jest zaufany.

## <a name="cryptography-next-generation-cng-classes"></a>Klasy kryptografii nowej generacji (CNG)

Klasy kryptografii nowej generacji (CNG) zapewniają zarządzaną otokę wokół natywnych funkcji CNG. (CNG jest zamiennikiem interfejsu CryptoAPI). Klasy te mają "CNG" jako część swoich nazw. Centralnie do klas otoki CNG jest <xref:System.Security.Cryptography.CngKey> klasą kontenerów kluczy, która stanowi abstrakcyjny magazyn i użycie kluczy CNG. Ta klasa umożliwia bezpieczne przechowywanie pary kluczy lub klucza publicznego i odwoływanie się do niego przy użyciu prostej nazwy ciągu. Klasa podpisu oparta na krzywej eliptycznej <xref:System.Security.Cryptography.ECDsaCng> i <xref:System.Security.Cryptography.ECDiffieHellmanCng> klasie szyfrowania mogą używać <xref:System.Security.Cryptography.CngKey> obiektów.

<xref:System.Security.Cryptography.CngKey>Klasa jest używana dla różnych dodatkowych operacji, w tym otwierania, tworzenia, usuwania i eksportowania kluczy. Zapewnia również dostęp do uchwytu klucza bazowego, który ma być używany podczas bezpośredniego wywoływania funkcji natywnych.

Platforma .NET zawiera również różne klasy obsługi CNG, takie jak:

- <xref:System.Security.Cryptography.CngProvider> obsługuje dostawcę magazynu kluczy.

- <xref:System.Security.Cryptography.CngAlgorithm> utrzymuje algorytm CNG.

- <xref:System.Security.Cryptography.CngProperty> zachowuje często używane właściwości klucza.

## <a name="see-also"></a>Zobacz także

- [Model kryptografii](cryptography-model.md) — opis sposobu implementacji kryptografii w bibliotece klas bazowych.
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- [Luki w zabezpieczeniach chronometrażu z odszyfrowywaniem symetrycznym w trybie CBC przy użyciu uzupełnienia](vulnerabilities-cbc-mode.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
