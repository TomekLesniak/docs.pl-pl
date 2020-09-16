---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 4b468b8ee4301693312e9545396f2b9f495f75d8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550914"
---
# <a name="-bugreport"></a>-bugreport

Tworzy plik, którego można użyć podczas tworzenia pliku raportu o usterce.

## <a name="syntax"></a>Składnia

```console
-bugreport:file
```

## <a name="arguments"></a>Argumenty

|Termin|Definicja|
|---|---|
|`file`|Wymagany. Nazwa pliku, który będzie zawierać raport o błędach. Nazwa pliku powinna być ujęta w cudzysłów (""), jeśli nazwa zawiera spację.|

## <a name="remarks"></a>Uwagi

Następujące informacje są dodawane do `file` :

- Kopia wszystkich plików kodu źródłowego w kompilacji.

- Lista opcji kompilatora używanych w kompilacji.

- Informacje o wersji dotyczące kompilatora, środowiska uruchomieniowego języka wspólnego i systemu operacyjnego.

- Dane wyjściowe kompilatora, jeśli istnieją.

- Opis problemu, dla którego zostanie wyświetlony monit.

- Opis sposobu, w jaki sądzisz, że problem powinien zostać rozwiązany, dla którego zostanie wyświetlony monit.

Ze względu na to, że kopia wszystkich plików kodu źródłowego jest uwzględniona w programie `file` , można odtworzyć defekt kodu (podejrzane) w najkrótszym możliwym programie.

> [!IMPORTANT]
> `-bugreport`Opcja tworzy plik, który zawiera potencjalnie poufne informacje. Obejmuje to bieżący czas, wersję kompilatora, wersję .NET Framework, wersję systemu operacyjnego, nazwę użytkownika, argumenty wiersza polecenia, za pomocą których kompilator został uruchomiony, wszystkie kod źródłowy oraz binarną postać dowolnego przywoływanego zestawu. Dostęp do tej opcji można uzyskać, określając opcje wiersza polecenia w pliku Web.config dla kompilacji aplikacji ASP.NET po stronie serwera. Aby tego uniknąć, zmodyfikuj plik Machine.config, aby nie zezwalać użytkownikom na kompilowanie na serwerze.

Jeśli ta opcja jest używana z `-errorreport:prompt` , `-errorreport:queue` , lub `-errorreport:send` , a aplikacja napotkała wewnętrzny błąd kompilatora, informacje w programie `file` są wysyłane do firmy Microsoft Corporation. Te informacje ułatwią inżynierom firmy Microsoft Identyfikowanie przyczyny błędu i mogą pomóc w ulepszaniu kolejnej wersji Visual Basic. Domyślnie żadne informacje nie są wysyłane do firmy Microsoft. Jednak podczas kompilowania aplikacji przy użyciu `-errorreport:queue` , która jest domyślnie włączona, aplikacja zbiera raporty o błędach. Po zalogowaniu się administratora komputera w systemie raportowanie błędów zostanie wyświetlone okno podręczne, które umożliwi administratorowi przekazanie do firmy Microsoft wszelkich raportów o błędach, które wystąpiły od momentu zalogowania.

> [!NOTE]
> `-bugreport`Opcja jest niedostępna w środowisku deweloperskim programu Visual Studio. jest ona dostępna tylko podczas kompilowania z wiersza polecenia.

## <a name="example"></a>Przykład

Poniższy przykład kompiluje *T2. vb* i umieszcza wszystkie informacje o raportowaniu błędów w pliku *Problem.txt*.

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [-Debug (Visual Basic)](debug.md)
- [-errorreport](errorreport.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
- [Element trustLevel dla securityPolicy (ASP.NET Schema Settings)](/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
