---
title: 'Instrukcje: Ładowanie i zwalnianie zestawów'
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: 77ea97c2fc324287e9c697d630def98241432c9f
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2019
ms.locfileid: "70973202"
---
# <a name="how-to-load-and-unload-assemblies"></a><span data-ttu-id="ba76a-102">Instrukcje: Ładowanie i zwalnianie zestawów</span><span class="sxs-lookup"><span data-stu-id="ba76a-102">How to: Load and unload assemblies</span></span>
<span data-ttu-id="ba76a-103">Zestawy, do których odwołuje się program, zostaną automatycznie załadowane przez środowisko uruchomieniowe języka wspólnego, ale możliwe jest również dynamiczne ładowanie określonych zestawów do domeny bieżącej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ba76a-103">The assemblies referenced by your program will automatically be loaded by the common language runtime, but it is also possible to dynamically load specific assemblies into the current application domain.</span></span> <span data-ttu-id="ba76a-104">Aby uzyskać więcej informacji, zobacz [jak: Ładowanie zestawów do domeny](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ba76a-104">For more information, see [How to: Load assemblies into an application domain](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>

<span data-ttu-id="ba76a-105">W .NET Framework nie ma możliwości zwolnienia pojedynczego zestawu bez zwalniania wszystkich domen aplikacji, które go zawierają.</span><span class="sxs-lookup"><span data-stu-id="ba76a-105">In .NET Framework, there is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="ba76a-106">Nawet jeśli zestaw wykracza poza zakres, rzeczywisty plik zestawu pozostanie załadowany do momentu, gdy wszystkie domeny aplikacji, które go zawierają, zostaną zwolnione.</span><span class="sxs-lookup"><span data-stu-id="ba76a-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span> <span data-ttu-id="ba76a-107">W programie .NET Core <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> Klasa obsługuje zwalnianie zestawów.</span><span class="sxs-lookup"><span data-stu-id="ba76a-107">In .NET Core, the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> class handles the unloading of assemblies.</span></span> <span data-ttu-id="ba76a-108">Aby uzyskać więcej informacji, zobacz [jak używać i debugować możliwość odciążania zestawów w programie .NET Core](unloadability.md).</span><span class="sxs-lookup"><span data-stu-id="ba76a-108">For more information, see [How to use and debug assembly unloadability in .NET Core](unloadability.md).</span></span>

## <a name="load-and-unload-assemblies"></a><span data-ttu-id="ba76a-109">Ładowanie i zwalnianie zestawów</span><span class="sxs-lookup"><span data-stu-id="ba76a-109">Load and unload assemblies</span></span>

<span data-ttu-id="ba76a-110">Aby załadować zestaw do domeny aplikacji, należy użyć jednej z kilku metod obciążenia zawartych w klasach <xref:System.AppDomain> i. <xref:System.Reflection.Assembly></span><span class="sxs-lookup"><span data-stu-id="ba76a-110">To load an assembly into an application domain, use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection.Assembly>.</span></span> <span data-ttu-id="ba76a-111">Aby uzyskać więcej informacji, zobacz [jak: Ładowanie zestawów do domeny](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ba76a-111">For more information, see [How to: Load assemblies into an application domain](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span> <span data-ttu-id="ba76a-112">Należy zauważyć, że platforma .NET Core obsługuje tylko jedną domenę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ba76a-112">Note that .NET Core supports only a single application domain.</span></span> 

<span data-ttu-id="ba76a-113">Aby zwolnić zestaw w .NET Framework, musisz zwolnić wszystkie domeny aplikacji, które go zawierają.</span><span class="sxs-lookup"><span data-stu-id="ba76a-113">To unload an assembly in the .NET Framework, you must unload all of the application domains that contain it.</span></span> <span data-ttu-id="ba76a-114">Aby zwolnić domenę aplikacji, należy użyć <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="ba76a-114">To unload an application domain, use the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ba76a-115">Aby uzyskać więcej informacji, zobacz [jak: Zwolnij domenę](../../framework/app-domains/how-to-unload-an-application-domain.md)aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ba76a-115">For more information, see [How to: Unload an application domain](../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>

<span data-ttu-id="ba76a-116">Jeśli chcesz zwolnić niektóre zestawy, ale nie inne w aplikacji .NET Framework, rozważ utworzenie nowej domeny aplikacji, wykonanie kodu w tej domenie, a następnie zwolnienie tej domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ba76a-116">If you want to unload some assemblies but not others in a .NET Framework application, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="ba76a-117">Aby uzyskać więcej informacji, zobacz [jak: Zwolnij domenę](../../framework/app-domains/how-to-unload-an-application-domain.md)aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ba76a-117">For more information, see [How to: Unload an application domain](../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="ba76a-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ba76a-118">See also</span></span>

- [<span data-ttu-id="ba76a-119">C#Przewodnik programowania</span><span class="sxs-lookup"><span data-stu-id="ba76a-119">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ba76a-120">Koncepcje programowania (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba76a-120">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="ba76a-121">Zestawy w środowisku .NET</span><span class="sxs-lookup"><span data-stu-id="ba76a-121">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="ba76a-122">Instrukcje: Ładowanie zestawów do domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="ba76a-122">How to: Load assemblies into an application domain</span></span>](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)