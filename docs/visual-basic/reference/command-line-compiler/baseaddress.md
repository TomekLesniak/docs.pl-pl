---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: c794d1fc1c9d20e22ffa747e3175c846341ad8ad
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097764"
---
# <a name="-baseaddress"></a><span data-ttu-id="1dea3-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="1dea3-102">-baseaddress</span></span>

<span data-ttu-id="1dea3-103">Określa domyślny adres podstawowy podczas tworzenia biblioteki DLL.</span><span class="sxs-lookup"><span data-stu-id="1dea3-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dea3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1dea3-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="1dea3-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="1dea3-105">Arguments</span></span>  
  
|<span data-ttu-id="1dea3-106">Termin</span><span class="sxs-lookup"><span data-stu-id="1dea3-106">Term</span></span>|<span data-ttu-id="1dea3-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="1dea3-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="1dea3-108">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="1dea3-108">Required.</span></span> <span data-ttu-id="1dea3-109">Adres podstawowy biblioteki DLL.</span><span class="sxs-lookup"><span data-stu-id="1dea3-109">The base address for the DLL.</span></span> <span data-ttu-id="1dea3-110">Ten adres musi być określony jako liczba szesnastkowa.</span><span class="sxs-lookup"><span data-stu-id="1dea3-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dea3-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1dea3-111">Remarks</span></span>  

 <span data-ttu-id="1dea3-112">Domyślny adres podstawowy dla biblioteki DLL jest ustawiany przez .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1dea3-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="1dea3-113">Należy pamiętać, że w tym adresie znajduje się wyraz o niższej kolejności.</span><span class="sxs-lookup"><span data-stu-id="1dea3-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="1dea3-114">Na przykład, jeśli określisz 0x11110001, zostanie zaokrąglona do 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="1dea3-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="1dea3-115">Aby ukończyć proces podpisywania dla biblioteki DLL, użyj `–R` opcji narzędzia silnego nazewnictwa (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="1dea3-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="1dea3-116">Ta opcja jest ignorowana, jeśli obiekt docelowy nie jest biblioteką DLL.</span><span class="sxs-lookup"><span data-stu-id="1dea3-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="1dea3-117">Aby ustawić-BaseAddress w środowisku IDE programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1dea3-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="1dea3-118">1. zaznaczono projekt w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="1dea3-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1dea3-119">W menu **projekt** kliknij polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="1dea3-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1dea3-120">2. Kliknij kartę **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="1dea3-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="1dea3-121">3. kliknij pozycję **Zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="1dea3-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="1dea3-122">4. Zmodyfikuj wartość w polu **adres podstawowy biblioteki dll:** .</span><span class="sxs-lookup"><span data-stu-id="1dea3-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="1dea3-123">**Uwaga:**      **Adres podstawowy biblioteki dll:** pole jest tylko do odczytu, chyba że obiekt docelowy jest biblioteką DLL.</span><span class="sxs-lookup"><span data-stu-id="1dea3-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dea3-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1dea3-124">See also</span></span>

- [<span data-ttu-id="1dea3-125">Kompilator wiersza polecenia Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1dea3-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="1dea3-126">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1dea3-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="1dea3-127">Przykłady kompilacji — wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="1dea3-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="1dea3-128">[Sn.exe (Narzędzie silnej nazwy)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="1dea3-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
