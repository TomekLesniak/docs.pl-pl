---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: fb317b3c555d151e132122c476ce19bdeceb1321
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065622"
---
# <a name="-main"></a>-main

Określa klasę lub moduł, który zawiera `Sub Main` procedurę.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a>Argumenty  

 `location`  
 Wymagany. Nazwa klasy lub modułu, która zawiera procedurę, która `Sub Main` ma zostać wywołana podczas uruchamiania programu. Może to być w formie **Main: module** lub **-Main: Namespace. module**.  
  
## <a name="remarks"></a>Uwagi  

 Użyj tej opcji, gdy tworzysz plik wykonywalny lub program wykonywalny systemu Windows. Jeśli opcja **-Main** zostanie pominięta, kompilator wyszukuje prawidłowe udostępnianie `Sub Main` we wszystkich publicznych klasach i modułach.  
  
 Zapoznaj się z [główną procedurą w Visual Basic](../../programming-guide/program-structure/main-procedure.md) , aby poznać różne formy `Main` procedury.  
  
 Gdy `location` jest klasą, która dziedziczy z <xref:System.Windows.Forms.Form> , kompilator dostarcza domyślną `Main` procedurę, która uruchamia aplikację, jeśli Klasa nie ma `Main` procedury. Dzięki temu można kompilować kod w wierszu polecenia, który został utworzony w środowisku programistycznym.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Aby ustawić — Main w zintegrowanym środowisku programistycznym programu Visual Studio  
  
1. Zaznaczono projekt w **Eksplorator rozwiązań**. W menu **projekt** kliknij polecenie **Właściwości**.  
  
2. Kliknij kartę **aplikacja** .  
  
3. Upewnij się, że pole wyboru **Włącz platformę aplikacji** nie jest zaznaczone.  
  
4. Zmodyfikuj wartość w polu **obiekt startowy** .  
  
## <a name="example"></a>Przykład  

 Poniższy kod kompiluje `T2.vb` i `T3.vb` , określając, że `Sub Main` procedura zostanie znaleziona w `Test2` klasie.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [-Target (Visual Basic)](target.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
- [Procedura główna w Visual Basic](../../programming-guide/program-structure/main-procedure.md)
