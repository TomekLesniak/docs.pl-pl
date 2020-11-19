---
title: Publikowanie aplikacji konsolowej .NET przy użyciu programu Visual Studio
description: Dowiedz się, jak za pomocą programu Visual Studio utworzyć zestaw plików, które są konieczne do uruchomienia aplikacji platformy .NET.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: b0c6bd85ddf86f0eb11c56f01abb74a7e9786363
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916032"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio"></a><span data-ttu-id="b6a89-103">Samouczek: publikowanie aplikacji konsolowej .NET przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6a89-103">Tutorial: Publish a .NET console application using Visual Studio</span></span>

<span data-ttu-id="b6a89-104">W tym samouczku pokazano, jak opublikować aplikację konsolową, tak aby inni użytkownicy mogli ją uruchomić.</span><span class="sxs-lookup"><span data-stu-id="b6a89-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="b6a89-105">Publikowanie tworzy zestaw plików, które są konieczne do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b6a89-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="b6a89-106">Aby wdrożyć pliki, skopiuj je na maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="b6a89-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b6a89-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b6a89-107">Prerequisites</span></span>

- <span data-ttu-id="b6a89-108">Ten samouczek współpracuje z aplikacją konsolową utworzoną w temacie [Tworzenie aplikacji konsolowej platformy .NET przy użyciu programu Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b6a89-108">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="b6a89-109">Publikowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="b6a89-109">Publish the app</span></span>

1. <span data-ttu-id="b6a89-110">Uruchom program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6a89-110">Start Visual Studio.</span></span>

1. <span data-ttu-id="b6a89-111">Otwórz projekt *HelloWorld* , który został utworzony w temacie [Tworzenie aplikacji konsolowej platformy .NET przy użyciu programu Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b6a89-111">Open the *HelloWorld* project that you created in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

1. <span data-ttu-id="b6a89-112">Upewnij się, że program Visual Studio używa konfiguracji kompilacji wydania.</span><span class="sxs-lookup"><span data-stu-id="b6a89-112">Make sure that Visual Studio is using the Release build configuration.</span></span> <span data-ttu-id="b6a89-113">W razie potrzeby zmień ustawienie konfiguracji kompilacji na pasku narzędzi z **Debuguj** na **Release**.</span><span class="sxs-lookup"><span data-stu-id="b6a89-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Program Visual Studio Toolbar z wybraną kompilacją wydania":::

1. <span data-ttu-id="b6a89-115">Kliknij prawym przyciskiem myszy projekt **HelloWorld** (nie rozwiązanie HelloWorld) i wybierz polecenie **Publikuj** z menu.</span><span class="sxs-lookup"><span data-stu-id="b6a89-115">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-context-menu.png" alt-text="Menu kontekstowe publikacji programu Visual Studio":::

1. <span data-ttu-id="b6a89-117">Na karcie **Target** strony **Publikowanie** wybierz pozycję **folder**, a następnie wybierz pozycję **dalej**.</span><span class="sxs-lookup"><span data-stu-id="b6a89-117">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/pick-publish-target.png" alt-text="Wybieranie elementu docelowego publikowania w programie Visual Studio":::

1. <span data-ttu-id="b6a89-119">Na karcie **określony cel** strony **Publikowanie** wybierz pozycję **folder**, a następnie wybierz pozycję **dalej**.</span><span class="sxs-lookup"><span data-stu-id="b6a89-119">On the **Specific Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/pick-specific-publish-target.png" alt-text="Wybieranie określonego docelowego publikowania w programie Visual Studio":::

1. <span data-ttu-id="b6a89-121">Na karcie **Lokalizacja** strony **Publikowanie** wybierz pozycję **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="b6a89-121">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-page-loc-tab.png" alt-text="Karta Lokalizacja strony publikacji programu Visual Studio":::

1. <span data-ttu-id="b6a89-123">Na karcie **Publikowanie** okna **Publikowanie** wybierz pozycję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="b6a89-123">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-page.png" alt-text="Okno publikowania programu Visual Studio":::

## <a name="inspect-the-files"></a><span data-ttu-id="b6a89-125">Inspekcja plików</span><span class="sxs-lookup"><span data-stu-id="b6a89-125">Inspect the files</span></span>

<span data-ttu-id="b6a89-126">Domyślnie proces publikowania tworzy wdrożenie zależne od platformy, które jest typem wdrożenia, w którym jest uruchomiona opublikowana aplikacja na komputerze z zainstalowanym środowiskiem uruchomieniowym platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="b6a89-126">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET runtime installed.</span></span> <span data-ttu-id="b6a89-127">Użytkownicy mogą uruchamiać opublikowaną aplikację przez dwukrotne kliknięcie pliku wykonywalnego lub wydawanie `dotnet HelloWorld.dll` polecenia z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="b6a89-127">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="b6a89-128">W poniższych krokach zawarto Podgląd plików utworzonych przez proces publikowania.</span><span class="sxs-lookup"><span data-stu-id="b6a89-128">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="b6a89-129">W **Eksplorator rozwiązań** wybierz opcję **Pokaż wszystkie pliki**.</span><span class="sxs-lookup"><span data-stu-id="b6a89-129">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="b6a89-130">W folderze projektu rozwiń węzeł *bin/Release/NET 5.0/Publikuj*.</span><span class="sxs-lookup"><span data-stu-id="b6a89-130">In the project folder, expand *bin/Release/net5.0/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Eksplorator rozwiązań wyświetlania opublikowanych plików":::

   <span data-ttu-id="b6a89-132">W miarę wyświetlania obrazu opublikowane dane wyjściowe zawierają następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="b6a89-132">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="b6a89-133">*HelloWorld.deps.jsna*</span><span class="sxs-lookup"><span data-stu-id="b6a89-133">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="b6a89-134">Jest to plik zależności środowiska uruchomieniowego aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b6a89-134">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="b6a89-135">Definiuje składniki platformy .NET i biblioteki (w tym bibliotekę dołączaną dynamicznie, która zawiera aplikację) potrzebną do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b6a89-135">It defines the .NET components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="b6a89-136">Aby uzyskać więcej informacji, zobacz [pliki konfiguracji środowiska uruchomieniowego](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="b6a89-136">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="b6a89-137">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="b6a89-137">*HelloWorld.dll*</span></span>

      <span data-ttu-id="b6a89-138">Jest to [zależna od platformy wersja wdrożenia](../deploying/deploy-with-cli.md#framework-dependent-deployment) aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b6a89-138">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="b6a89-139">Aby wykonać tę bibliotekę dołączaną dynamicznie, wprowadź `dotnet HelloWorld.dll` w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="b6a89-139">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="b6a89-140">Ta metoda uruchamiania aplikacji działa na dowolnej platformie, na której zainstalowano środowisko uruchomieniowe platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="b6a89-140">This method of running the app works on any platform that has the .NET runtime installed.</span></span>

   * <span data-ttu-id="b6a89-141">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="b6a89-141">*HelloWorld.exe*</span></span>

      <span data-ttu-id="b6a89-142">Jest to [zależna od struktury wersja pliku wykonywalnego](../deploying/deploy-with-cli.md#framework-dependent-executable) aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b6a89-142">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="b6a89-143">Aby uruchomić tę opcję, wprowadź `HelloWorld.exe` w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="b6a89-143">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="b6a89-144">Plik działa w systemie operacyjnym.</span><span class="sxs-lookup"><span data-stu-id="b6a89-144">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="b6a89-145">*HelloWorld. pdb* (opcjonalnie dla wdrożenia)</span><span class="sxs-lookup"><span data-stu-id="b6a89-145">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="b6a89-146">Jest to plik symboli debugowania.</span><span class="sxs-lookup"><span data-stu-id="b6a89-146">This is the debug symbols file.</span></span> <span data-ttu-id="b6a89-147">Nie musisz wdrażać tego pliku wraz z aplikacją, chociaż należy je zapisać w zdarzeniu, które trzeba debugować opublikowaną wersję aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b6a89-147">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="b6a89-148">*HelloWorld.runtimeconfig.jsna*</span><span class="sxs-lookup"><span data-stu-id="b6a89-148">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="b6a89-149">To jest plik konfiguracji czasu wykonywania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b6a89-149">This is the application's run-time configuration file.</span></span> <span data-ttu-id="b6a89-150">Identyfikuje wersję platformy .NET, w której aplikacja została skompilowana.</span><span class="sxs-lookup"><span data-stu-id="b6a89-150">It identifies the version of .NET that your application was built to run on.</span></span> <span data-ttu-id="b6a89-151">Możesz również dodać do niej opcje konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="b6a89-151">You can also add configuration options to it.</span></span> <span data-ttu-id="b6a89-152">Aby uzyskać więcej informacji, zobacz [Ustawienia konfiguracji środowiska uruchomieniowego .NET](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="b6a89-152">For more information, see [.NET run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="b6a89-153">Uruchom opublikowaną aplikację</span><span class="sxs-lookup"><span data-stu-id="b6a89-153">Run the published app</span></span>

1. <span data-ttu-id="b6a89-154">W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy folder *Publikowanie* , a następnie wybierz polecenie **Kopiuj pełną ścieżkę**.</span><span class="sxs-lookup"><span data-stu-id="b6a89-154">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="b6a89-155">Otwórz wiersz polecenia i przejdź do folderu *Publikowanie* .</span><span class="sxs-lookup"><span data-stu-id="b6a89-155">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="b6a89-156">W tym celu wprowadź, `cd` a następnie wklej pełną ścieżkę.</span><span class="sxs-lookup"><span data-stu-id="b6a89-156">To do that, enter `cd` and then paste the full path.</span></span> <span data-ttu-id="b6a89-157">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b6a89-157">For example:</span></span>

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="b6a89-158">Uruchom aplikację przy użyciu pliku wykonywalnego:</span><span class="sxs-lookup"><span data-stu-id="b6a89-158">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="b6a89-159">Wprowadź `HelloWorld.exe` i naciśnij klawisz <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="b6a89-159">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="b6a89-160">Wprowadź nazwę w odpowiedzi na monit, a następnie naciśnij dowolny klawisz, aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="b6a89-160">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="b6a89-161">Uruchom aplikację za pomocą `dotnet` polecenia:</span><span class="sxs-lookup"><span data-stu-id="b6a89-161">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="b6a89-162">Wprowadź `dotnet HelloWorld.dll` i naciśnij klawisz <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="b6a89-162">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="b6a89-163">Wprowadź nazwę w odpowiedzi na monit, a następnie naciśnij dowolny klawisz, aby wyjść.</span><span class="sxs-lookup"><span data-stu-id="b6a89-163">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6a89-164">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="b6a89-164">Additional resources</span></span>

- [<span data-ttu-id="b6a89-165">Wdrażanie aplikacji .NET</span><span class="sxs-lookup"><span data-stu-id="b6a89-165">.NET application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="b6a89-166">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="b6a89-166">Next steps</span></span>

<span data-ttu-id="b6a89-167">W tym samouczku opublikowano aplikację konsolową.</span><span class="sxs-lookup"><span data-stu-id="b6a89-167">In this tutorial, you published a console app.</span></span> <span data-ttu-id="b6a89-168">W następnym samouczku utworzysz bibliotekę klas.</span><span class="sxs-lookup"><span data-stu-id="b6a89-168">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6a89-169">Tworzenie biblioteki klas .NET przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6a89-169">Create a .NET class library using Visual Studio</span></span>](library-with-visual-studio.md)
