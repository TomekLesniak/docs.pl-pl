---
title: 'Przewodnik: Tworzenie aplikacji kryptograficznej'
description: Zapoznaj się z tworzeniem aplikacji kryptograficznej. Dowiedz się, jak szyfrować i odszyfrowywać zawartość w aplikacji Windows Forms.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET], example
- cryptography [NET], cryptographic application example
- cryptography [NET], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 70218d60abb336cdb35fc2e89e62a50b6bd79c67
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830561"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="5c07f-104">Przewodnik: Tworzenie aplikacji kryptograficznej</span><span class="sxs-lookup"><span data-stu-id="5c07f-104">Walkthrough: Creating a Cryptographic Application</span></span>

> [!NOTE]
> <span data-ttu-id="5c07f-105">Ten artykuł dotyczy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="5c07f-105">This article applies to Windows.</span></span>
>
> <span data-ttu-id="5c07f-106">Aby uzyskać informacje na temat ASP.NET Core, zobacz [ASP.NET Core ochrony danych](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="5c07f-106">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="5c07f-107">W tym instruktażu pokazano, jak szyfrować i odszyfrowywać zawartość.</span><span class="sxs-lookup"><span data-stu-id="5c07f-107">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="5c07f-108">Przykłady kodu są przeznaczone dla aplikacji Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5c07f-108">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="5c07f-109">Ta aplikacja nie pokazuje rzeczywistych scenariuszy, takich jak korzystanie z kart inteligentnych.</span><span class="sxs-lookup"><span data-stu-id="5c07f-109">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="5c07f-110">Zamiast tego pokazuje podstawowe informacje dotyczące szyfrowania i odszyfrowywania.</span><span class="sxs-lookup"><span data-stu-id="5c07f-110">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
<span data-ttu-id="5c07f-111">W tym instruktażu zastosowano następujące wytyczne dotyczące szyfrowania:</span><span class="sxs-lookup"><span data-stu-id="5c07f-111">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="5c07f-112">Użyj <xref:System.Security.Cryptography.Aes> klasy, algorytmu symetrycznego, aby szyfrować i odszyfrowywać dane przy użyciu automatycznie wygenerowanego <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> i <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A> .</span><span class="sxs-lookup"><span data-stu-id="5c07f-112">Use the <xref:System.Security.Cryptography.Aes> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="5c07f-113">Użyj <xref:System.Security.Cryptography.RSA> algorytmu asymetrycznego do szyfrowania i odszyfrowywania klucza do danych szyfrowanych przez program <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="5c07f-113">Use the <xref:System.Security.Cryptography.RSA> asymmetric algorithm to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.Aes>.</span></span> <span data-ttu-id="5c07f-114">Algorytmy asymetryczne najlepiej używać w przypadku mniejszych ilości danych, takich jak klucz.</span><span class="sxs-lookup"><span data-stu-id="5c07f-114">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5c07f-115">Jeśli chcesz chronić dane na komputerze zamiast wymieniać zaszyfrowaną zawartość z innymi osobami, rozważ użycie <xref:System.Security.Cryptography.ProtectedData> klasy.</span><span class="sxs-lookup"><span data-stu-id="5c07f-115">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> class.</span></span>  
  
 <span data-ttu-id="5c07f-116">Poniższa tabela zawiera podsumowanie zadań kryptograficznych w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="5c07f-116">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="5c07f-117">Zadanie</span><span class="sxs-lookup"><span data-stu-id="5c07f-117">Task</span></span>|<span data-ttu-id="5c07f-118">Opis</span><span class="sxs-lookup"><span data-stu-id="5c07f-118">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5c07f-119">Tworzenie aplikacji Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c07f-119">Creating a Windows Forms application</span></span>|<span data-ttu-id="5c07f-120">Wyświetla listę kontrolek, które są wymagane do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5c07f-120">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="5c07f-121">Deklarowanie obiektów globalnych</span><span class="sxs-lookup"><span data-stu-id="5c07f-121">Declaring global objects</span></span>|<span data-ttu-id="5c07f-122">Deklaruje zmienne ścieżki ciągów, <xref:System.Security.Cryptography.CspParameters> i i ma <xref:System.Security.Cryptography.RSACryptoServiceProvider> kontekst globalny <xref:System.Windows.Forms.Form> klasy.</span><span class="sxs-lookup"><span data-stu-id="5c07f-122">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="5c07f-123">Tworzenie klucza asymetrycznego</span><span class="sxs-lookup"><span data-stu-id="5c07f-123">Creating an asymmetric key</span></span>|<span data-ttu-id="5c07f-124">Tworzy asymetryczną parę wartości klucza publicznego i prywatnego i przypisuje mu nazwę kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="5c07f-124">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="5c07f-125">Szyfrowanie pliku</span><span class="sxs-lookup"><span data-stu-id="5c07f-125">Encrypting a file</span></span>|<span data-ttu-id="5c07f-126">Wyświetla okno dialogowe, w którym można wybrać plik do szyfrowania i szyfruje plik.</span><span class="sxs-lookup"><span data-stu-id="5c07f-126">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="5c07f-127">Odszyfrowywanie pliku</span><span class="sxs-lookup"><span data-stu-id="5c07f-127">Decrypting a file</span></span>|<span data-ttu-id="5c07f-128">Wyświetla okno dialogowe, w którym można wybrać zaszyfrowany plik do odszyfrowania i odszyfrować plik.</span><span class="sxs-lookup"><span data-stu-id="5c07f-128">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="5c07f-129">Pobieranie klucza prywatnego</span><span class="sxs-lookup"><span data-stu-id="5c07f-129">Getting a private key</span></span>|<span data-ttu-id="5c07f-130">Pobiera pełną parę kluczy przy użyciu nazwy kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="5c07f-130">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="5c07f-131">Eksportowanie klucza publicznego</span><span class="sxs-lookup"><span data-stu-id="5c07f-131">Exporting a public key</span></span>|<span data-ttu-id="5c07f-132">Zapisuje klucz do pliku XML tylko z parametrami publicznymi.</span><span class="sxs-lookup"><span data-stu-id="5c07f-132">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="5c07f-133">Importowanie klucza publicznego</span><span class="sxs-lookup"><span data-stu-id="5c07f-133">Importing a public key</span></span>|<span data-ttu-id="5c07f-134">Ładuje klucz z pliku XML do kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="5c07f-134">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="5c07f-135">Testowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="5c07f-135">Testing the application</span></span>|<span data-ttu-id="5c07f-136">Wyświetla listę procedur testowania tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5c07f-136">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="5c07f-137">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="5c07f-137">Prerequisites</span></span>  

<span data-ttu-id="5c07f-138">Następujące składniki są wymagane do przeprowadzenia tego instruktażu:</span><span class="sxs-lookup"><span data-stu-id="5c07f-138">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="5c07f-139">Odwołania do <xref:System.IO> <xref:System.Security.Cryptography> przestrzeni nazw i.</span><span class="sxs-lookup"><span data-stu-id="5c07f-139">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="5c07f-140">Tworzenie aplikacji Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c07f-140">Creating a Windows Forms Application</span></span>  

<span data-ttu-id="5c07f-141">Większość przykładów kodu w tym instruktażu została zaprojektowana jako programy obsługi zdarzeń dla kontrolek Button.</span><span class="sxs-lookup"><span data-stu-id="5c07f-141">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="5c07f-142">Poniższa tabela zawiera listę formantów wymaganych dla przykładowej aplikacji i ich wymaganych nazw w celu dopasowania do przykładów kodu.</span><span class="sxs-lookup"><span data-stu-id="5c07f-142">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="5c07f-143">Kontrola</span><span class="sxs-lookup"><span data-stu-id="5c07f-143">Control</span></span>|<span data-ttu-id="5c07f-144">Nazwa</span><span class="sxs-lookup"><span data-stu-id="5c07f-144">Name</span></span>|<span data-ttu-id="5c07f-145">Właściwość Text (zgodnie z wymaganiami)</span><span class="sxs-lookup"><span data-stu-id="5c07f-145">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="5c07f-146">Szyfruj plik</span><span class="sxs-lookup"><span data-stu-id="5c07f-146">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="5c07f-147">Odszyfruj plik</span><span class="sxs-lookup"><span data-stu-id="5c07f-147">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="5c07f-148">Utwórz klucze</span><span class="sxs-lookup"><span data-stu-id="5c07f-148">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="5c07f-149">Eksportuj klucz publiczny</span><span class="sxs-lookup"><span data-stu-id="5c07f-149">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="5c07f-150">Importuj klucz publiczny</span><span class="sxs-lookup"><span data-stu-id="5c07f-150">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="5c07f-151">Pobierz klucz prywatny</span><span class="sxs-lookup"><span data-stu-id="5c07f-151">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="5c07f-152">Nie ustawiono klucza</span><span class="sxs-lookup"><span data-stu-id="5c07f-152">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="5c07f-153">Kliknij dwukrotnie przyciski w projektancie programu Visual Studio, aby utworzyć obsługę zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="5c07f-153">Double-click the buttons in the Visual Studio designer to create their event handlers.</span></span>
  
## <a name="declaring-global-objects"></a><span data-ttu-id="5c07f-154">Deklarowanie obiektów globalnych</span><span class="sxs-lookup"><span data-stu-id="5c07f-154">Declaring Global Objects</span></span>  

<span data-ttu-id="5c07f-155">Dodaj następujący kod do konstruktora formularza.</span><span class="sxs-lookup"><span data-stu-id="5c07f-155">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="5c07f-156">Edytuj zmienne ciągów dla środowiska i preferencji.</span><span class="sxs-lookup"><span data-stu-id="5c07f-156">Edit the string variables for your environment and preferences.</span></span>  
  
[!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
[!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="5c07f-157">Tworzenie klucza asymetrycznego</span><span class="sxs-lookup"><span data-stu-id="5c07f-157">Creating an Asymmetric Key</span></span>  

<span data-ttu-id="5c07f-158">To zadanie tworzy klucz asymetryczny, który szyfruje i odszyfrowuje <xref:System.Security.Cryptography.Aes> klucz.</span><span class="sxs-lookup"><span data-stu-id="5c07f-158">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.Aes> key.</span></span> <span data-ttu-id="5c07f-159">Ten klucz został użyty do zaszyfrowania zawartości i wyświetla nazwę kontenera kluczy w kontrolce etykieta.</span><span class="sxs-lookup"><span data-stu-id="5c07f-159">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="5c07f-160">Dodaj następujący kod jako `Click` procedurę obsługi zdarzeń dla `Create Keys` przycisku ( `buttonCreateAsmKeys_Click` ).</span><span class="sxs-lookup"><span data-stu-id="5c07f-160">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="5c07f-161">Szyfrowanie pliku</span><span class="sxs-lookup"><span data-stu-id="5c07f-161">Encrypting a File</span></span>  

<span data-ttu-id="5c07f-162">To zadanie obejmuje dwie metody: metoda obsługi zdarzeń dla `Encrypt File` przycisku ( `buttonEncryptFile_Click` ) i `EncryptFile` metody.</span><span class="sxs-lookup"><span data-stu-id="5c07f-162">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="5c07f-163">Pierwsza metoda wyświetla okno dialogowe, w którym można wybrać plik i przekazuje nazwę pliku do drugiej metody, która wykonuje szyfrowanie.</span><span class="sxs-lookup"><span data-stu-id="5c07f-163">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
<span data-ttu-id="5c07f-164">Zaszyfrowana zawartość, klucz i IV są zapisywane na jednym <xref:System.IO.FileStream> , który jest nazywany Pakietem szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="5c07f-164">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
<span data-ttu-id="5c07f-165">`EncryptFile`Metoda wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="5c07f-165">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="5c07f-166">Tworzy <xref:System.Security.Cryptography.Aes> algorytm symetryczny do szyfrowania zawartości.</span><span class="sxs-lookup"><span data-stu-id="5c07f-166">Creates a <xref:System.Security.Cryptography.Aes> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="5c07f-167">Tworzy obiekt służący <xref:System.Security.Cryptography.RSACryptoServiceProvider> do szyfrowania <xref:System.Security.Cryptography.Aes> klucza.</span><span class="sxs-lookup"><span data-stu-id="5c07f-167">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
3. <span data-ttu-id="5c07f-168">Używa <xref:System.Security.Cryptography.CryptoStream> obiektu do odczytu i szyfrowania <xref:System.IO.FileStream> pliku źródłowego w blokach bajtów do <xref:System.IO.FileStream> obiektu docelowego dla zaszyfrowanego pliku.</span><span class="sxs-lookup"><span data-stu-id="5c07f-168">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="5c07f-169">Określa długość zaszyfrowanego klucza i IV i tworzy tablicę bajtową wartości ich długości.</span><span class="sxs-lookup"><span data-stu-id="5c07f-169">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="5c07f-170">Zapisuje wartości key, IV i ich długości do zaszyfrowanego pakietu.</span><span class="sxs-lookup"><span data-stu-id="5c07f-170">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="5c07f-171">Pakiet szyfrowania używa następującego formatu:</span><span class="sxs-lookup"><span data-stu-id="5c07f-171">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="5c07f-172">Długość klucza, bajty 0-3</span><span class="sxs-lookup"><span data-stu-id="5c07f-172">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="5c07f-173">Długość IV, bajtów 4-7</span><span class="sxs-lookup"><span data-stu-id="5c07f-173">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="5c07f-174">Zaszyfrowany klucz</span><span class="sxs-lookup"><span data-stu-id="5c07f-174">Encrypted key</span></span>  
  
- <span data-ttu-id="5c07f-175">V</span><span class="sxs-lookup"><span data-stu-id="5c07f-175">IV</span></span>  
  
- <span data-ttu-id="5c07f-176">Szyfrowanie tekstu</span><span class="sxs-lookup"><span data-stu-id="5c07f-176">Cipher text</span></span>  
  
 <span data-ttu-id="5c07f-177">Możesz użyć długości klucza i IV, aby określić punkty początkowe i długości wszystkich części pakietu szyfrującego, które mogą być następnie użyte do odszyfrowania pliku.</span><span class="sxs-lookup"><span data-stu-id="5c07f-177">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="5c07f-178">Dodaj następujący kod jako `Click` procedurę obsługi zdarzeń dla `Encrypt File` przycisku ( `buttonEncryptFile_Click` ).</span><span class="sxs-lookup"><span data-stu-id="5c07f-178">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="5c07f-179">Dodaj następującą `EncryptFile` metodę do formularza.</span><span class="sxs-lookup"><span data-stu-id="5c07f-179">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="5c07f-180">Odszyfrowywanie pliku</span><span class="sxs-lookup"><span data-stu-id="5c07f-180">Decrypting a File</span></span>  

<span data-ttu-id="5c07f-181">To zadanie obejmuje dwie metody, metodę obsługi zdarzeń dla `Decrypt File` przycisku ( `buttonDecryptFile_Click` ) i `DecryptFile` metodę.</span><span class="sxs-lookup"><span data-stu-id="5c07f-181">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="5c07f-182">Pierwsza metoda wyświetla okno dialogowe, w którym można wybrać plik i przekazuje jego nazwę pliku do drugiej metody, która wykonuje odszyfrowywanie.</span><span class="sxs-lookup"><span data-stu-id="5c07f-182">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
<span data-ttu-id="5c07f-183">`Decrypt`Metoda wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="5c07f-183">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="5c07f-184">Tworzy <xref:System.Security.Cryptography.Aes> algorytm symetryczny do odszyfrowywania zawartości.</span><span class="sxs-lookup"><span data-stu-id="5c07f-184">Creates an <xref:System.Security.Cryptography.Aes> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="5c07f-185">Odczytuje pierwsze osiem bajtów <xref:System.IO.FileStream> zaszyfrowanego pakietu do tablic bajtów w celu uzyskania długości zaszyfrowanego klucza i IV.</span><span class="sxs-lookup"><span data-stu-id="5c07f-185">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="5c07f-186">Wyodrębnia klucz i IV z pakietu szyfrowania do tablic bajtowych.</span><span class="sxs-lookup"><span data-stu-id="5c07f-186">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="5c07f-187">Tworzy <xref:System.Security.Cryptography.RSACryptoServiceProvider> obiekt do odszyfrowania <xref:System.Security.Cryptography.Aes> klucza.</span><span class="sxs-lookup"><span data-stu-id="5c07f-187">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
5. <span data-ttu-id="5c07f-188">Używa <xref:System.Security.Cryptography.CryptoStream> obiektu do odczytywania i odszyfrowywania sekcji szyfrowania tekstu <xref:System.IO.FileStream> pakietu szyfrowania w blokach bajtów do <xref:System.IO.FileStream> obiektu w odszyfrowanym pliku.</span><span class="sxs-lookup"><span data-stu-id="5c07f-188">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="5c07f-189">Po zakończeniu odszyfrowywania zostanie zakończone.</span><span class="sxs-lookup"><span data-stu-id="5c07f-189">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="5c07f-190">Dodaj następujący kod jako `Click` procedurę obsługi zdarzeń dla `Decrypt File` przycisku.</span><span class="sxs-lookup"><span data-stu-id="5c07f-190">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="5c07f-191">Dodaj następującą `DecryptFile` metodę do formularza.</span><span class="sxs-lookup"><span data-stu-id="5c07f-191">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="5c07f-192">Eksportowanie klucza publicznego</span><span class="sxs-lookup"><span data-stu-id="5c07f-192">Exporting a Public Key</span></span>

<span data-ttu-id="5c07f-193">To zadanie służy do zapisywania klucza utworzonego przez `Create Keys` przycisk do pliku.</span><span class="sxs-lookup"><span data-stu-id="5c07f-193">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="5c07f-194">Eksportuje tylko parametry publiczne.</span><span class="sxs-lookup"><span data-stu-id="5c07f-194">It exports only the public parameters.</span></span>  
  
<span data-ttu-id="5c07f-195">To zadanie symuluje scenariusz dla Alicja przekazującej Roberta swój klucz publiczny, aby mógł szyfrować pliki.</span><span class="sxs-lookup"><span data-stu-id="5c07f-195">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="5c07f-196">Osoby, które mają ten klucz publiczny, nie będą w stanie odszyfrować, ponieważ nie mają pełnej pary kluczy z parametrami prywatnymi.</span><span class="sxs-lookup"><span data-stu-id="5c07f-196">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="5c07f-197">Dodaj następujący kod jako `Click` procedurę obsługi zdarzeń dla `Export Public Key` przycisku ( `buttonExportPublicKey_Click` ).</span><span class="sxs-lookup"><span data-stu-id="5c07f-197">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
[!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="5c07f-198">Importowanie klucza publicznego</span><span class="sxs-lookup"><span data-stu-id="5c07f-198">Importing a Public Key</span></span>

<span data-ttu-id="5c07f-199">To zadanie ładuje klucz z tylko parametrami publicznymi, utworzonym przez `Export Public Key` przycisk i ustawia go jako nazwę kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="5c07f-199">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
<span data-ttu-id="5c07f-200">To zadanie symuluje scenariusz ładowania klucza Alicja z tylko parametrami publicznymi, dzięki czemu może zaszyfrować pliki.</span><span class="sxs-lookup"><span data-stu-id="5c07f-200">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
<span data-ttu-id="5c07f-201">Dodaj następujący kod jako `Click` procedurę obsługi zdarzeń dla `Import Public Key` przycisku ( `buttonImportPublicKey_Click` ).</span><span class="sxs-lookup"><span data-stu-id="5c07f-201">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
[!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="5c07f-202">Pobieranie klucza prywatnego</span><span class="sxs-lookup"><span data-stu-id="5c07f-202">Getting a Private Key</span></span>  

<span data-ttu-id="5c07f-203">To zadanie ustawia nazwę kontenera kluczy na nazwę klucza utworzonego za pomocą `Create Keys` przycisku.</span><span class="sxs-lookup"><span data-stu-id="5c07f-203">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="5c07f-204">Kontener kluczy będzie zawierać pełną parę kluczy z parametrami prywatnymi.</span><span class="sxs-lookup"><span data-stu-id="5c07f-204">The key container will contain the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="5c07f-205">To zadanie symuluje scenariusz Alicja przy użyciu klucza prywatnego w celu odszyfrowania plików zaszyfrowanych przez Robert.</span><span class="sxs-lookup"><span data-stu-id="5c07f-205">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
<span data-ttu-id="5c07f-206">Dodaj następujący kod jako `Click` procedurę obsługi zdarzeń dla `Get Private Key` przycisku ( `buttonGetPrivateKey_Click` ).</span><span class="sxs-lookup"><span data-stu-id="5c07f-206">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
[!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="5c07f-207">Testowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="5c07f-207">Testing the Application</span></span>

<span data-ttu-id="5c07f-208">Po skompilowaniu aplikacji wykonaj następujące scenariusze testowania.</span><span class="sxs-lookup"><span data-stu-id="5c07f-208">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="5c07f-209">Aby utworzyć klucze, szyfrowanie i odszyfrowywanie</span><span class="sxs-lookup"><span data-stu-id="5c07f-209">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="5c07f-210">Kliknij przycisk `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="5c07f-210">Click the `Create Keys` button.</span></span> <span data-ttu-id="5c07f-211">Etykieta Wyświetla nazwę klucza i pokazuje, że jest to pełna para kluczy.</span><span class="sxs-lookup"><span data-stu-id="5c07f-211">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="5c07f-212">Kliknij przycisk `Export Public Key`.</span><span class="sxs-lookup"><span data-stu-id="5c07f-212">Click the `Export Public Key` button.</span></span> <span data-ttu-id="5c07f-213">Należy zauważyć, że eksportowanie parametrów klucza publicznego nie zmienia bieżącego klucza.</span><span class="sxs-lookup"><span data-stu-id="5c07f-213">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="5c07f-214">Kliknij `Encrypt File` przycisk i wybierz plik.</span><span class="sxs-lookup"><span data-stu-id="5c07f-214">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="5c07f-215">Kliknij `Decrypt File` przycisk i wybierz plik, który został zaszyfrowany.</span><span class="sxs-lookup"><span data-stu-id="5c07f-215">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="5c07f-216">Zapoznaj się z odszyfrowaniem pliku.</span><span class="sxs-lookup"><span data-stu-id="5c07f-216">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="5c07f-217">Zamknij aplikację i uruchom ją ponownie, aby przetestować pobieranie utrwalonych kontenerów kluczy w następnym scenariuszu.</span><span class="sxs-lookup"><span data-stu-id="5c07f-217">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="5c07f-218">Aby zaszyfrować przy użyciu klucza publicznego</span><span class="sxs-lookup"><span data-stu-id="5c07f-218">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="5c07f-219">Kliknij przycisk `Import Public Key`.</span><span class="sxs-lookup"><span data-stu-id="5c07f-219">Click the `Import Public Key` button.</span></span> <span data-ttu-id="5c07f-220">Etykieta Wyświetla nazwę klucza i pokazuje, że jest tylko publiczna.</span><span class="sxs-lookup"><span data-stu-id="5c07f-220">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="5c07f-221">Kliknij `Encrypt File` przycisk i wybierz plik.</span><span class="sxs-lookup"><span data-stu-id="5c07f-221">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="5c07f-222">Kliknij `Decrypt File` przycisk i wybierz plik, który został zaszyfrowany.</span><span class="sxs-lookup"><span data-stu-id="5c07f-222">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="5c07f-223">Nie powiedzie się, ponieważ musisz mieć klucz prywatny do odszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="5c07f-223">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="5c07f-224">W tym scenariuszu przedstawiono tylko klucz publiczny do szyfrowania pliku dla innej osoby.</span><span class="sxs-lookup"><span data-stu-id="5c07f-224">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="5c07f-225">Zwykle osoba ta może uzyskać tylko klucz publiczny i wstrzymać klucz prywatny do odszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="5c07f-225">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="5c07f-226">Aby odszyfrować przy użyciu klucza prywatnego</span><span class="sxs-lookup"><span data-stu-id="5c07f-226">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="5c07f-227">Kliknij przycisk `Get Private Key`.</span><span class="sxs-lookup"><span data-stu-id="5c07f-227">Click the `Get Private Key` button.</span></span> <span data-ttu-id="5c07f-228">Etykieta Wyświetla nazwę klucza i pokazuje, czy jest to pełna para kluczy.</span><span class="sxs-lookup"><span data-stu-id="5c07f-228">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="5c07f-229">Kliknij `Decrypt File` przycisk i wybierz plik, który został zaszyfrowany.</span><span class="sxs-lookup"><span data-stu-id="5c07f-229">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="5c07f-230">Ta operacja zakończy się pomyślnie, ponieważ masz pełną parę kluczy do odszyfrowania.</span><span class="sxs-lookup"><span data-stu-id="5c07f-230">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c07f-231">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5c07f-231">See also</span></span>

- <span data-ttu-id="5c07f-232">[Model kryptografii](cryptography-model.md) — opis sposobu implementacji kryptografii w bibliotece klas bazowych.</span><span class="sxs-lookup"><span data-stu-id="5c07f-232">[Cryptography Model](cryptography-model.md) - Describes how cryptography is implemented in the base class library.</span></span>
- [<span data-ttu-id="5c07f-233">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="5c07f-233">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="5c07f-234">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="5c07f-234">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="5c07f-235">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5c07f-235">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
