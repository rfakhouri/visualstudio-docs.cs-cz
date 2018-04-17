---
title: Možnosti, textový Editor, všechny jazyky, karty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.ResJSON.Tabs
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Tabs
- VS.ToolsOptionsPages.Text_Editor.All_Languages.Tabs
helpviewer_keywords:
- indents, Code Editor
- Code Editor, default behavior
- tabs, setting in Code Editor
- All Languages Text Editor Options dialog box
- editors, Code Editor
- Code Editor, indenting
- Code Editor, tabs
ms.assetid: 7e208e1d-5e3a-4bf7-a27b-4417e3e049c7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ded3c11dc1b367489c2a5ff578557b6fb6f6f401
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="options-text-editor-all-languages-tabs"></a>Možnosti, textový editor, všechny jazyky, karty
Toto dialogové okno umožňuje změnit výchozí chování z editoru kódu. Toto nastavení platí také pro jiné editory založen na editoru kódu, například zobrazení zdroje Návrháře HTML. Pokud chcete zobrazit tyto možnosti, vyberte **možnosti** z **nástroje** nabídky. V rámci **textového editoru** rozbalte složku **všechny jazyky** podsložku a potom zvolte **karty**.  
  
> [!CAUTION]
>  Tato stránka nastaví výchozí možnosti pro všechny jazyky, vývoj. Mějte na paměti, že resetování možnost v tomto dialogovém okně obnovíte možnosti karty ve všech jazycích, ať možnosti jsou zde vybrat. Chcete-li změnit možnosti textového editoru pro právě jeden jazyk, rozbalte název podsložky pro daný jazyk a vyberte jeho stránky možnost.  
  
 Pokud jsou na stránkách karet možnosti pro konkrétní programovací jazyky, pak zpráva "Nastavení odsazení u jednotlivých textových formátů konfliktu mezi sebou" různá nastavení, zobrazí se pro liší **Indenting**možnosti; a pro které se liší se zobrazí zpráva "Karta nastavení pro jednotlivé text formáty jsou v konfliktu s sebou" **kartě** možnosti. Například tato připomenutí se zobrazí, pokud **inteligentní odsazení** je vybraná možnost v jazyce Visual Basic, ale **blokovat odsazení** je vybraná pro Visual C++.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="indenting"></a>Odsazení  
 Žádné  
 Pokud vybraná, nejsou odsazeny nové řádky. Kurzor je umístěn v první sloupec nový řádek.  
  
 Blok  
 Při výběru, jsou automaticky odsazeny nové řádky. Kurzor je umístěna do stejného počátečního bodu jako v předchozím řádku.  
  
 Inteligentní  
 Při výběru, jsou nové řádky umístěny podle kontextu kód, na jiný kód, formátování nastavení a pravidla týkající se technologie IntelliSense pro váš jazyk vývoj. Tato možnost není k dispozici pro všechny jazyky, vývoj.  
  
 Například řádky uzavřena mezi žádná levá složená závorka ({}) a pravé složené závorce (}) může být automaticky odsazeny navíc zarážku od pozice zarovnaných složených závorek.  
  
## <a name="tabs"></a>Karty  
 Velikost tabulátoru  
 Nastaví vzdálenost v mezery mezi karta zastaví. Výchozí hodnota je čtyři prostory.  
  
 Velikost odsazení  
 Nastaví velikost v prostorech automatického odsazení. Výchozí hodnota je čtyři prostory. K vyplnění zadaná velikost se vloží tabulátory, znaky nebo obojí.  
  
 Vložení mezer  
 Pokud vybraná, operace odsazení vloží pouze znaky, není karta znaků. Pokud **velikost odsazení** nastavena na 5, například pak pět znaků místa jsou vloženy vždy, když stiskněte klávesu tabulátor nebo **zvětšit odsazení** na tlačítko **formátování** panel nástrojů.  
  
 Zachovat tabulátory  
 Pokud vybraná, operace odsazení vloží tolik znaků karta míře. Každý znak TABULÁTORU vyplní počet mezer zadaný v **Velikost tabulátoru**. Pokud **velikost odsazení** není i násobkem **Velikost tabulátoru**, místo znaky jsou přidány do vyplnění rozdílu.  
  
## <a name="see-also"></a>Viz také  
 [Možnosti, textový Editor, všechny jazyky](../../ide/reference/options-text-editor-all-languages.md)   
 [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)