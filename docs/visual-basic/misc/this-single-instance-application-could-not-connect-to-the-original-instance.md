---
title: Ta aplikacja z jednym wystąpieniem nie może nawiązać połączenia z oryginalnym wystąpieniem
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 8e2caa158c3874d216671979430a03b11bf60066
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095684"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Ta aplikacja z jednym wystąpieniem nie może nawiązać połączenia z oryginalnym wystąpieniem

Ta aplikacja pojedynczego wystąpienia nie może nawiązać połączenia z oryginalnym wystąpieniem. Poniżej przedstawiono niektóre możliwe przyczyny tego problemu:  
  
- Oryginalne wystąpienie przestało odpowiadać.  
  
- Aplikacja nie ma uprawnień do tworzenia obiektów jądra. Aby uzyskać więcej informacji na temat obiektów jądra, zobacz [muteksy](../../standard/threading/mutexes.md).  
  
     Nazwa podstawowa obiektów jądra pochodzi z łączenia identyfikatora GUID zestawu, głównego numeru wersji i pomocniczego numeru wersji. Przykładowo może to być nazwa podstawowa `3639f15d-9547-43da-8145-60da347829915.1` .  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>Aby poprawić ten błąd podczas tworzenia aplikacji  
  
1. Sprawdź, czy aplikacja nie przechodzi w stan braku odpowiedzi.  
  
2. Sprawdź, czy aplikacja ma wystarczające uprawnienia do tworzenia obiektów jądra.  
  
3. Uruchom ponownie oryginalne wystąpienie aplikacji.  
  
4. Uruchom ponownie komputer, aby wyczyścić każdy proces, który może korzystać z zasobu, który jest wymagany do nawiązania połączenia z aplikacją oryginalnego wystąpienia.  
  
5. Zanotuj sytuacje, w których wystąpił błąd, i telefoniczne usługi pomocy technicznej firmy Microsoft.  
  
## <a name="see-also"></a>Zobacz także

- [Podstawowe informacje o debugerze](/visualstudio/debugger/debugger-feature-tour)
