---
title: Jak zainstalować obsługę procesora GPU w konstruktorze modelu
description: Dowiedz się, jak zainstalować obsługę procesora GPU w konstruktorze modelu
ms.date: 08/18/2020
author: luisquintanilla
ms.author: luquinta
ms.topic: how-to
ms.openlocfilehash: ce629efa4c12a69f87196de35ebfe4331dc0800f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608569"
---
# <a name="how-to-install-gpu-support-in-model-builder"></a><span data-ttu-id="2ba41-103">Jak zainstalować obsługę procesora GPU w konstruktorze modelu</span><span class="sxs-lookup"><span data-stu-id="2ba41-103">How to install GPU support in Model Builder</span></span>

<span data-ttu-id="2ba41-104">Dowiedz się, jak zainstalować sterowniki procesora GPU, aby użyć procesora GPU z konstruktorem modelu.</span><span class="sxs-lookup"><span data-stu-id="2ba41-104">Learn how to install the GPU drivers to use your GPU with Model Builder.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ba41-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2ba41-105">Prerequisites</span></span>

- <span data-ttu-id="2ba41-106">Rozszerzenie programu Visual Studio w programie model Builder.</span><span class="sxs-lookup"><span data-stu-id="2ba41-106">Model Builder Visual Studio extension.</span></span> <span data-ttu-id="2ba41-107">Rozszerzenie jest wbudowane w program Visual Studio w wersji 16.6.1.</span><span class="sxs-lookup"><span data-stu-id="2ba41-107">The extension is built into Visual Studio as of version 16.6.1.</span></span>
- <span data-ttu-id="2ba41-108">[Rozszerzenie obsługi procesora GPU programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).</span><span class="sxs-lookup"><span data-stu-id="2ba41-108">[Model Builder Visual Studio GPU support extension](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).</span></span>
- <span data-ttu-id="2ba41-109">Co najmniej jeden procesor GPU zgodny z CUDA.</span><span class="sxs-lookup"><span data-stu-id="2ba41-109">At least one CUDA compatible GPU.</span></span> <span data-ttu-id="2ba41-110">Aby zapoznać się z listą zgodnych procesorów GPU, zobacz [Podręcznik firmy NVIDIA](https://developer.nvidia.com/cuda-gpus).</span><span class="sxs-lookup"><span data-stu-id="2ba41-110">For a list of compatible GPUs, see [NVIDIA's guide](https://developer.nvidia.com/cuda-gpus).</span></span>
- <span data-ttu-id="2ba41-111">Konto dewelopera NVIDIA.</span><span class="sxs-lookup"><span data-stu-id="2ba41-111">NVIDIA developer account.</span></span> <span data-ttu-id="2ba41-112">Jeśli jej nie masz, [utwórz bezpłatne konto](https://developer.nvidia.com/developer-program).</span><span class="sxs-lookup"><span data-stu-id="2ba41-112">If you don't have one, [create a free account](https://developer.nvidia.com/developer-program).</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="2ba41-113">Instalowanie zależności</span><span class="sxs-lookup"><span data-stu-id="2ba41-113">Install dependencies</span></span>

1. <span data-ttu-id="2ba41-114">Zainstaluj program [cuda v 10.0](https://developer.nvidia.com/cuda-10.0-download-archive).</span><span class="sxs-lookup"><span data-stu-id="2ba41-114">Install [CUDA v10.0](https://developer.nvidia.com/cuda-10.0-download-archive).</span></span> <span data-ttu-id="2ba41-115">Upewnij się, że zainstalowano program CUDA v 10.0, a nie inną nowszą wersję.</span><span class="sxs-lookup"><span data-stu-id="2ba41-115">Make sure you install CUDA v10.0, not any other newer version.</span></span> <span data-ttu-id="2ba41-116">Nie można mieć zainstalowanych wielu wersji CUDA.</span><span class="sxs-lookup"><span data-stu-id="2ba41-116">You cannot have multiple versions of CUDA installed.</span></span>
1. <span data-ttu-id="2ba41-117">Zainstaluj [cuDNN v 7.6.4 dla CUDA 10,0](https://developer.nvidia.com/rdp/cudnn-download).</span><span class="sxs-lookup"><span data-stu-id="2ba41-117">Install [cuDNN v7.6.4 for CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download).</span></span> <span data-ttu-id="2ba41-118">Nie można mieć zainstalowanych wielu wersji cuDNN.</span><span class="sxs-lookup"><span data-stu-id="2ba41-118">You cannot have multiple versions of cuDNN installed.</span></span> <span data-ttu-id="2ba41-119">Po pobraniu pliku zip cuDNN v 7.6.4 i rozpakowaniu go, skopiuj `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` do `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin` .</span><span class="sxs-lookup"><span data-stu-id="2ba41-119">After downloading cuDNN v7.6.4 zip file and unpacking it, copy `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` to `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2ba41-120">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="2ba41-120">Troubleshooting</span></span>

<span data-ttu-id="2ba41-121">**Jak mogę wiesz, co mam GPU?**</span><span class="sxs-lookup"><span data-stu-id="2ba41-121">**How do I know what GPU I have?**</span></span>

<span data-ttu-id="2ba41-122">Postępuj zgodnie z podanymi instrukcjami:</span><span class="sxs-lookup"><span data-stu-id="2ba41-122">Follow instructions provided:</span></span>

1. <span data-ttu-id="2ba41-123">Kliknij prawym przyciskiem myszy na pulpicie</span><span class="sxs-lookup"><span data-stu-id="2ba41-123">Right-click on desktop</span></span>
1. <span data-ttu-id="2ba41-124">Jeśli w oknie podręcznym zostanie wyświetlony komunikat "Panel sterowania NVIDIA" lub "NVIDIA Display", masz procesor NVIDIA GPU</span><span class="sxs-lookup"><span data-stu-id="2ba41-124">If you see "NVIDIA Control Panel" or "NVIDIA Display" in the pop-up window, you have an NVIDIA GPU</span></span>
1. <span data-ttu-id="2ba41-125">Kliknij "Panel sterowania NVIDIA" lub "NVIDIA Display" w oknie podręcznym</span><span class="sxs-lookup"><span data-stu-id="2ba41-125">Click on "NVIDIA Control Panel" or "NVIDIA Display" in the pop-up window</span></span>
1. <span data-ttu-id="2ba41-126">Spójrz na "informacje o karcie graficznej"</span><span class="sxs-lookup"><span data-stu-id="2ba41-126">Look at "Graphics Card Information"</span></span>
1. <span data-ttu-id="2ba41-127">Zostanie wyświetlona nazwa procesora GPU NVIDIA</span><span class="sxs-lookup"><span data-stu-id="2ba41-127">You will see the name of your NVIDIA GPU</span></span>

<span data-ttu-id="2ba41-128">**Nie widzę panelu sterowania NVIDIA (lub nie można go otworzyć), ale wiem, że mam procesor GPU firmy NVIDIA.**</span><span class="sxs-lookup"><span data-stu-id="2ba41-128">**I don't see NVIDIA Control Panel (or it fails to open) but I know I have an NVIDIA GPU.**</span></span>

1. <span data-ttu-id="2ba41-129">Otwórz Menedżera urządzeń</span><span class="sxs-lookup"><span data-stu-id="2ba41-129">Open Device Manager</span></span>
1. <span data-ttu-id="2ba41-130">Przyjrzyj się kartom wyświetlania</span><span class="sxs-lookup"><span data-stu-id="2ba41-130">Look at Display adapters</span></span>
1. <span data-ttu-id="2ba41-131">Zainstaluj odpowiedni [Sterownik](https://www.nvidia.com/drivers) dla procesora GPU.</span><span class="sxs-lookup"><span data-stu-id="2ba41-131">Install appropriate [driver](https://www.nvidia.com/drivers) for your GPU.</span></span>
