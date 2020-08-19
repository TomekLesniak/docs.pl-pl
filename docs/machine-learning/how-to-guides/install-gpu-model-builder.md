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
# <a name="how-to-install-gpu-support-in-model-builder"></a>Jak zainstalować obsługę procesora GPU w konstruktorze modelu

Dowiedz się, jak zainstalować sterowniki procesora GPU, aby użyć procesora GPU z konstruktorem modelu.

## <a name="prerequisites"></a>Wymagania wstępne

- Rozszerzenie programu Visual Studio w programie model Builder. Rozszerzenie jest wbudowane w program Visual Studio w wersji 16.6.1.
- [Rozszerzenie obsługi procesora GPU programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).
- Co najmniej jeden procesor GPU zgodny z CUDA. Aby zapoznać się z listą zgodnych procesorów GPU, zobacz [Podręcznik firmy NVIDIA](https://developer.nvidia.com/cuda-gpus).
- Konto dewelopera NVIDIA. Jeśli jej nie masz, [utwórz bezpłatne konto](https://developer.nvidia.com/developer-program).

## <a name="install-dependencies"></a>Instalowanie zależności

1. Zainstaluj program [cuda v 10.0](https://developer.nvidia.com/cuda-10.0-download-archive). Upewnij się, że zainstalowano program CUDA v 10.0, a nie inną nowszą wersję. Nie można mieć zainstalowanych wielu wersji CUDA.
1. Zainstaluj [cuDNN v 7.6.4 dla CUDA 10,0](https://developer.nvidia.com/rdp/cudnn-download). Nie można mieć zainstalowanych wielu wersji cuDNN. Po pobraniu pliku zip cuDNN v 7.6.4 i rozpakowaniu go, skopiuj `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` do `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin` .

## <a name="troubleshooting"></a>Rozwiązywanie problemów

**Jak mogę wiesz, co mam GPU?**

Postępuj zgodnie z podanymi instrukcjami:

1. Kliknij prawym przyciskiem myszy na pulpicie
1. Jeśli w oknie podręcznym zostanie wyświetlony komunikat "Panel sterowania NVIDIA" lub "NVIDIA Display", masz procesor NVIDIA GPU
1. Kliknij "Panel sterowania NVIDIA" lub "NVIDIA Display" w oknie podręcznym
1. Spójrz na "informacje o karcie graficznej"
1. Zostanie wyświetlona nazwa procesora GPU NVIDIA

**Nie widzę panelu sterowania NVIDIA (lub nie można go otworzyć), ale wiem, że mam procesor GPU firmy NVIDIA.**

1. Otwórz Menedżera urządzeń
1. Przyjrzyj się kartom wyświetlania
1. Zainstaluj odpowiedni [Sterownik](https://www.nvidia.com/drivers) dla procesora GPU.
