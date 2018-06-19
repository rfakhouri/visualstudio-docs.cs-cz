---
title: Možnosti, textový editor, JavaScript, IntelliSense
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Intellisense.References
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Intellisense.General
ms.assetid: b4a9816d-cf87-4dc6-a8d4-1591d6a48103
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 962d185232fc8a98343ed97fa4dd0230d55f5bb7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948805"
---
# <a name="options-text-editor-javascript-intellisense"></a>Možnosti, textový editor, JavaScript, IntelliSense
Použití **IntelliSense** stránky **možnosti** dialogové okno Upravit nastavení, které ovlivňují chování IntelliSense pro jazyk JavaScript. Dostanete **IntelliSense** stránky tak, že zvolíte **nástroje**, **možnosti** na řádku nabídek a pak se zvětšující **textového editoru**,  **JavaScript**, **IntelliSense.**

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

**IntelliSense** stránky obsahuje následující části:

## <a name="validation"></a>Ověřování
 Pomocí těchto možností můžete nastavit předvolby toho, jak editor kódu JavaScript validuje syntaxi v dokumentu.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Zobrazit chyby syntaxe**

 Pokud toto políčko není zaškrtnuto, nezobrazuje editor kódu JavaScript žádné chyby syntaxe. To je užitečné, pokud pracujete s kódem, který jste nenapsali a nehodláte opravovat chyby syntaxe.

 Když toto políčko zaškrtnuto, máte možnost vybrat **zobrazit chyby jako upozornění** zaškrtávací políčko.

 **Zobrazit chyby jako upozornění**

 Je-li toto políčko zaškrtnuto, zobrazují se chyby kódu JavaScript jako upozornění a nikoli jako chyby v seznamu chyb.

 **Stažení vzdálené odkazy (např. http://) pro soubory v projektu ostatní soubory**

 Pokud je toto políčko zaškrtnuto a soubor s kódem JavaScript je otevřen mimo kontext projektu, stáhne Visual Studio vzdálené soubory jazyka JavaScript odkazované v tomto souboru za účelem získání informací technologie IntelliSense. Při výběru této možnosti se soubory stáhnou, pokud je vložíte jako referenci do souboru s kódem JavaScript.

> [!NOTE]
> Pro webové projekty jsou ve výchozím nastavení vzdálené soubory, na které váš projekt odkazuje, staženy automaticky.


## <a name="statement-completion"></a>Doplňování výrazů
 Tyto možnosti slouží ke změně chování při doplňování výrazů technologie IntelliSense.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Pouze, použijte kartu nebo zadejte potvrzení**

 Je-li toto políčko zaškrtnuto, doplňuje editor kódu JavaScript příkazy položkami vybranými v seznamu doplňování až po stisknutí klávesy Tab nebo Enter. Pokud není zaškrtnuto, mohou se příkazy doplňovat vybranými položkami také při použití jiných znaků, jako je tečka, čárka, dvojtečka, levá závorka a levá složená závorka ({).

## <a name="references"></a>Odkazy
 Pomocí těchto možností lze určit typy souborů .js technologie IntelliSense, které jsou v oboru pro různé typy projektů jazyka JavaScript. Reference IntelliSense se zpravidla používají k zajištění podpory IntelliSense pro globální objekty. Tato stránka navíc umožňuje nastavit pořadí načítání skriptů, které musejí být načteny při spuštění, a přidat soubory s rozšířením IntelliSense.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Odkazové skupiny**

 Tato možnost určuje typ referenční skupiny. Jsou podporovány tři referenční skupiny:

 Pomocí předdefinovaných referenčních skupin můžete určit, že konkrétní soubory .js technologie IntelliSense jsou v oboru pro různé projekty jazyka JavaScript. K dispozici jsou čtyři referenční skupiny:

-   Implicitní (Windows *verze*), pro [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] aplikací pomocí jazyka JavaScript. Soubory zahrnuti do této skupiny jsou v oboru pro každý soubor .js otevřen v editoru kódu pro pro [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] aplikací pomocí jazyka JavaScript.

-   Implicitní (web) pro projekty HTML5. Soubory zahrnuté v této skupině jsou v oboru pro každý soubor .js otevřený v editoru kódu pro tyto typy projektů.

-   Referenční skupiny vyhrazeného pracovníka, pro HTML5 Web Workers. Soubory zahrnuté v této skupině jsou v oboru pro každý soubor .js, který má explicitní odkaz na referenční skupinu vyhrazeného pracovníka.

-   Obecné, pro ostatní typy projektů jazyka JavaScript.

**Zahrnuté soubory**

Tato možnost určuje pořadí, v jakém se soubory načítají do kontextu jazykové služby. Můžete nakonfigurovat pořadí pomocí **odebrat**, **nahoru**, a **přesunout dolů** tlačítka. Aby technologie IntelliSense správně fungovala, musí se po určení souboru načíst soubor, který je na něm závislý.

> [!CAUTION]
> Pokud je objekt definován nepodmíněně ve dvou nebo více implicitních odkazech, použije se k definování tohoto objektu poslední odkaz v tomto seznamu.


**Přidat odkaz na skupinu**

Tato možnost poskytuje způsob, jak přidat další soubory .js technologie IntelliSense vyhledáním příslušných souborů.

## <a name="see-also"></a>Viz také

- [JavaScript IntelliSense](../../ide/javascript-intellisense.md)