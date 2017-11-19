---
title: Okno Seznam chyb | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ErrorList
helpviewer_keywords:
- Task List
- build errors
- Error List window
- errors [Visual Studio], Error List window
ms.assetid: b7f6d45a-733b-4ad8-bc2f-737a37509e56
caps.latest.revision: "32"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d332700fc663375c9fab96d86645b5762e77d851
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="error-list-window"></a>Okno Seznam chyb
> [!NOTE]
>  V seznamu chyb se zobrazí informace o konkrétní chybová zpráva. Chyba číslo nebo řetězec text chyby můžete zkopírovat v okně výstupu. Chcete-li zobrazit ve výstupním okně, stiskněte Ctrl + Alt + O. V tématu [výstup okna](../../ide/reference/output-window.md).  
  
 Můžete vyvíjet aplikace, které jsou rychlejší pomocí **seznam chyb** okno. Například můžete provádět následující úlohy:  
  
-   Zobrazí chyby, upozornění a zprávy vytvořeného při psaní kódu.  
  
-   Najít chyby syntaxe uvedené technologii IntelliSense.  
  
-   Najít chyby nasazení, určité statické analýza chyb a chyb zjištěných při použití šablony organizace zásad.  
  
-   Dvakrát klikněte na všechny položky zpráva Chyba k otevření souboru, kde dojde k problému a přesuňte do umístění chyby.  
  
-   Filtrovat položky, které se zobrazí, a sloupce, které informace se zobrazují pro každou položku.  
  
-   Vyhledání specifických termínů a obor vyhledávání právě aktuálního projektu nebo dokumentu.  
  
Chcete-li zobrazit **seznam chyb**, klikněte na tlačítko **zobrazení / chyba seznamu**, nebo **CTRL +\\+ E**.  
  
Můžete **chyby**, **upozornění**, a **zprávy** karty se můžete podívat různé úrovně informace.  
  
Seřadit seznamu, klikněte na libovolné záhlaví sloupce. Chcete-li znovu seřadit sloupec, podržte stisknutou klávesu SHIFT a klikněte na tlačítko Další záhlaví sloupce. Chcete-li vybrat sloupce, které se zobrazí a které jsou skryté, zvolte **zobrazit sloupce** z místní nabídky. Chcete-li změnit pořadí, ve kterém jsou zobrazeny sloupce, přetáhněte záhlaví všechny sloupce doleva nebo doprava.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte může lišit od těch, které tu popsané, v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, klikněte na tlačítko **nástroje / Import a Export nastavení**. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="error-list-filters"></a>Filtry seznam chyb  
 Existují dva typy filtru v dva rozevírací seznamy, jeden na pravé straně panelu nástrojů a druhý na levém panelu nástrojů. Určuje sadu soubory kódu pro použití rozevíracího seznamu na levé straně panelu nástrojů (**celé řešení**, **otevřené dokumenty**, **aktuálního projektu**,  **Aktuální dokumentu**).  
  
 Můžete omezit rozsah hledání k analýze a fungovat na skupiny chyb. Například můžete chtít zaměřit se na chyby jádra, které brání kompilace projektu. Možnosti oboru:  
  
1.  **Otevřít dokumenty**: Zobrazit chyby, upozornění a zprávy pro otevřené dokumenty.  
  
2.  **Aktuální projekt**: Zobrazit chyby, upozornění a zprávy z aktuálně vybraného dokumentu v projektu **Editor** nebo vybrané projekt v **Průzkumníku řešení**.  
  
    > [!NOTE]
    >  Filtrovaný seznam chyby, upozornění a zprávy se změní, pokud projekt aktuálně vybraný dokument se liší od projekt vybraný v **Průzkumníku řešení**.  
  
3.  **Aktuální dokumentu**: Zobrazit chyby, upozornění a zprávy pro aktuálně vybraný dokument v **Editor** nebo **Průzkumníku řešení**.  
  
Pokud aktuálně filtru na výsledek hledání, název filtru se zobrazí v **seznam chyb** záhlaví. **Chyby**, **upozornění**, a **zprávy** tlačítka následně se zobrazí počet filtrované položek, které se zobrazí spolu s celkový počet položek, které; například zobrazit tlačítka x, y chyb. Pokud je použit žádný filtr, záhlaví říká pouze chyby seznam"".  
  
V seznamu na pravé straně panelu nástrojů Určuje, jestli se má zobrazit chyby ze sestavení (chyby způsobené operace sestavení) nebo z IntelliSense (byly zjištěny chyby před spuštěním sestavení), nebo z obou.  
  
## <a name="search"></a>Hledat  
 Použití **seznam vyhledávání chyb** textového pole na pravé straně **seznam chyb** nástrojů k vyhledání konkrétní chyby v seznamu chyb. Můžete hledat na žádné viditelné sloupce v seznamu chyb a výsledky hledání jsou vždy seřazené podle sloupce, který má prioritu řazení místo v dotazu nebo je použit filtr. Pokud se rozhodnete **Esc** klíče při je zaměření **seznam chyb**, můžete vymazat hledaný termín a filtrování výsledků hledání. Můžete také kliknutím **X** na pravé straně pole a vymazat.  
  
## <a name="save"></a>Uložit  
 Můžete zkopírovat v seznamu chyb a uložte ho do souboru. Vyberte chyby, které chcete kopírovat a klikněte pravým tlačítkem na výběr a potom v místní nabídce vyberte **kopie**. Potom můžete vložit chyby do souboru. Pokud můžete vložit chyby do tabulky aplikace Excel, pole se objeví jako různé sloupce.  
  
## <a name="ui-element-list"></a>Seznam prvků uživatelského rozhraní  
 Závažnost  
 Zobrazuje různé typy **seznam chyb** položka (**chyba**, **zpráva**, **upozornění**, **upozornění (aktivní)**, **Upozornění (neaktivní)**.  
  
 Kód  
 Zobrazí kód chyby.  
  
 Popis  
 Zobrazí text položky.  
  
 Project  
 Zobrazí název aktuálního projektu.  
  
 Soubor  
 Zobrazuje název souboru.  
  
 Řádek  
 Zobrazí řádek, kde k problému dochází.