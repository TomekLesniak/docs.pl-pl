---
title: Zagadnienia dotyczące zabezpieczeń zestawów
description: Podczas kompilowania zestawu .NET można określić uprawnienia wymagane przez zestaw do uruchomienia. W tym artykule omówiono zestawy o silnych nazwach i narzędzia podpisywania.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], security
- signcodes
- names [.NET], assemblies
- strong-named assemblies, security considerations
- signing assemblies
- assemblies [.NET], signing
- granting permissions, assemblies
- assemblies [.NET], strong-named
- names [.NET], strong names
- permissions [.NET], assemblies
- security [.NET], assemblies
- integrity with assemblies
ms.assetid: 1b5439c1-f3d5-4529-bd69-01814703d067
ms.openlocfilehash: 91ea206abf80da275651854b9f13aa0116b7a1c5
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687260"
---
# <a name="assembly-security-considerations"></a>Zagadnienia dotyczące zabezpieczeń zestawów

Podczas kompilowania zestawu można określić zestaw uprawnień wymaganych do uruchomienia zestawu. To, czy określone uprawnienia są przyznane do zestawu, czy nie, zależy od dowodów.  
  
 Istnieją dwa wyraźnie różniące się sposoby używania dowodów:  
  
- Dowód wejściowy jest scalany z dowodami zebranymi przez moduł ładujący w celu utworzenia ostatecznego zestawu dowodów stosowanego do rozpoznawania zasad. Metody używające tej semantyki obejmują **Assembly. Load** , **Assembly. LoadFrom** i **aktywator. CreateInstance** .  
  
- Dowód wejściowy jest używany w niezmienionej formie jako ostateczny zestaw dowodów stosowanych do rozpoznawania zasad. Metody używające tej semantyki obejmują **zestaw. Load (Byte [])** i **AppDomain. DefineDynamicAssembly ()** .  
  
  Uprawnienia opcjonalne mogą być przyznawane [zasadom zabezpieczeń](../../framework/misc/code-access-security-basics.md) ustawionym na komputerze, na którym zostanie uruchomiony zestaw. Jeśli kod ma obsługiwać wszystkie potencjalne wyjątki zabezpieczeń, można wykonać jedną z następujących czynności:  
  
- Wstawić żądania o uprawnienia dla wszystkich uprawnień, których wymaga kod, oraz obsługiwać z wyprzedzeniem niepowodzenia w czasie ładowania, które występują w razie nieprzyznania uprawnień.  
  
- W celu uzyskania uprawnień wymaganych przez kod nie używać żądań o uprawnienia, ale przygotować się na obsługę wyjątków zabezpieczeń w razie nieprzyznania uprawnień.  
  
  > [!NOTE]
  > Zabezpieczenia to skomplikowana dziedzina, w której istnieje wiele opcji do wyboru. Aby uzyskać więcej informacji, zobacz podstawowe [pojęcia dotyczące zabezpieczeń](../security/key-security-concepts.md).  
  
 Podczas ładowania dowód zestawu jest wykorzystywany jako dane wejściowe dla zasad zabezpieczeń. Zasady zabezpieczeń są ustalane przez przedsiębiorstwo i administratora komputera, a także przez ustawienia zasad użytkownika. Określają one zestaw uprawnień przydzielanych całemu zarządzanemu kodowi podczas wykonywania. Zasady zabezpieczeń można ustanowić dla wydawcy zestawu (jeśli ma on podpis wygenerowany przez narzędzie do podpisywania), dla witryny internetowej i strefy (w znaczeniu używanym w programie Internet Explorer), z której zestaw został pobrany, lub dla silnej nazwy zestawu. Na przykład administrator komputera może ustanowić zasady zabezpieczeń, które pozwalają, aby kod pobrany z witryny internetowej i podpisany przez producenta danego oprogramowania miał dostęp do bazy danych na komputerze, ale nie przyznają dostępu umożliwiającego zapis na dysku komputera.  
  
## <a name="strong-named-assemblies-and-signing-tools"></a>Zestawy o silnych nazwach i narzędzia podpisywania  

 > [!WARNING]
 > Nie należy polegać na silnych nazwach zabezpieczeń. Zapewniają one tylko unikatową tożsamość.

 Zestaw można podpisać na dwa różne, ale uzupełniające sposoby: za pomocą silnej nazwy lub przy użyciu  [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md). Podpisywanie zestawu o silnej nazwie dodaje szyfrowanie klucza publicznego do pliku zawierającego manifest zestawu. Podpisywanie za pomocą silnej nazwy pomaga zweryfikować unikatowość nazwy, zapobiec podszywaniu się pod nazwę oraz dostarczyć obiektom wywołującym jakąś tożsamość podczas rozpoznawania odwołań.  
  
 Żaden poziom zaufania nie jest skojarzony z silną nazwą, co sprawia, że [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md) ważne. Te dwa narzędzia podpisywania wymagają, aby wydawca potwierdził swoją tożsamość wobec zewnętrznego urzędu i uzyskał certyfikat. Certyfikat jest następnie osadzany w pliku i na jego podstawie administrator może decydować, czy ufa autentyczności kodu.  
  
 Można utworzyć silną nazwę i podpis cyfrowy utworzony przy użyciu [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md) do zestawu lub użyć dowolnego z nich. Oba narzędzia podpisywania mogą podpisywać tylko jeden plik jednocześnie. W przypadku zestawu wieloplikowego podpisuje się plik zawierający manifest zestawu. Silna nazwa jest przechowywana w pliku zawierającym manifest zestawu, ale sygnatura utworzona przy użyciu [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md) jest przechowywana w zastrzeżonym miejscu w przenośnym pliku wykonywalnym (PE) zawierającym manifest zestawu. Podpisywanie zestawu przy użyciu [SignTool.exe (narzędzia podpisywania)](../../framework/tools/signtool-exe.md) może być używane (z silną nazwą lub bez niej), gdy istnieje już Hierarchia zaufania, która opiera się na wygenerowanych sygnaturach [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md) lub gdy zasady korzystają tylko z części klucza i nie sprawdzają łańcucha zaufania.  
  
> [!NOTE]
> Jeśli do zestawu ma być stosowana silna nazwa i podpis z narzędzia podpisywania, najpierw należy przypisać silną nazwę.  
  
 Środowisko uruchomieniowe języka wspólnego również dokonuje weryfikacji skrótu. Manifest zestawu zawiera listę wszystkich plików tworzących zestaw, a także skrót każdego pliku utworzony podczas kompilowania manifestu. Przy wczytywaniu każdego pliku jego wartość jest skracana i porównywana z wartością skrótu przechowywaną w manifeście. Jeśli skróty różnią się od siebie, zestaw nie jest wczytywany.  
  
 Ponieważ silne nazewnictwo i podpisywanie przy użyciu [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md) gwarantuje integralność, zasady zabezpieczeń dostępu kodu można oprzeć na tych dwóch formach dowodu zestawu. Silne nazewnictwo i podpisywanie przy użyciu [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md) gwarantuje integralność dzięki podpisom cyfrowym i certyfikatom. Wszystkie wymienione technologie — weryfikacja skrótu, silne nazewnictwo i podpisywanie przy użyciu [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md)— współdziałanie, aby upewnić się, że zestaw nie został zmieniony w żaden sposób.  
  
## <a name="see-also"></a>Zobacz także

- [Zestawy o silnych nazwach](strong-named.md)
- [Zestawy w środowisku .NET](index.md)
- [SignTool.exe (Narzędzie podpisywania)](../../framework/tools/signtool-exe.md)
