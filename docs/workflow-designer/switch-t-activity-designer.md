---
title: "Přepínač&lt;T&gt; Návrhář aktivity | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.ModelItemKeyValuePair.UI
- System.Activities.Statements.Switch`1.UI
ms.assetid: 18a6c96e-49a9-4356-ab61-fbd7e3ab44bb
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 51d3a29e16409dff09d7ed50f4dbfa14f8ce9505
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="switchlttgt-activity-designer"></a>Přepínač&lt;T&gt; Návrhář aktivity
<xref:System.Activities.Statements.Switch%601> Aktivita vyhodnotí zadaný výraz a provádí aktivity z kolekce aktivit, jejichž přidružené klíč odpovídá hodnotě získané z vyhodnocení.

 **Přepínač < T\>**  Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Switch%601> aktivity v Návrháři pracovních postupů Windows.

## <a name="the-switchtactivity"></a>Přepínač\<T > aktivity
 A <xref:System.Activities.Statements.Switch%601> obsahuje aktivitu <xref:System.Activities.Statements.Switch%601.Expression%2A> a slovník <xref:System.Activities.Statements.Switch%601.Cases%2A>. Každý případ ve slovníku tvořený dvojicí, který obsahuje *klíč* a aktivitu, která slouží jako jeho odpovídající *hodnotu*. <xref:System.Activities.Statements.Switch%601> Vyhodnotí aktivity <xref:System.Activities.Statements.Switch%601.Expression%2A> a porovná je s všechny klíče. Pokud je nalezena shoda, bude odpovídající aktivita se spustí. Pouze jeden výsledek je možné, protože klíče slovníku musí být jedinečné v závislosti na typu rovnosti definované procedury rovnosti slovníku. Pokud není nalezena žádná shoda, <xref:System.Activities.Statements.Switch%601.Default%2A> je aktivita spuštěna.

## <a name="how-to-use-the-switcht-activity-designer"></a>Jak používat přepínač\<T > Návrhář aktivity
 **Přepínač\<T >** Návrhář aktivity naleznete v **tok řízení** kategorii **sada nástrojů**, což je dostat kliknutím **Sada nástrojů** na kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.) Po vyřazení ji do [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], se zobrazí **vyberte typy** dialogové okno, aby mohl uživatel zadat obecného typu *T* použít v <xref:System.Activities.Statements.Switch%601> aktivity. Výchozí hodnota je **Int32**. Jednou obecného typu *T* byla vybrána, **přepínač < T\>**  designer je přidán do návrháře pracovních postupů.

 Toto jsou vlastnosti **přepínač < T\>**  designer. Všechny tyto vlastnosti se dá upravit v tabulce vlastností. Některé z nich můžete upravovat také na plochu návrháře.

 V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.Switch%601> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.Switch%601> Návrhář aktivity. Výchozí hodnota je přepínač < Int32\>. Hodnotu lze upravit v **vlastnosti** okno nebo přímo v hlavičce návrháře.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.Switch%601.Expression%2A>|True|Určuje výraz použit k porovnání s klíči v kolekci případů k určení takovém případě provést.|
|<xref:System.Activities.Statements.Switch%601.Default%2A>||Určuje aktivity provést, pokud není nalezena žádná shoda. Klikněte na tlačítko **přidat aktivitu** tlačítko v návrháři otevřít **výchozí** pole, kde může být přetažen aktivity.|
|<xref:System.Activities.Statements.Switch%601.Cases%2A>||Určuje případů k vyhodnocení. Chcete-li přidat případu, klikněte na tlačítko **přidat nového případu** tlačítko v dolní části **přepínač\<T >** designer. Tlačítko se změní na textové pole (Pokud obecného typu vybrali při přidávání přepínač pole se seznamem\<T > je řetězec nebo výčtu). Po přidání klíče v **případ hodnota** pole rozšíří oblasti případu a aktivity můžete vyřadit, kde text nápovědy "Zde rozevírací aktivita" k definování logiku spouštění pro případ.|

 Několik případů lze přidat, dokud se neduplikují case klíče. Dialogové okno chyby, jinak hodnota zobrazí vytváření sestav, že již existuje zadaný klíč případu a že je nutné vybrat jiný klíč. V **přepínač\<T >** návrháře, může být pouze jeden případu oblasti v rozšířené zobrazení najednou. Pokud malá oblasti v sbaleným zobrazením, kliknutím na tlačítko oblasti případu rozšíří ho. Všimněte si, že pro sbalené případě návrháře zobrazuje zobrazovaný název aktivity v případě na pravé straně Pokud neexistuje žádné. Jinak se zobrazí **přidat aktivitu** tlačítko, které rozšíří případě, pokud kliknete na tlačítko a umožňuje přidat aktivitu.

 Kliknutím na klíč existující případ změní klíč z štítek do textové pole tak, aby můžete upravit klíč případu.

 Chcete-li odstranit případu 2 způsoby:

1.  Vyberte tento případ a odstraňte ji.

2.  Vyberte případu, klikněte pravým tlačítkem a zobrazení v místní nabídce vyberte **odstranit**.

 Všimněte si, že je nutné vybrat samotného odstranit případu. Vyberete a odstraníte aktivity v případě odstraní pouze aktivity tak není.

## <a name="see-also"></a>Viz také

- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)