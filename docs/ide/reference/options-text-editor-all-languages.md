---
title: Možnosti, textový Editor, všechny jazyky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.General
- VS.ToolsOptionsPages.Text_Editor.ResJSON.General
- vs.toolsoptionspages.text_editor.all_languages.scrollbars
helpviewer_keywords:
- Text Editor Options dialog box
- statement completion
- word wrap
- General dialog box
- line numbers
- virtual space
ms.assetid: 49ee7306-9d46-4170-850f-a1716171752d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 762fc7ffbf3ca4dbf8cb768ee96f73cb1f9190aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="options-text-editor-all-languages"></a>Možnosti, textový editor, všechny jazyky
Toto dialogové okno umožňuje změnit výchozí chování z editoru kódu. Toto nastavení platí také pro jiné editory založen na editoru kódu, například zobrazení zdroje Návrháře HTML. Chcete-li otevřít toto dialogové okno, vyberte **možnosti** z **nástroje** nabídky. V rámci **textového editoru** složky, rozbalte **všechny jazyky** podsložky a potom zvolte **Obecné**.  
  
> [!CAUTION]
>  Tato stránka nastaví výchozí možnosti pro všechny jazyky, vývoj. Mějte na paměti, že resetování možnost v tomto dialogovém okně obnovíte Obecné možnosti ve všech jazycích, jsou zde vybrat libovolnou volby. Chcete-li změnit možnosti textového editoru pro právě jeden jazyk, rozbalte název podsložky pro daný jazyk a vyberte jeho stránky možnost.  
  
 Šedým zaškrtnutí se zobrazí, pokud byla vybrána možnost na stránkách Obecné možnosti pro některé programovacích jazyků, ale nikoli pro ostatní uživatele.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="statement-completion"></a>Doplňování výrazů  
 Automatický seznam členů  
 Při výběru, jsou technologii IntelliSense zobrazí automaticky otevírané okno seznam Dostupní členové, vlastnosti, hodnoty nebo metody, jako typ v editoru. Vyberte libovolnou položku ze seznamu místní vložení položky do vašeho kódu. Výběrem této možnosti povolíte **Skrýt rozšířené členy** možnost.  
  
 Skrýt členy rozšířené úrovně  
 Pokud vybraná, zkrátí seznamy dokončení automaticky otevírané okno příkaz zobrazením jen ty položky, které se běžně používají. Další položky jsou filtrovány ze seznamu.  
  
 Informace o parametrech  
 Při výběru, úplnou syntaxi pro aktuální deklaraci nebo proceduru se zobrazí v části kurzoru v editoru, se všemi jeho dostupné parametry. Je parametr další, které jsou zobrazeny tučně.  
  
## <a name="settings"></a>Nastavení  
 Povolit virtuální prostor  
 Pokud je vybraná tato možnost a **zalamování** je zaškrtnutí zrušeno, můžete kliknout na libovolné místo přesahuje za konec řádku v editoru kódu a typ. Tato funkce slouží k umístění komentářů ve stejném místě vedle vašeho kódu.  
  
 Zalamování řádků  
 Při výběru, jakékoli její části řádek, který vodorovně přesahuje zobrazovací oblast editoru se automaticky zobrazí na další řádek. Výběrem této možnosti povolíte **zobrazit vizuální glyfy pro zalamování** možnost.  
  
> [!NOTE]
>  **Virtuální adresní prostor** je zapnuta funkce vypnutém chvíli **zalamování** zapnutý.  
  
 Zobrazit vizuální glyfy pro zalamování řádků  
 Při výběru, vrátí šipku indikátoru se zobrazí, kde je dlouhý řádek zalomen na druhém řádku.  
  
 ![LineBreakSymbol – snímek obrazovky](../../ide/reference/media/linebreak.gif "linebreak")  
  
 Pokud nechcete zobrazit tyto ukazatele, zrušte zaškrtnutí tohoto políčka.  
  
> [!NOTE]
>  Tyto šipky připomenutí nejsou přidány do vašeho kódu a ne k tisku. Jsou pouze pro referenci.  
  
 Používání příkazů Vyjmout nebo zkopírovat pro prázdné řádky, když není výběr  
 Tento parametr nastaví chování editoru při umístěte kurzor na prázdný řádek, vyberte nothing a poté zkopírujte nebo vyjmout.  
  
-   Pokud je vybraná tato možnost, prázdný řádek je zkopírovat nebo vyjmout. Pokud potom vložte nový prázdný řádek vložena.  
  
-   Pokud tato možnost vybrána, odebere příkaz Cut prázdné řádky. Ale uchování dat do schránky. Pokud pak použijete příkaz Vložit, je proto vložit obsah naposledy zkopírován do schránky. Pokud nic byla dříve zkopírovali, nic vložit.  
  
Toto nastavení nemá žádný vliv na kopírování nebo vyjmutí, když řádek není prázdný. Pokud není nic vybráno, je zkopírovat celý řádek nebo vyjmout. Pokud je pak vložíte, jsou vložit text celý řádek a jeho ukončovacího znaku.  
  
> [!TIP]
>  Chcete-li zobrazit ukazatele pro mezery, tabulátory a konce řádku a tedy odlišit odsazené řádky od řádků, které jsou zcela prázdné, vyberte **Upřesnit** z **upravit** nabídky a zvolte **prázdné zobrazení Místo**.  
  
## <a name="display"></a>Displej  
 Čísla řádků  
 Pokud vybraná, číslo řádku se zobrazí vedle každého řádku kódu.  
  
> [!NOTE]
>  Tato čísla řádků nejsou přidány do vašeho kódu a ne k tisku. Jsou pouze pro referenci.  
  
 Povolení navigace URL jedním kliknutím  
 Pokud vybraná, ukazatelem myši změní ukazující ruku při průchodu adresu URL v editoru. Můžete kliknout na adresu URL pro zobrazení stránky označené ve webovém prohlížeči.  
  
 Navigační panel  
 Když vyberete, zobrazí se **navigační panel** v horní části editoru kódu. Jeho rozevírací **objekty** a **členy** seznamy vám umožní vybrat určitý objekt ve vašem kódu, vyberte z jejích členů a přejde na deklaraci vybraného člena v editoru kódu.  
  
## <a name="see-also"></a>Viz také  
 [Možnosti, textový Editor, všechny jazyky, karty](../../ide/reference/options-text-editor-all-languages-tabs.md)   
 [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)   
 [Používání atributu IntelliSense](../../ide/using-intellisense.md)