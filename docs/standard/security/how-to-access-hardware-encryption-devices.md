---
title: 'Instrukcje: Dostęp do sprzętowych urządzeń szyfrujących'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
ms.openlocfilehash: 7cd3aab80a8388c1d4ce08e4ae94aae84cfff239
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557141"
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="93f41-102">Instrukcje: Dostęp do sprzętowych urządzeń szyfrujących</span><span class="sxs-lookup"><span data-stu-id="93f41-102">How to: Access Hardware Encryption Devices</span></span>

> [!NOTE]
> <span data-ttu-id="93f41-103">Ten artykuł dotyczy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="93f41-103">This article applies to Windows.</span></span>

<span data-ttu-id="93f41-104"><xref:System.Security.Cryptography.CspParameters>Aby uzyskać dostęp do urządzeń do szyfrowania sprzętu, można użyć klasy.</span><span class="sxs-lookup"><span data-stu-id="93f41-104">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="93f41-105">Na przykład można użyć tej klasy do zintegrowania aplikacji z kartą inteligentną, generatorem losowych liczb sprzętowych lub sprzętową implementacją określonego algorytmu kryptograficznego.</span><span class="sxs-lookup"><span data-stu-id="93f41-105">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  

<span data-ttu-id="93f41-106"><xref:System.Security.Cryptography.CspParameters>Klasa tworzy dostawcę usług kryptograficznych (CSP), który uzyskuje dostęp do prawidłowo zainstalowanego urządzenia szyfrującego sprzęt.</span><span class="sxs-lookup"><span data-stu-id="93f41-106">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="93f41-107">Dostępność dostawcy CSP można sprawdzić, sprawdzając następujący klucz rejestru przy użyciu Edytora rejestru (Regedit.exe): HKEY_LOCAL_MACHINE \Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="93f41-107">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="93f41-108">Aby podpisać dane przy użyciu karty klucza</span><span class="sxs-lookup"><span data-stu-id="93f41-108">To sign data using a key card</span></span>  
  
1. <span data-ttu-id="93f41-109">Utwórz nowe wystąpienie <xref:System.Security.Cryptography.CspParameters> klasy, przekazując typ dostawcy integer i nazwę dostawcy do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="93f41-109">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="93f41-110">Przekaż odpowiednie flagi do <xref:System.Security.Cryptography.CspParameters.Flags%2A> właściwości nowo utworzonego <xref:System.Security.Cryptography.CspParameters> obiektu.</span><span class="sxs-lookup"><span data-stu-id="93f41-110">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="93f41-111">Na przykład, Przekaż <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flagę.</span><span class="sxs-lookup"><span data-stu-id="93f41-111">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3. <span data-ttu-id="93f41-112">Utwórz nowe wystąpienie <xref:System.Security.Cryptography.AsymmetricAlgorithm> klasy (na przykład <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy), przekazując <xref:System.Security.Cryptography.CspParameters> obiekt do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="93f41-112">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4. <span data-ttu-id="93f41-113">Podpisz swoje dane przy użyciu jednej z `Sign` metod i sprawdź swoje dane przy użyciu jednej z `Verify` metod.</span><span class="sxs-lookup"><span data-stu-id="93f41-113">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="93f41-114">Aby wygenerować liczbę losową przy użyciu generatora liczb losowych sprzętowych</span><span class="sxs-lookup"><span data-stu-id="93f41-114">To generate a random number using a hardware random number generator</span></span>  
  
1. <span data-ttu-id="93f41-115">Utwórz nowe wystąpienie <xref:System.Security.Cryptography.CspParameters> klasy, przekazując typ dostawcy integer i nazwę dostawcy do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="93f41-115">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="93f41-116">Utwórz nowe wystąpienie <xref:System.Security.Cryptography.RNGCryptoServiceProvider> , przekazując <xref:System.Security.Cryptography.CspParameters> obiekt do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="93f41-116">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3. <span data-ttu-id="93f41-117">Utwórz wartość losową przy użyciu <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> metody lub.</span><span class="sxs-lookup"><span data-stu-id="93f41-117">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93f41-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="93f41-118">Example</span></span>

<span data-ttu-id="93f41-119">Poniższy przykład kodu demonstruje sposób podpisywania danych przy użyciu karty inteligentnej.</span><span class="sxs-lookup"><span data-stu-id="93f41-119">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="93f41-120">Przykładowy kod tworzy <xref:System.Security.Cryptography.CspParameters> obiekt, który uwidacznia kartę inteligentną, a następnie inicjuje <xref:System.Security.Cryptography.RSACryptoServiceProvider> Obiekt przy użyciu dostawcy CSP.</span><span class="sxs-lookup"><span data-stu-id="93f41-120">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="93f41-121">Przykład kodu następnie podpisuje i weryfikuje niektóre dane.</span><span class="sxs-lookup"><span data-stu-id="93f41-121">The code example then signs and verifies some data.</span></span>  

<span data-ttu-id="93f41-122">Ze względu na kolizje problemów z algorytmem SHA1 zalecamy SHA256 lub lepszą.</span><span class="sxs-lookup"><span data-stu-id="93f41-122">Due to collision problems with SHA1, we recommend SHA256 or better.</span></span>
  
[!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
[!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
[!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93f41-123">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="93f41-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="93f41-124">Uwzględnij <xref:System> <xref:System.Security.Cryptography> przestrzenie nazw i.</span><span class="sxs-lookup"><span data-stu-id="93f41-124">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
- <span data-ttu-id="93f41-125">Na komputerze musi być zainstalowany czytnik kart inteligentnych i sterowniki.</span><span class="sxs-lookup"><span data-stu-id="93f41-125">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
- <span data-ttu-id="93f41-126">Należy zainicjować <xref:System.Security.Cryptography.CspParameters> Obiekt przy użyciu informacji specyficznych dla czytnika kart.</span><span class="sxs-lookup"><span data-stu-id="93f41-126">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="93f41-127">Aby uzyskać więcej informacji, zobacz dokumentację czytnika kart.</span><span class="sxs-lookup"><span data-stu-id="93f41-127">For more information, see the documentation of your card reader.</span></span>

## <a name="see-also"></a><span data-ttu-id="93f41-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="93f41-128">See also</span></span>

- [<span data-ttu-id="93f41-129">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="93f41-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="93f41-130">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="93f41-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="93f41-131">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="93f41-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="93f41-132">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="93f41-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
