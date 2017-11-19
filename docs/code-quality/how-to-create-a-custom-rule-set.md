---
title: "Postupy: vytvoření vlastní sady pravidel | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.addremoverulesets
helpviewer_keywords: Development Edition, rule sets
ms.assetid: bcc42508-9592-4802-9f66-a50111641d73
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7e9cba33565af81a76d043a3fc3f63eef831e1ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-custom-rule-set"></a>Postupy: Vytvoření vlastní sady pravidel
V [!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)], [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)], a [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)], můžete vytvořit a upravit vlastní *sadu pravidel* podle potřeb konkrétní projekt přidružené analýza kódu. Chcete-li vytvořit vlastní pravidlo nastavit, otevřete ho nebo více standardní pravidlo nastaví v editoru sadu pravidel. Potom můžete přidat nebo odebrat konkrétní pravidla a akce, která nastane, když analýza kódu určuje, že došlo k porušení pravidlo můžete změnit.  
  
 Chcete-li vytvořit nové vlastní pravidlo nastavte, ukládáte ji pomocí nový název souboru. Sadu vlastních pravidel se automaticky přiřadí do projektu.  
  
## <a name="opening-the-rule-set-editor"></a>Otevírání pravidlo s editorem sad  
  
#### <a name="to-open-an-empty-rule-set-file-in-the-rule-set-editor"></a>Otevřete prázdnou pravidlo nastavené souboru v editoru sadu pravidel  
  
1.  Na **soubor** nabídky [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], přejděte na příkaz **nový** a pak klikněte na **soubor**.  
  
2.  V **nový soubor** dialogové okno, klikněte na tlačítko **Obecné** v **nainstalovaných šablonách** seznamu a pak vyberte **sady pravidel analýzy kódu**.  
  
3.  Zobrazí se editor sadu pravidel. Žádná pravidla jsou vybrány v seznamu editor.  
  
#### <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Chcete-li vytvořit vlastní pravidlo z jednoho existující sady pravidel  
  
1.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt a potom vyberte **vlastnosti**.  
  
2.  Na **vlastnosti** , klikněte na **analýza kódu**.  
  
3.  V **pravidlo nastavené** rozevíracího seznamu, proveďte jednu z následujících akcí:  
  
    -   Vyberte sadu pravidel, který chcete přizpůsobit.  
  
     \-nebo –  
  
    -   Vyberte  **\<Procházet... >** k určení nastavení existující pravidlo, které se nenachází v seznamu.  
  
4.  Klikněte na tlačítko **otevřete** zobrazíte pravidla v editoru sadu pravidel.  
  
#### <a name="to-create-a-custom-rule-set-from-multiple-existing-rule-sets"></a>Chcete-li vytvořit vlastní pravidlo nastavte z více sad existující pravidlo  
  
1.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt a potom vyberte **vlastnosti**.  
  
2.  Na **vlastnosti** , klikněte na **analýza kódu**.  
  
3.  Vyberte  **\<zvolte více pravidlo nastaví... >** z **spuštění této sady pravidel**.  
  
4.  V **přidat nebo odebrat pravidlo nastaví** dialogové okno, vyberte pravidlo nastaví na který chcete základní vaší nové sady pravidel a pak klikněte na **OK**.  
  
5.  Uložte novou sadu pravidel.  
  
     Název nové sady pravidel je vybrána v **spuštění této sady pravidel** seznamu. Můžete změnit zobrazovaný název pravidla nastavit v dalším kroku.  
  
6.  (Volitelné) Chcete změnit zobrazovaný název sadu pravidel, na **zobrazení** nabídky, klikněte na tlačítko **vlastnosti – okno**. Zadejte název zobrazení **název** pole.  
  
7.  Pokud chcete přidat, odebrat, nebo upravit pravidel analýzy konkrétního kódu v sadě nové pravidel, klikněte na **otevřete**.  
  
## <a name="modifying-a-rule-set"></a>Úprava sady pravidel  
  
#### <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Chcete-li upravit pravidlo nastavte v editoru sadu pravidel  
  
-   Chcete změnit zobrazovaný název sadu pravidel, na **zobrazení** nabídky, klikněte na tlačítko **vlastnosti – okno**. Zadejte zobrazovaný název v **název** pole. Všimněte si, že zobrazovaný název se může lišit od názvu souboru.  
  
-   Pokud chcete přidat do vlastní sady pravidel všechna pravidla skupiny, zaškrtněte políčko skupiny. Chcete-li odebrat všechna pravidla skupiny, zrušte zaškrtnutí políčka.  
  
-   Chcete-li přidat konkrétní pravidlo do sady vlastní pravidlo, zaškrtněte políčko pravidla. Chcete-li odebrat pravidlo ze sady pravidel, zrušte zaškrtnutí políčka.  
  
-   Chcete-li změnit akce při porušení pravidlo v analýza kódu, klikněte na tlačítko v **akce** pole pro pravidlo a pak vyberte jednu z následujících hodnot:  
  
     **Upozornit** – vygeneruje upozornění.  
  
     **Chyba** -, vygeneruje se chyba.  
  
     **Žádný** – zakáže pravidlo. Tato akce je stejná jako odebrání pravidlo ze sady pravidel.  
  
## <a name="changing-the-rule-set-editor-display"></a>Změna pravidla nastavit editor zobrazení  
  
#### <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Chcete-li skupinu, filtrovat nebo změňte pole v editoru sadu pravidla pomocí pravidla nastavte panelu nástrojů editoru  
  
-   Rozšířit pravidla ve všech skupinách, klikněte na tlačítko **Rozbalit vše**.  
  
-   Sbalit pravidla v všechny skupiny, klepněte na **sbalit všechny**.  
  
-   Chcete-li změnit pravidla se seskupují podle pole, vyberte pole ze seznamu **Group By** seznamu. Chcete-li zobrazit neseskupení pravidla, vyberte  **\<žádné >**.  
  
-   Chcete-li přidat nebo odebrat pole ve sloupcích pravidlo, klikněte na tlačítko **sloupec možnosti**.  
  
-   Chcete-li skrýt pravidla, která se nevztahují k aktuálnímu řešení **skrýt pravidla, která se nevztahují k aktuálnímu řešení**.  
  
-   Chcete-li přepnout mezi zobrazení a skrytí pravidla, které jsou přiřazeny akce chyby, klikněte na tlačítko **zobrazit pravidla, která může způsobit chyby analýzy kódu**.  
  
-   Chcete-li přepnout mezi zobrazení a skrytí pravidla, které jsou přiřazeny akce upozornění, klikněte na tlačítko **zobrazit pravidla, která může generovat upozornění analýzy kódu**.  
  
-   Pro přepínání zobrazení a skrytí pravidla, které jsou přiřazeny **žádné** akce, klikněte na tlačítko **zobrazit pravidla, která nejsou povolené**.  
  
-   Chcete-li přidat nebo odebrat Microsoft výchozí pravidlo nastaví aktuální sady pravidel, klikněte na tlačítko **přidat nebo odebrat sady pravidel podřízené**.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)   
 [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/code-analysis-rule-set-reference.md)