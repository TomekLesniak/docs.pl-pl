---
title: Operacje potokowe w programie .NET
description: 'Informacje o operacjach potoku w programie .NET. Potoki zapewniają metodę komunikacji międzyprocesowej. Istnieją dwa rodzaje potoków: anonimowe potoki i nazwane potoki.'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET]
- pipe operations [.NET]
- interprocess communication [.NET], pipes
- I/O [.NET], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 8d954d55e07a7cbb2b09843afe7f45b1ff5abcc7
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188864"
---
# <a name="pipe-operations-in-net"></a><span data-ttu-id="4b71f-105">Operacje potokowe w programie .NET</span><span class="sxs-lookup"><span data-stu-id="4b71f-105">Pipe Operations in .NET</span></span>
<span data-ttu-id="4b71f-106">Potoki zapewniają metodę komunikacji międzyprocesowej.</span><span class="sxs-lookup"><span data-stu-id="4b71f-106">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="4b71f-107">Istnieją dwa typy potoków:</span><span class="sxs-lookup"><span data-stu-id="4b71f-107">There are two types of pipes:</span></span>  
  
- <span data-ttu-id="4b71f-108">Potoki anonimowe.</span><span class="sxs-lookup"><span data-stu-id="4b71f-108">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="4b71f-109">Potoki anonimowe zapewniają komunikację międzyprocesową na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="4b71f-109">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="4b71f-110">Potoki anonimowe wymagają mniej obciążenia niż potoki nazwane, ale oferują ograniczone usługi.</span><span class="sxs-lookup"><span data-stu-id="4b71f-110">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="4b71f-111">Potoki anonimowe są jednokierunkowe i nie mogą być używane w sieci.</span><span class="sxs-lookup"><span data-stu-id="4b71f-111">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="4b71f-112">Obsługują one tylko jedno wystąpienie serwera.</span><span class="sxs-lookup"><span data-stu-id="4b71f-112">They support only a single server instance.</span></span> <span data-ttu-id="4b71f-113">Potoki anonimowe są przydatne do komunikacji między wątkami lub między procesami nadrzędnymi i podrzędnymi, w których uchwyty potoku mogą być łatwo przesłane do procesu podrzędnego po jego utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="4b71f-113">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="4b71f-114">W programie .NET można zaimplementować anonimowe potoki przy <xref:System.IO.Pipes.AnonymousPipeServerStream> użyciu <xref:System.IO.Pipes.AnonymousPipeClientStream> klas i.</span><span class="sxs-lookup"><span data-stu-id="4b71f-114">In .NET, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="4b71f-115">Zobacz [jak: korzystanie z anonimowych potoków do lokalnej komunikacji międzyprocesowej](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="4b71f-115">See [How to: Use Anonymous Pipes for Local Interprocess Communication](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
- <span data-ttu-id="4b71f-116">Nazwane potoki.</span><span class="sxs-lookup"><span data-stu-id="4b71f-116">Named pipes.</span></span>  
  
     <span data-ttu-id="4b71f-117">Nazwane potoki zapewniają komunikację międzyprocesorową pomiędzy serwerem potoku i jednym lub kilkoma klientami potoku.</span><span class="sxs-lookup"><span data-stu-id="4b71f-117">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="4b71f-118">Nazwane potoki mogą być jednokierunkowe lub dwustronne.</span><span class="sxs-lookup"><span data-stu-id="4b71f-118">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="4b71f-119">Obsługują komunikację opartą na komunikatach i umożliwiają wielu klientom jednoczesne łączenie się z procesem serwera przy użyciu tej samej nazwy potoku.</span><span class="sxs-lookup"><span data-stu-id="4b71f-119">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="4b71f-120">Nazwane potoki obsługują również personifikację, która umożliwia łączenie procesów w celu używania ich własnych uprawnień na serwerach zdalnych.</span><span class="sxs-lookup"><span data-stu-id="4b71f-120">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="4b71f-121">W programie .NET należy zaimplementować nazwane potoki przy użyciu <xref:System.IO.Pipes.NamedPipeServerStream> <xref:System.IO.Pipes.NamedPipeClientStream> klas i.</span><span class="sxs-lookup"><span data-stu-id="4b71f-121">In .NET, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="4b71f-122">Zobacz [jak: używanie nazwanych potoków do komunikacji międzyprocesowej sieci](how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="4b71f-122">See [How to: Use Named Pipes for Network Interprocess Communication](how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b71f-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4b71f-123">See also</span></span>

- [<span data-ttu-id="4b71f-124">We/wy plików i strumieni</span><span class="sxs-lookup"><span data-stu-id="4b71f-124">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="4b71f-125">Instrukcje: Stosowanie anonimowych potoków do lokalnej komunikacji międzyprocesowej</span><span class="sxs-lookup"><span data-stu-id="4b71f-125">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [<span data-ttu-id="4b71f-126">Instrukcje: Stosowanie nazwanych potoków do sieciowej komunikacji międzyprocesowej</span><span class="sxs-lookup"><span data-stu-id="4b71f-126">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
