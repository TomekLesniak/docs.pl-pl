---
title: Kroki przepływu pracy DevOps w zewnętrznej pętli dla aplikacji platformy Docker
description: Cykl życia konteneryzowanych aplikacji platformy Docker korzystających z platformy i narzędzi firmy Microsoft
ms.date: 08/06/2020
ms.openlocfilehash: 1a973407d59484899f99fb6e326b8d7c8e97079b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915218"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="abc2e-103">Tworzenie potoków ciągłej integracji/ciągłego wdrażania w Azure DevOps Services dla aplikacji .NET Core w kontenerach i wdrażanie ich w klastrze Kubernetes</span><span class="sxs-lookup"><span data-stu-id="abc2e-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="abc2e-104">Na rysunku 5-12 można zobaczyć kompleksowy scenariusz DevOps obejmujący Zarządzanie kodem, kompilację kodu, kompilację obrazów platformy Docker, wypychanie obrazów Docker do rejestru platformy Docker, a wreszcie Wdrożenie klastra Kubernetes na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="abc2e-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![Przepływ pracy: uruchamiany na komputerze deweloperskim.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="abc2e-107">**Rysunek 5-12**.</span><span class="sxs-lookup"><span data-stu-id="abc2e-107">**Figure 5-12**.</span></span> <span data-ttu-id="abc2e-108">Scenariusz ciągłej integracji/ciągłego tworzenia obrazów platformy Docker i wdrażania ich w klastrze Kubernetes na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="abc2e-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="abc2e-109">Należy zaznaczyć, że dwa potoki, kompilacja/CI i wersja/dysk CD są połączone za pomocą rejestru platformy Docker (takiego jak usługa Docker Hub lub Azure Container Registry).</span><span class="sxs-lookup"><span data-stu-id="abc2e-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="abc2e-110">Rejestr platformy Docker jest jedną z głównych różnic w porównaniu do tradycyjnego procesu ciągłej integracji/ciągłego wdrażania bez platformy Docker.</span><span class="sxs-lookup"><span data-stu-id="abc2e-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="abc2e-111">Jak pokazano na rysunku 5-13, Pierwsza faza to potok kompilacji/elementu konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="abc2e-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="abc2e-112">W Azure DevOps Services można tworzyć potoki kompilacji/CI, które będą kompilować kod, tworzyć obrazy platformy Docker i wypchnąć je do rejestru Docker, takiego jak Docker Hub lub Azure Container Registry.</span><span class="sxs-lookup"><span data-stu-id="abc2e-112">In Azure DevOps Services you can create build/CI pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Widok przeglądarki Azure DevOps, definicja zadania procesu kompilacji.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="abc2e-114">**Rysunek 5-13**.</span><span class="sxs-lookup"><span data-stu-id="abc2e-114">**Figure 5-13**.</span></span> <span data-ttu-id="abc2e-115">Potok kompilacji/elementu konfiguracji w usłudze Azure DevOps tworzenie obrazów platformy Docker i wypychanie obrazów do rejestru platformy Docker</span><span class="sxs-lookup"><span data-stu-id="abc2e-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="abc2e-116">Drugim etapem jest utworzenie potoku wdrożenia/wydania.</span><span class="sxs-lookup"><span data-stu-id="abc2e-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="abc2e-117">W Azure DevOps Services można łatwo utworzyć potok wdrożenia przeznaczony dla klastra Kubernetes za pomocą Kubernetes zadań dla Azure DevOps Services, jak pokazano na rysunku 5-14.</span><span class="sxs-lookup"><span data-stu-id="abc2e-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Widok przeglądarki Azure DevOps, wdrażanie do Kubernetes definicji zadań.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="abc2e-119">**Rysunek 5-14**.</span><span class="sxs-lookup"><span data-stu-id="abc2e-119">**Figure 5-14**.</span></span> <span data-ttu-id="abc2e-120">Potok wydania/CD w Azure DevOps Services wdrożenia w klastrze Kubernetes</span><span class="sxs-lookup"><span data-stu-id="abc2e-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> <span data-ttu-id="abc2e-121">[! Przewodnik] wdrażanie eShopModernized do Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="abc2e-121">[!Walkthrough] Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="abc2e-122">Aby zapoznać się ze szczegółowymi wskazówkami dotyczącymi potoków ciągłej integracji/ciągłego wdrażania w usłudze Azure DevOps, zobacz ten wpis: </span><span class="sxs-lookup"><span data-stu-id="abc2e-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: </span></span>\
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="abc2e-123">[Poprzedni](docker-application-outer-loop-devops-workflow.md) 
> [Dalej](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="abc2e-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
