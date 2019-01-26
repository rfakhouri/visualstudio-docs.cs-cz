---
title: Možnosti, textový editor, všechny jazyky
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.General
- VS.ToolsOptionsPages.Text_Editor.ResJSON.General
- VS.ToolsOptionsPages.Text_Editor.All_Languages.General
- VS.ToolsOptionsPages.Text_Editor.Basic.General
- VS.ToolsOptionsPages.Text_Editor.CSharp.General
- VS.ToolsOptionsPages.Text_Editor.C/C++.General
- VS.ToolsOptionsPages.Text_Editor.CoffeeScript.General
- VS.ToolsOptionsPages.Text_Editor.CSS.General
- VS.ToolsOptionsPages.Text_Editor.Dockerfile.General
- VS.ToolsOptionsPages.Text_Editor.F#.General
- VS.ToolsOptionsPages.Text_Editor.Fsharp.General
- VS.ToolsOptionsPages.Text_Editor.HQL.General
- VS.ToolsOptionsPages.Text_Editor.HTML.General
- VS.ToolsOptionsPages.Text_Editor.HTML_(Web_Forms).General
- VS.ToolsOptionsPages.Text_Editor.JavaScript.General
- VS.ToolsOptionsPages.Text_Editor.TypeScript.General
- VS.ToolsOptionsPages.Text_Editor.JSON.General
- VS.ToolsOptionsPages.Text_Editor.LESS.General
- VS.ToolsOptionsPages.Text_Editor.Plain_Text.General
- VS.ToolsOptionsPages.Text_Editor.SCSS.General
- VS.TOOLSOPTIONSPAGES.TEXT_EDITOR.SQL_SERVER_TOOLS.GENERAL
- VS.ToolsOptionsPages.Text_Editor.StreamAnalytics.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL90.General
- VS.ToolsOptionsPages.Text_Editor.U-SQL.General
- VS.ToolsOptionsPages.Text_Editor.XAML.General
- VS.ToolsOptionsPages.Text_Editor.XML.General
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 36ffcdb1601a3a0402c04a2fa093461e7cf01d6a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960851"
---
# <a name="options-text-editor-all-languages"></a>Možnosti, textový editor, všechny jazyky

Toto dialogové okno umožňuje změnit výchozí chování editoru kódu. Tato nastavení platí také pro jiné editory založen na editoru kódu, jako je HTML návrháře zobrazení zdroje. Chcete-li otevřít toto dialogové okno, vyberte **možnosti** z **nástroje** nabídky. V rámci **textový Editor** složky, rozbalte **všechny jazyky** podsložky a klikněte na tlačítko **Obecné**.

> [!CAUTION]
> Tato stránka nastaví výchozí možnosti pro všechny vývojářské jazyky. Mějte na paměti, že obnovení možnost v tomto dialogovém okně resetuje Obecné možnosti ve všech jazycích na jakékoli volby jsou tady vyberete. Chcete-li změnit možnosti textového editoru pro právě jeden jazyk, rozbalte podsložku pro daný jazyk a vyberte jeho možnosti.

Zatržení šedým se zobrazí, když byla vybrána možnost na stránkách Obecné možnosti pro některé programovací jazyky, ale ne pro ostatní uživatele.

## <a name="statement-completion"></a>Doplňování výrazů

**Automatický seznam členů**

Při výběru rozbalovací seznam dostupných členů, vlastnosti, hodnoty nebo metody se zobrazí v IntelliSense při psaní v editoru. Vyberte libovolnou položku ze seznamu místní nabídky k vložení položky do kódu. Tato volba umožňuje **rýt pokročilé členy** možnost.

**Skrýt členy rozšířené úrovně**

Při výběru, zkrátí seznamy dokončení rozbalovací příkaz tím, že zobrazuje pouze ty položky, které jsou obvykle používány. Další položky jsou filtrovány ze seznamu.

**Informace o parametrech**

Pokud je vybráno, zobrazí se pod kurzor v editoru se všechny její dostupné parametry úplnou syntaxi pro deklaraci aktuální nebo proceduru. Zobrazí se další parametr, který můžete přiřadit tučným písmem.

## <a name="settings"></a>Nastavení

**Povolit virtuální prostor**

Pokud je vybraná tato možnost a **zalamování** je zaškrtnutí zrušeno, můžete kliknout na libovolné místo za koncem řádku v editoru kódu a typu. Tato funkce slouží k umístění komentářů na bod konzistentní vzhledem k vedle vašeho kódu.

**Zalamování řádků**

Pokud je vybráno, jakékoli její části řádek, který rozšiřuje vodorovně nad rámec oblasti Zobrazit editor automaticky zobrazí na dalším řádku. Tato volba umožňuje **brazit piktogramy pro zalamování řádků** možnost.

> [!NOTE]
> **Virtuální prostor** zapnuté funkce chvíli off **zalamování** zapnutý.

**Brazit piktogramy pro zalamování řádků**

Při výběru, zobrazí se ukazatel vrátit šipku kde dlouhý řádek zalamuje na další řádek.

![Snímek obrazovky LineBreakSymbol](../../ide/reference/media/linebreak.gif)

Pokud nechcete zobrazovat tyto indikátory, zrušte zaškrtnutí tohoto políčka.

> [!NOTE]
> Tyto šipky připomenutí nejsou přidány do kódu a ne k tisku. Jsou pouze pro referenci.

**Čísla řádků**

Pokud je vybráno, číslo řádku vedle každého řádku kódu.

> [!NOTE]
> Tato čísla řádků nejsou přidány do kódu a ne k tisku. Jsou pouze pro referenci.

**Povolit navigaci adres URL jedním kliknutím**

Pokud je vybráno, ukazatel myši se změní ukazující ruku během přes adresu URL v editoru. Můžete kliknout na adresu URL pro zobrazení stránky označené ve webovém prohlížeči.

**Navigační panel**

Pokud je vybráno, zobrazí **navigační panel** v horní části stránky editoru kódu. Jeho rozevíracího seznamu **objekty** a **členy** seznamy umožňují vybrat určitý objekt v kódu, vyberte z jejích členů a přejde na deklaraci vybraného členu v editoru kódu.

**Použít příkazů Vyjmout nebo kopírovat na prázdné řádky, pokud nebyla vybrána žádná položka**

Tato možnost nastaví chování editoru, když umístíte kurzor na prázdný řádek, nothing, vyberte a zkopírujte nebo vyjmutí.

-   Pokud je vybraná tato možnost, prázdný řádek zkopíruje nebo vyjmutí. Pokud pak vložíte, je vložen nový, prázdný řádek.

-   Pokud tato možnost vybrána, příkaz Cut odstraní prázdné řádky. Nicméně se zajistilo uchování dat do schránky. Proto pokud použijete příkaz Paste, je vložit obsah naposledy zkopírovaný do schránky. Pokud není nic se zkopírovala dříve, není nic vloženo.

Toto nastavení nemá žádný vliv na kopírování nebo vyjmutí, když řádek není prázdný. Pokud není nic vybráno, celý řádek zkopíruje nebo vyjmutí. Pokud pak vložte text celý řádek a jeho ukončovacího znaku jsou vloženy.

> [!TIP]
> Chcete-li zobrazit ukazatele pro mezery, tabulátory a konce řádků a proto odlišit odsazené řádky z řádků, které jsou zcela prázdný, vyberte **Upřesnit** z **upravit** nabídku a zvolte **prázdné zobrazení Místo**.

## <a name="see-also"></a>Viz také

- [Možnosti, Textový editor, Všechny jazyky, Tabulátory](../../ide/reference/options-text-editor-all-languages-tabs.md)
- [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)
- [Používání atributu IntelliSense](../../ide/using-intellisense.md)