---
title: 'Instrukcje: przechowywanie kluczy asymetrycznych w kontenerze kluczy'
description: Dowiedz się, jak przechowywać klucze asymetryczne w kontenerze kluczy w programie .NET. Zobacz jak utworzyć klucz asymetryczny, zapisać go w kontenerze kluczy i pobrać i usunąć klucz.
ms.date: 05/26/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET]
- encryption [.NET], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: aa6fad815338cbd6316deca7be0a23286630fa56
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556296"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="dcc64-104">Przechowywanie kluczy asymetrycznych w kontenerze kluczy</span><span class="sxs-lookup"><span data-stu-id="dcc64-104">Store asymmetric keys in a key container</span></span>

<span data-ttu-id="dcc64-105">Asymetryczne klucze prywatne nigdy nie powinny być przechowywane Verbatim ani w postaci zwykłego tekstu na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="dcc64-105">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="dcc64-106">Jeśli musisz zapisać klucz prywatny, Użyj kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="dcc64-106">If you need to store a private key, use a key container.</span></span> <span data-ttu-id="dcc64-107">Aby uzyskać więcej informacji na temat kontenerów kluczy, zobacz temat [Omówienie kontenerów kluczy RSA na poziomie komputera i użytkownika](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="dcc64-107">For more information on key containers, see [Understanding machine-level and user-level RSA key containers](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="dcc64-108">Kod w tym artykule ma zastosowanie do systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="dcc64-108">The code in this article applies to Windows.</span></span>

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="dcc64-109">Tworzenie klucza asymetrycznego i zapisywanie go w kontenerze kluczy</span><span class="sxs-lookup"><span data-stu-id="dcc64-109">Create an asymmetric key and save it in a key container</span></span>

1. <span data-ttu-id="dcc64-110">Utwórz nowe wystąpienie <xref:System.Security.Cryptography.CspParameters> klasy i przekaż nazwę, która ma być wywoływana przez kontener kluczy do <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> pola.</span><span class="sxs-lookup"><span data-stu-id="dcc64-110">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="dcc64-111">Utwórz nowe wystąpienie klasy, która dziedziczy z <xref:System.Security.Cryptography.AsymmetricAlgorithm> klasy (zwykle <xref:System.Security.Cryptography.RSACryptoServiceProvider> lub <xref:System.Security.Cryptography.DSACryptoServiceProvider> ) i przekaż wcześniej utworzony `CspParameters` obiekt do jego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="dcc64-111">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually <xref:System.Security.Cryptography.RSACryptoServiceProvider> or <xref:System.Security.Cryptography.DSACryptoServiceProvider>) and pass the previously created `CspParameters` object to its constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="dcc64-112">Tworzenie i pobieranie klucza asymetrycznego jest jedną operacją.</span><span class="sxs-lookup"><span data-stu-id="dcc64-112">The creation and retrieval of an asymmetric key is one operation.</span></span> <span data-ttu-id="dcc64-113">Jeśli klucz nie znajduje się już w kontenerze, jest tworzony przed zwróceniem.</span><span class="sxs-lookup"><span data-stu-id="dcc64-113">If a key is not already in the container, it's created before being returned.</span></span>
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a><span data-ttu-id="dcc64-114">Usuń klucz z kontenera kluczy</span><span class="sxs-lookup"><span data-stu-id="dcc64-114">Delete the key from the key container</span></span>

1. <span data-ttu-id="dcc64-115">Utwórz nowe wystąpienie `CspParameters` klasy i przekaż nazwę, która ma być wywoływana przez kontener kluczy do <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> pola.</span><span class="sxs-lookup"><span data-stu-id="dcc64-115">Create a new instance of a `CspParameters` class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="dcc64-116">Utwórz nowe wystąpienie klasy, która dziedziczy z <xref:System.Security.Cryptography.AsymmetricAlgorithm> klasy (zwykle `RSACryptoServiceProvider` lub `DSACryptoServiceProvider` ) i przekaż wcześniej utworzony `CspParameters` obiekt do jego konstruktora.</span><span class="sxs-lookup"><span data-stu-id="dcc64-116">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually `RSACryptoServiceProvider` or `DSACryptoServiceProvider`) and pass the previously created `CspParameters` object to its constructor.</span></span>

1. <span data-ttu-id="dcc64-117">Ustaw <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> lub <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> Właściwość klasy, która pochodzi od `AsymmetricAlgorithm` do `false` ( `False` w Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dcc64-117">Set the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> or the <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> property of the class that derives from `AsymmetricAlgorithm` to `false` (`False` in Visual Basic).</span></span>

1. <span data-ttu-id="dcc64-118">Wywoływanie `Clear` metody klasy, która dziedziczy z `AsymmetricAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="dcc64-118">Call the `Clear` method of the class that derives from `AsymmetricAlgorithm`.</span></span> <span data-ttu-id="dcc64-119">Ta metoda zwalnia wszystkie zasoby klasy i czyści kontener kluczy.</span><span class="sxs-lookup"><span data-stu-id="dcc64-119">This method releases all resources of the class and clears the key container.</span></span>

## <a name="example"></a><span data-ttu-id="dcc64-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="dcc64-120">Example</span></span>

<span data-ttu-id="dcc64-121">Poniższy przykład ilustruje sposób tworzenia klucza asymetrycznego, zapisywania go w kontenerze kluczy, pobierania klucza w późniejszym czasie i usuwania klucza z kontenera.</span><span class="sxs-lookup"><span data-stu-id="dcc64-121">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>

<span data-ttu-id="dcc64-122">Zwróć uwagę, że kod w `GenKey_SaveInContainer` metodzie i `GetKeyFromContainer` metodzie jest podobny.</span><span class="sxs-lookup"><span data-stu-id="dcc64-122">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span> <span data-ttu-id="dcc64-123">Jeśli określisz nazwę kontenera kluczy dla <xref:System.Security.Cryptography.CspParameters> obiektu i przekażesz go do <xref:System.Security.Cryptography.AsymmetricAlgorithm> obiektu z <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> właściwością lub <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> właściwością ustawioną na `true` , zachowanie jest następujące:</span><span class="sxs-lookup"><span data-stu-id="dcc64-123">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to `true`, the behavior is as follows:</span></span>

- <span data-ttu-id="dcc64-124">Jeśli kontener kluczy o podanej nazwie nie istnieje, zostanie utworzony jeden i klucz zostanie utrwalony.</span><span class="sxs-lookup"><span data-stu-id="dcc64-124">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>
- <span data-ttu-id="dcc64-125">Jeśli istnieje kontener kluczy o podanej nazwie, klucz w kontenerze zostanie automatycznie załadowany do bieżącego <xref:System.Security.Cryptography.AsymmetricAlgorithm> obiektu.</span><span class="sxs-lookup"><span data-stu-id="dcc64-125">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>

<span data-ttu-id="dcc64-126">W związku z tym kod w `GenKey_SaveInContainer` metodzie utrzymuje klucz, ponieważ jest uruchamiany jako pierwszy, podczas gdy kod w `GetKeyFromContainer` metodzie ładuje klucz, ponieważ jest uruchamiany drugi.</span><span class="sxs-lookup"><span data-stu-id="dcc64-126">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it's run second.</span></span>

```vb
Imports System
Imports System.Security.Cryptography

Public Class StoreKey

    Public Shared Sub Main()
        Try
            ' Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer")

            ' Retrieve the key from the container.
            GetKeyFromContainer("MyKeyContainer")

            ' Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer")

            ' Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer")

            ' Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer")
        Catch e As CryptographicException
            Console.WriteLine(e.Message)
        End Try
    End Sub

    Private Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        ' name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key added to container:  {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub GetKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key retrieved from container : {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container.
        ' Delete the key entry in the container.
        Dim rsa As New RSACryptoServiceProvider(parameters) With {
            .PersistKeyInCsp = False
        }

        ' Call Clear to release resources and delete the key from the container.
        rsa.Clear()

        Console.WriteLine("Key deleted.")
    End Sub
End Class
```

```csharp
using System;
using System.Security.Cryptography;

public class StoreKey
{
    public static void Main()
    {
        try
        {
            // Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer");

            // Retrieve the key from the container.
            GetKeyFromContainer("MyKeyContainer");

            // Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer");

            // Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer");

            // Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer");
        }
        catch (CryptographicException e)
        {
            Console.WriteLine(e.Message);
        }
    }

    private static void GenKey_SaveInContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key added to container: \n  {rsa.ToXmlString(true)}");
    }

    private static void GetKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key retrieved from container : \n {rsa.ToXmlString(true)}");
    }

    private static void DeleteKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container.
        using var rsa = new RSACryptoServiceProvider(parameters)
        {
            // Delete the key entry in the container.
            PersistKeyInCsp = false
        };

        // Call Clear to release resources and delete the key from the container.
        rsa.Clear();

        Console.WriteLine("Key deleted.");
    }
}
```

<span data-ttu-id="dcc64-127">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="dcc64-127">The output is as follows:</span></span>

```console
Key added to container:
<RSAKeyValue> Key Information A</RSAKeyValue>
Key retrieved from container :
<RSAKeyValue> Key Information A</RSAKeyValue>
Key deleted.
Key added to container:
<RSAKeyValue> Key Information B</RSAKeyValue>
Key deleted.
```

## <a name="see-also"></a><span data-ttu-id="dcc64-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dcc64-128">See also</span></span>

- [<span data-ttu-id="dcc64-129">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="dcc64-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="dcc64-130">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="dcc64-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="dcc64-131">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="dcc64-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="dcc64-132">Generowanie kluczy szyfrowania i odszyfrowywania</span><span class="sxs-lookup"><span data-stu-id="dcc64-132">Generating keys for encryption and decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="dcc64-133">Szyfrowanie danych</span><span class="sxs-lookup"><span data-stu-id="dcc64-133">Encrypting data</span></span>](encrypting-data.md)
- [<span data-ttu-id="dcc64-134">Odszyfrowywanie danych</span><span class="sxs-lookup"><span data-stu-id="dcc64-134">Decrypting data</span></span>](decrypting-data.md)
- [<span data-ttu-id="dcc64-135">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dcc64-135">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
