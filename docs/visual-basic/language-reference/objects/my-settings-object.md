---
title: My.Settings — Obiekt
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: f3348e9eea5bdd7f4fd911150877c9aefdd66bcc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867296"
---
# <a name="mysettings-object"></a><span data-ttu-id="753a7-102">My.Settings — Obiekt</span><span class="sxs-lookup"><span data-stu-id="753a7-102">My.Settings Object</span></span>

<span data-ttu-id="753a7-103">Zawiera właściwości i metody uzyskiwania dostępu do ustawień aplikacji.</span><span class="sxs-lookup"><span data-stu-id="753a7-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="753a7-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="753a7-104">Remarks</span></span>  

 <span data-ttu-id="753a7-105">`My.Settings`Obiekt zapewnia dostęp do ustawień aplikacji i umożliwia dynamiczne przechowywanie i pobieranie ustawień właściwości oraz innych informacji dotyczących aplikacji.</span><span class="sxs-lookup"><span data-stu-id="753a7-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="753a7-106">Aby uzyskać więcej informacji, zobacz [Zarządzanie ustawieniami aplikacji (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="753a7-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="753a7-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="753a7-107">Properties</span></span>  

 <span data-ttu-id="753a7-108">Właściwości `My.Settings` obiektu zapewniają dostęp do ustawień aplikacji.</span><span class="sxs-lookup"><span data-stu-id="753a7-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="753a7-109">Aby dodać lub usunąć ustawienia, użyj **projektanta ustawień**.</span><span class="sxs-lookup"><span data-stu-id="753a7-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="753a7-110">Każde ustawienie ma **nazwę**, **typ**, **zakres**i **wartość**, a te ustawienia określają, jak Właściwość uzyskiwania dostępu do każdego ustawienia pojawia się w `My.Settings` obiekcie:</span><span class="sxs-lookup"><span data-stu-id="753a7-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="753a7-111">**Nazwa** określa nazwę właściwości.</span><span class="sxs-lookup"><span data-stu-id="753a7-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="753a7-112">**Typ** określa typ właściwości.</span><span class="sxs-lookup"><span data-stu-id="753a7-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="753a7-113">**Zakres** wskazuje, czy właściwość jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="753a7-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="753a7-114">Jeśli wartość jest **aplikacją**, właściwość jest tylko do odczytu; Jeśli wartość to **User**, właściwość jest do odczytu i zapisu.</span><span class="sxs-lookup"><span data-stu-id="753a7-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="753a7-115">**Wartość** jest wartością domyślną właściwości.</span><span class="sxs-lookup"><span data-stu-id="753a7-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="753a7-116">Metody</span><span class="sxs-lookup"><span data-stu-id="753a7-116">Methods</span></span>  
  
|<span data-ttu-id="753a7-117">Metoda</span><span class="sxs-lookup"><span data-stu-id="753a7-117">Method</span></span>|<span data-ttu-id="753a7-118">Opis</span><span class="sxs-lookup"><span data-stu-id="753a7-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="753a7-119">Ponownie ładuje ustawienia użytkownika z ostatnich zapisanych wartości.</span><span class="sxs-lookup"><span data-stu-id="753a7-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="753a7-120">Zapisuje bieżące ustawienia użytkownika.</span><span class="sxs-lookup"><span data-stu-id="753a7-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="753a7-121">`My.Settings`Obiekt zawiera również zaawansowane właściwości i metody dziedziczone z <xref:System.Configuration.ApplicationSettingsBase> klasy.</span><span class="sxs-lookup"><span data-stu-id="753a7-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="753a7-122">Zadania</span><span class="sxs-lookup"><span data-stu-id="753a7-122">Tasks</span></span>  

 <span data-ttu-id="753a7-123">W poniższej tabeli przedstawiono przykłady zadań związanych z `My.Settings` obiektem.</span><span class="sxs-lookup"><span data-stu-id="753a7-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="753a7-124">Działanie</span><span class="sxs-lookup"><span data-stu-id="753a7-124">To</span></span>|<span data-ttu-id="753a7-125">Zobacz</span><span class="sxs-lookup"><span data-stu-id="753a7-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="753a7-126">Odczytaj ustawienie aplikacji</span><span class="sxs-lookup"><span data-stu-id="753a7-126">Read an application setting</span></span>|[<span data-ttu-id="753a7-127">Porady: odczytywanie ustawień aplikacji w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="753a7-127">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="753a7-128">Zmiana ustawienia użytkownika</span><span class="sxs-lookup"><span data-stu-id="753a7-128">Change a user setting</span></span>|[<span data-ttu-id="753a7-129">Porady: zmienianie ustawień użytkownika w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="753a7-129">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="753a7-130">Utrwalanie ustawień użytkownika</span><span class="sxs-lookup"><span data-stu-id="753a7-130">Persist user settings</span></span>|[<span data-ttu-id="753a7-131">Porady: utrwalanie ustawień użytkownika w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="753a7-131">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="753a7-132">Tworzenie siatki właściwości dla ustawień użytkownika</span><span class="sxs-lookup"><span data-stu-id="753a7-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="753a7-133">Porady: tworzenie siatek właściwości dla ustawień użytkownika w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="753a7-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="753a7-134">Przykład</span><span class="sxs-lookup"><span data-stu-id="753a7-134">Example</span></span>  

 <span data-ttu-id="753a7-135">Ten przykład wyświetla wartość `Nickname` Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="753a7-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="753a7-136">Aby ten przykład działał, aplikacja musi mieć `Nickname` ustawienie typu `String` .</span><span class="sxs-lookup"><span data-stu-id="753a7-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753a7-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="753a7-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="753a7-138">Porady: odczytywanie ustawień aplikacji w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="753a7-138">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="753a7-139">Porady: zmienianie ustawień użytkownika w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="753a7-139">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="753a7-140">Porady: utrwalanie ustawień użytkownika w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="753a7-140">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="753a7-141">Porady: tworzenie siatek właściwości dla ustawień użytkownika w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="753a7-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="753a7-142">Zarządzanie ustawieniami aplikacji (.NET)</span><span class="sxs-lookup"><span data-stu-id="753a7-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
