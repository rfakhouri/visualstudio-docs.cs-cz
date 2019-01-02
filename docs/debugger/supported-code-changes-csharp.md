---
title: Podporované změny kódu (C# a Visual Basic) | Dokumentace Microsoftu
ms.date: 10/11/2017
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], supported code changes
- Edit and Continue [Visual Basic], supported code changes
ms.assetid: c7a48ea9-5a7f-4328-a9d7-f0e76fac399d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 865b5c220a410c9b0d744263820a50dd1bb9395a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53878624"
---
# <a name="supported-code-changes-c-and-visual-basic"></a>Podporované změny kódu (C# a Visual Basic)
Upravit a pokračovat zpracovává většinu typů změn kódu uvnitř těla metody. Během ladění, ale nejde použít většinu změn mimo těl metod a několik změn v rámci těla metod. Nepodporované změny použít, musíte Zastavit ladění a znovu s novou verzi kódu.

## <a name="supported-changes-to-code"></a>Podporované změny kódu

Následující tabulka uvádí změny, které mohou být provedeny C# a kód jazyka Visual Basic během relace ladění bez restartování relace.

|Element Language/funkce|Operace podporované úprav|Omezení|
|-|-|-|
|Typy|Přidejte metody, pole, konstruktory, et al.|[Ano](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits)|
|Iterátory|Přidat nebo upravit|Ne|
|Async/await výrazy|Přidat nebo upravit|[Ano](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits)|
|Dynamické objekty|Přidat nebo upravit|Ne|
|výrazy lambda|Přidat nebo upravit|[Ano](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits)|
|LINQ – výrazy|Přidat nebo upravit|[Stejně jako výrazy lambda](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits)|

> [!NOTE]
> Novějších funkcí jazyka, jako je například interpolace řetězců a podmíněné operátory s null jsou obecně podporována možností upravit a pokračovat. Nejnovější informace najdete v tématu [nepodporuje úpravy Enc](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits) stránky.

## <a name="unsupported-changes-to-code"></a>Nepodporované změny kódu
 Následující změny nejde použít u C# a kód jazyka Visual Basic během relace ladění:  
  
-   Změny aktuálního příkazu nebo jiné aktivní příkaz.  
  
     Aktivní příkazy zahrnout všechny příkazy, funkce v zásobníku volání, které byly volány zobrazíte aktuální příkaz.  
  
     Aktuální příkaz je označena žlutým pozadím v okně zdroje. Jiné aktivní příkazy jsou označené nástrojem pozadí označeno šedou barvou a jsou jen pro čtení. Tyto výchozí barvy lze změnit v **možnosti** dialogové okno.

- Následující tabulka uvádí nepodporované změny kódu pomocí prvku jazyka.

|Element Language/funkce|Nepodporované úpravy operace|
|-|-|
|Všechny prvky kódu|Přejmenování|
|Jmenné prostory|Přidejte|
|Obory názvů, typy, členy|Odstranit|
|Obecné typy|Přidat nebo upravit|
|Rozhraní|Upravit|
|Typy|Přidat člena abstraktní nebo virtuální, přidejte přepsání (viz [podrobnosti](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits))|
|Typy|Přidat destruktor|
|Členové|Upravte člen odkazující na vloženém typu spolupráce|
|Členové (Visual Basic)|Upravte člena s On Error nebo Resume – příkaz|
|Členové (Visual Basic)|Upravte člen obsahující klauzuli dotazu agregace, Group By, jednoduché připojení nebo skupiny připojení LINQ|
|Metody|Změna podpisů|
|Metody|Díky přidání těla metody abstraktní metoda stát jako neabstraktní|
|Metody|Odstranění těla metody|
|Atributy|Přidat nebo upravit|
|Vlastnosti nebo události|Upravit parametr typu, základní typ, typ delegáta nebo návratový typ |
|Operátory nebo indexerů|Upravit parametr typu, základní typ, typ delegáta nebo návratový typ |
|catch – bloky|Když obsahuje aktivní příkaz|
|konstrukce try-catch-finally bloky|Když obsahuje aktivní příkaz|
|using – příkazy|Přidejte|
|asynchronní metody nebo výrazy lambda|Upravit asynchronní metody nebo lambda v projekt cílí na rozhraní .NET Framework 4 a snížení (viz [podrobnosti](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits))|
|Iterátory|Upravit iterátor v projekt cílí na rozhraní .NET Framework 4 a snížení (viz [podrobnosti](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits))|
  
## <a name="unsafe-code"></a>Nezabezpečený kód  
 Změny nezabezpečený kód mají stejná omezení jako změny bezpečný kód, jeden další omezení: Upravit a pokračovat nepodporuje změny nebezpečný kód, který ukončí v rámci metody, která obsahuje `stackalloc` operátor.  

## <a name="unsupported-app-scenarios"></a>Scénáře pro nepodporované aplikace

Nepodporované aplikace a platformy obsahují ASP.NET 5, Silverlight 5 a Windows 8.1.

> [!NOTE]
> Aplikace, které jsou podporovány zahrnout UWP ve Windows 10 a x86 a x64 aplikací určených pro rozhraní .NET Framework 4.6 klasické pracovní plochy nebo novější verze (jenom desktopové verze rozhraní .NET Framework je).
  
## <a name="unsupported-scenarios"></a>Nepodporované scénáře  
 Upravit a pokračovat není k dispozici v následujících scénářích ladění:  
  
-   Ladění ve smíšeném režimu (nativní a spravovaná).  
  
-   Ladění SQL.  
  
-   Ladění zotavení po havárii. Watson s výpisem paměti.  
  
-   Ladění aplikace vložený modul runtime.  
  
-   Ladění aplikace s využitím připojit k procesu (**ladit > připojit k procesu**) namísto spuštění aplikace výběrem **Start** z **ladění** nabídky.  
  
-   Ladění optimalizovaného kódu.  
  
-   Ladění starou verzi kódu po nové verze se nepovedlo sestavit kvůli chybám sestavení.
  
## <a name="see-also"></a>Viz také  
 [Upravit a pokračovat (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)   
 [Postupy: Použití operace upravit a pokračovat (C#)](../debugger/how-to-use-edit-and-continue-csharp.md)