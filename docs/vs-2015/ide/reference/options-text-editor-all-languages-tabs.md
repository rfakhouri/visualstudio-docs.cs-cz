---
title: Možnosti, textový Editor, všechny jazyky, karty | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
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
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c89154cef2325da8b8073ded264afeb8f765302a
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54800801"
---
# <a name="options-text-editor-all-languages-tabs"></a>Možnosti, textový editor, všechny jazyky, karty
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Toto dialogové okno umožňuje změnit výchozí chování editoru kódu. Tato nastavení platí také pro jiné editory založen na editoru kódu, jako je HTML návrháře zobrazení zdroje. Chcete-li zobrazit tyto možnosti, vyberte **možnosti** z **nástroje** nabídky. V rámci **textový Editor** rozbalte složku **všechny jazyky** podsložku a klikněte na tlačítko **karty**.  
  
> [!CAUTION]
>  Tato stránka nastaví výchozí možnosti pro všechny vývojářské jazyky. Mějte na paměti, že obnovení možnost v tomto dialogovém okně obnovíte možnosti karty ve všech jazycích k jakékoli volby jsou tady vyberete. Chcete-li změnit možnosti textového editoru pro právě jeden jazyk, rozbalte podsložku pro daný jazyk a vyberte jeho možnosti.  
  
 Pokud vyberete různá nastavení na stránkách možností karty pro konkrétní programovací jazyky a pak zprávy "Nastavení odsazení pro jednotlivé textové formáty jsou v konfliktu mezi sebou", zobrazí se pro lišící se **Indenting**možnosti; a zobrazí se zpráva "Nastavení tabulátoru pro jednotlivé textové formáty jsou v konfliktu mezi sebou," pro lišící se **kartu** možnosti. Například toto připomenutí se zobrazí v případě **inteligentní odsazení** vybrána možnost Visual Basic, ale **blokovat odsazení** je vybrán pro Visual C++.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="indenting"></a>Odsazení  
 Žádná  
 Při výběru, nejsou nové řádky odsazeny. Kurzor je umístěn v prvním sloupci nový řádek.  
  
 Blok  
 Při výběru nového řádku mají být automaticky odsazeny. Kurzor je umístěn na stejné počáteční bod na každém řádku.  
  
 Smart  
 Pokud je vybráno, jsou umístěny nové řádky podle kontextu kód za další formátování nastavení a zásady technologie IntelliSense pro vývojový jazyk kódu. Tato možnost není k dispozici pro všechny vývojářské jazyky.  
  
 Například řádků uzavřeny mezi levá složená závorka ({}) a pravou závorkou (}) může být automaticky další zarážku od pozice zarovnané složené závorky odsazeny.  
  
## <a name="tabs"></a>Karty  
 Velikost tabulátoru  
 Nastaví zastaví vzdálenost v mezery mezi kartu. Výchozí hodnota je mezery čtyři.  
  
 Velikost odsazení  
 Nastaví velikost v prostorách Automatické odsazení. Výchozí hodnota je mezery čtyři. Karta znaky a znaky se vloží tak, aby vyplnil zadané velikosti.  
  
 Vložit mezery  
 Pokud je vybráno, operace odsazení vložit pouze znaky mezery, tabulátory není. Pokud **velikost odsazení** je nastavena na 5, například pak pět znaky mezery jsou vloženy pokaždé, když stisknete klávesu TAB nebo **zvětšit odsazení** tlačítko **formátování** panel nástrojů.  
  
 Zachovat tabulátory  
 Pokud je vybráno, operace odsazení vložit tolik znaků TABULÁTORU nejvíce. Každý znak TABULÁTORU vyplní počet mezer podle **Velikost tabulátoru**. Pokud **velikost odsazení** není i násobek **Velikost tabulátoru**, znaky mezery jsou přidány k vyplnění rozdíl.  
  
## <a name="see-also"></a>Viz také  
 [Možnosti, textový Editor, všechny jazyky](../../ide/reference/options-text-editor-all-languages.md)   
 [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)
