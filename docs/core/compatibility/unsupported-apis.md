---
title: Nieobsługiwane interfejsy API w oprogramowaniu .NET Core i .NET 5 +
titleSuffix: ''
description: Dowiedz się, które interfejsy API platformy .NET zawsze zgłaszają wyjątek w oprogramowaniu .NET Core i .NET 5,0 i nowszych wersjach.
ms.date: 10/13/2020
ms.openlocfilehash: 51d73557a48910d9cb1c4d3cdced34dfe4d849d8
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329784"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="c767d-103">Interfejsy API, które zawsze generują wyjątki w oprogramowaniu .NET Core i .NET 5 +</span><span class="sxs-lookup"><span data-stu-id="c767d-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="c767d-104">Następujące interfejsy API zawsze będą zgłaszać <xref:System.PlatformNotSupportedException> na platformie .net 5,0 i nowszych wersjach (łącznie ze wszystkimi wersjami programu .NET Core) na wszystkich lub podzestawach platform.</span><span class="sxs-lookup"><span data-stu-id="c767d-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="c767d-105">Ten artykuł organizuje interfejsy API, których to dotyczy, według przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c767d-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c767d-106">Ten artykuł jest pracą w toku.</span><span class="sxs-lookup"><span data-stu-id="c767d-106">This article is a work-in-progress.</span></span> <span data-ttu-id="c767d-107">Nie jest to kompletna lista interfejsów API, które generują wyjątki w programie .NET 5 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="c767d-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="c767d-108">Ten artykuł nie zawiera jawnych implementacji interfejsu dla serializacji binarnej, która jest zgłaszana w programie .NET 5 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="c767d-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="c767d-109">Aby uzyskać więcej informacji, zobacz [Serializacja binarna w programie .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="c767d-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="c767d-110">System</span><span class="sxs-lookup"><span data-stu-id="c767d-110">System</span></span>

| <span data-ttu-id="c767d-111">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-111">Member</span></span> | <span data-ttu-id="c767d-112">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-113">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="c767d-114">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="c767d-115">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="c767d-116">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-117">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="c767d-118">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="c767d-119">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="c767d-120">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-121">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c767d-122">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="c767d-123">System. CodeDom. Compiler</span><span class="sxs-lookup"><span data-stu-id="c767d-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="c767d-124">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-124">Member</span></span> | <span data-ttu-id="c767d-125">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-126">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-127">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-128">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="c767d-129">System. Collections. specjalizowane</span><span class="sxs-lookup"><span data-stu-id="c767d-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="c767d-130">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-130">Member</span></span> | <span data-ttu-id="c767d-131">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-132">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-133">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c767d-134">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="c767d-135">System.Configwersja</span><span class="sxs-lookup"><span data-stu-id="c767d-135">System.Configuration</span></span>

| <span data-ttu-id="c767d-136">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-136">Member</span></span> | <span data-ttu-id="c767d-137">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c767d-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (wszystkie elementy członkowskie)</span><span class="sxs-lookup"><span data-stu-id="c767d-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="c767d-139">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="c767d-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="c767d-140">System.Console</span></span>

| <span data-ttu-id="c767d-141">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-141">Member</span></span> | <span data-ttu-id="c767d-142">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="c767d-143">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-143">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-145">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-145">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-147">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-147">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-149">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-149">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (tylko pobieranie)</span><span class="sxs-lookup"><span data-stu-id="c767d-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c767d-151">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-152">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-153">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-154">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-154">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-155"><xref:System.Console.Title?displayProperty=nameWithType> (tylko pobieranie)</span><span class="sxs-lookup"><span data-stu-id="c767d-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c767d-156">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-156">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-158">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-158">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-160">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-160">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-162">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-162">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-164">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="c767d-165">System. Data. Common</span><span class="sxs-lookup"><span data-stu-id="c767d-165">System.Data.Common</span></span>

| <span data-ttu-id="c767d-166">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-166">Member</span></span> | <span data-ttu-id="c767d-167">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c767d-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (zgłasza <xref:System.NotSupportedException> )</span><span class="sxs-lookup"><span data-stu-id="c767d-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="c767d-169">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="c767d-170">System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="c767d-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="c767d-171">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-171">Member</span></span> | <span data-ttu-id="c767d-172">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="c767d-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-174">Linux</span><span class="sxs-lookup"><span data-stu-id="c767d-174">Linux</span></span> |
| <span data-ttu-id="c767d-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-176">Linux</span><span class="sxs-lookup"><span data-stu-id="c767d-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="c767d-177">macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="c767d-178">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-179">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="c767d-180">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="c767d-181">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="c767d-182">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="c767d-183">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-183">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-185">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-185">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (tylko pobieranie)</span><span class="sxs-lookup"><span data-stu-id="c767d-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="c767d-187">macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-187">macOS</span></span> |
| <span data-ttu-id="c767d-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-189">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="c767d-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="c767d-190">System.IO</span></span>

| <span data-ttu-id="c767d-191">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-191">Member</span></span> | <span data-ttu-id="c767d-192">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-193">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-194">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="c767d-195">System. IO. Pipes</span><span class="sxs-lookup"><span data-stu-id="c767d-195">System.IO.Pipes</span></span>

| <span data-ttu-id="c767d-196">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-196">Member</span></span> | <span data-ttu-id="c767d-197">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="c767d-198">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="c767d-199">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="c767d-200">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="c767d-201">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-201">Linux and macOS</span></span> |
| <span data-ttu-id="c767d-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-203">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="c767d-204">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="c767d-205">System. Media</span><span class="sxs-lookup"><span data-stu-id="c767d-205">System.Media</span></span>

| <span data-ttu-id="c767d-206">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-206">Member</span></span> | <span data-ttu-id="c767d-207">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-208">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="c767d-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="c767d-209">System.Net</span></span>

| <span data-ttu-id="c767d-210">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-210">Member</span></span> | <span data-ttu-id="c767d-211">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="c767d-212">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="c767d-213">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-214">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-215">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-216">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-217">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-218">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-219">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-220">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-221">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-222">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="c767d-223">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-224">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-225">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-226">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-227">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-228">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="c767d-229">System .NET. NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="c767d-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="c767d-230">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-230">Member</span></span> | <span data-ttu-id="c767d-231">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-232">Windows (platformy UWP)</span><span class="sxs-lookup"><span data-stu-id="c767d-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="c767d-233">System .NET. Sockets</span><span class="sxs-lookup"><span data-stu-id="c767d-233">System.Net.Sockets</span></span>

| <span data-ttu-id="c767d-234">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-234">Member</span></span> | <span data-ttu-id="c767d-235">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="c767d-236">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="c767d-237">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="c767d-238">System .NET. WebSockets</span><span class="sxs-lookup"><span data-stu-id="c767d-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="c767d-239">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-239">Member</span></span> | <span data-ttu-id="c767d-240">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="c767d-241">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="c767d-242">System. odbicie</span><span class="sxs-lookup"><span data-stu-id="c767d-242">System.Reflection</span></span>

| <span data-ttu-id="c767d-243">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-243">Member</span></span> | <span data-ttu-id="c767d-244">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-245">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c767d-246">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-247">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c767d-248">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="c767d-249">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-250">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="c767d-251">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="c767d-252">System. Runtime. CompilerServices</span><span class="sxs-lookup"><span data-stu-id="c767d-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="c767d-253">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-253">Member</span></span> | <span data-ttu-id="c767d-254">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="c767d-255">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="c767d-256">System. Runtime. InteropServices</span><span class="sxs-lookup"><span data-stu-id="c767d-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="c767d-257">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-257">Member</span></span> | <span data-ttu-id="c767d-258">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c767d-259">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="c767d-260">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="c767d-261">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="c767d-262">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c767d-263">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="c767d-264">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="c767d-265">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="c767d-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="c767d-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="c767d-267">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-267">Member</span></span> | <span data-ttu-id="c767d-268">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="c767d-269">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="c767d-270">System. Security</span><span class="sxs-lookup"><span data-stu-id="c767d-270">System.Security</span></span>

| <span data-ttu-id="c767d-271">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-271">Member</span></span> | <span data-ttu-id="c767d-272">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="c767d-273">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="c767d-274">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="c767d-275">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="c767d-276">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="c767d-277">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="c767d-278">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="c767d-279">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="c767d-280">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="c767d-281">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="c767d-282">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="c767d-283">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="c767d-284">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="c767d-285">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="c767d-286">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="c767d-287">System. Security. Claims</span><span class="sxs-lookup"><span data-stu-id="c767d-287">System.Security.Claims</span></span>

| <span data-ttu-id="c767d-288">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-288">Member</span></span> | <span data-ttu-id="c767d-289">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-290">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-291">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="c767d-292">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-293">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-294">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="c767d-295">System. Security. Cryptography</span><span class="sxs-lookup"><span data-stu-id="c767d-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="c767d-296">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-296">Member</span></span> | <span data-ttu-id="c767d-297">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c767d-298">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="c767d-299">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="c767d-300">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="c767d-301">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="c767d-302">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="c767d-303">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="c767d-304">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="c767d-305">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="c767d-306">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="c767d-307">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="c767d-308">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="c767d-309">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="c767d-310">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="c767d-311">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c767d-312">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="c767d-313">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c767d-314">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-315">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-316">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-317">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c767d-318">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c767d-319">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-320">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-321">Linux i macOS</span><span class="sxs-lookup"><span data-stu-id="c767d-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-322">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-323">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="c767d-324">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="c767d-325">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="c767d-326">System. Security. Cryptography. PKCS</span><span class="sxs-lookup"><span data-stu-id="c767d-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="c767d-327">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-327">Member</span></span> | <span data-ttu-id="c767d-328">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="c767d-329">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="c767d-330">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-330">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="c767d-331">System. Security. Cryptography. x509</span><span class="sxs-lookup"><span data-stu-id="c767d-331">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="c767d-332">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-332">Member</span></span> | <span data-ttu-id="c767d-333">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-333">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-334">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-334">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-335">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-336">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-336">All</span></span> |
| <span data-ttu-id="c767d-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (tylko ustaw)</span><span class="sxs-lookup"><span data-stu-id="c767d-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="c767d-338">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-338">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="c767d-339">System. Security. Authentication. Kiedy</span><span class="sxs-lookup"><span data-stu-id="c767d-339">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="c767d-340">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-340">Member</span></span> | <span data-ttu-id="c767d-341">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-341">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-342">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-342">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="c767d-343">System. Security. Policy</span><span class="sxs-lookup"><span data-stu-id="c767d-343">System.Security.Policy</span></span>

| <span data-ttu-id="c767d-344">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-344">Member</span></span> | <span data-ttu-id="c767d-345">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-345">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-346">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-346">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="c767d-347">System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="c767d-347">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="c767d-348">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-348">Member</span></span> | <span data-ttu-id="c767d-349">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-349">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="c767d-350">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-350">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="c767d-351">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="c767d-351">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="c767d-352">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-352">Member</span></span> | <span data-ttu-id="c767d-353">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-353">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-354">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-354">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="c767d-355">System. Threading</span><span class="sxs-lookup"><span data-stu-id="c767d-355">System.Threading</span></span>

| <span data-ttu-id="c767d-356">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-356">Member</span></span> | <span data-ttu-id="c767d-357">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-357">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-358">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-358">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="c767d-359">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-359">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="c767d-360">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-360">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="c767d-361">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-361">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="c767d-362">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-362">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="c767d-363">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-363">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="c767d-364">System.Xml</span><span class="sxs-lookup"><span data-stu-id="c767d-364">System.Xml</span></span>

| <span data-ttu-id="c767d-365">Członek</span><span class="sxs-lookup"><span data-stu-id="c767d-365">Member</span></span> | <span data-ttu-id="c767d-366">Platformy, które generują</span><span class="sxs-lookup"><span data-stu-id="c767d-366">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="c767d-367">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-367">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="c767d-368">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="c767d-369">Wszystko</span><span class="sxs-lookup"><span data-stu-id="c767d-369">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="c767d-370">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c767d-370">See also</span></span>

- [<span data-ttu-id="c767d-371">Istotne zmiany dotyczące migracji z .NET Framework do platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="c767d-371">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="c767d-372">Serializacja binarna w programie .NET Core</span><span class="sxs-lookup"><span data-stu-id="c767d-372">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="c767d-373">Analizator przenośności platformy .NET</span><span class="sxs-lookup"><span data-stu-id="c767d-373">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
