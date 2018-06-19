---
title: Zadejte vlastních událostí sestavení v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- build events, customizing
ms.assetid: 69e935a5-e208-4bcd-865c-3e5f9b047ca8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c45f439a8bb1ae559e915769f8ea89ef7f4bf863
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945919"
---
# <a name="specify-custom-build-events-in-visual-studio"></a>Zadejte vlastních událostí sestavení v sadě Visual Studio

Určení událostí sestavení vlastní, můžete automaticky spouštět příkazy před zahájením sestavení nebo po jejím dokončení. Například můžete spustit *.bat* soubor před zahájením sestavení nebo zkopírujte nové soubory do složky, po dokončení sestavení. Události sestavení spustit pouze v případě, že sestavení úspěšně dosáhne těchto bodů v procesu sestavení.

 Konkrétní informace o programovací jazyk, který používáte najdete v následujících tématech:

-   Visual Basic –[postup: Zadejte události (Visual Basic) sestavení](../ide/how-to-specify-build-events-visual-basic.md).

-   C# a F # –[postup: Zadejte události (C#) sestavení](../ide/how-to-specify-build-events-csharp.md).

-   Visual C++ –[události sestavení zadejte](/cpp/ide/specifying-build-events).

## <a name="syntax"></a>Syntaxe

Události sestavení použijte stejnou syntaxi jako DOS příkazy, ale makra můžete snadno vytvořit událostí sestavení. Seznam dostupných makra najdete v tématu [dialogové okno Příkazový řádek před sestavením událostí/po sestavení událostí](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

 Nejlepších výsledků dosáhnete postupujte podle těchto tipy formátování:

-   Přidat `call` příkaz před všechny události, které spustit sestavení *.bat* soubory.

     Příklad: `call C:\MyFile.bat`

     Příklad: `call C:\MyFile.bat call C:\MyFile2.bat`

-   Cesty k souborům uzavřete do uvozovek.

     Příklad (pro [!INCLUDE[win8](../debugger/includes/win8_md.md)]): "% ProgramFiles (x86) %\Microsoft SDKs\Windows\v8.0A\Bin\NETFX 4.0 Tools\gacutil.exe"-Pokud "$(TargetPath)"

-   Oddělte více příkazů konce řádků.

-   Podle potřeby použít zástupné znaky.

     Příklad: `for %I in (*.txt *.doc *.html) do copy %I c:\` *mydirectory*`\`

    > [!NOTE]
    >  `%I` ve výše uvedeném kódu by měla být `%%I` v dávkovém skriptu.

## <a name="see-also"></a>Viz také

- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)
- [Dialogové okno Příkazový řádek události/po sestavení události před sestavením](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)
- [Speciální znaky nástroje MSBuild](../msbuild/msbuild-special-characters.md)
- [Návod: Vytvoření aplikace](../ide/walkthrough-building-an-application.md)
