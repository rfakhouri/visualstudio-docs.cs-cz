---
title: "Přechod Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Transition.UI
ms.assetid: f6e8b5cc-7fb8-4699-9703-f3c9fc7cc316
caps.latest.revision: "7"
ms.author: sdanie
manager: erikre
ms.workload: multiple
ms.openlocfilehash: ba933b2eebb7193f8ee93852ce2a047f01ca4e0d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="transition-activity-designer"></a>Návrhář aktivity přechodu
A <xref:System.Activities.Statements.Transition> představuje přechod mezi dvěma stavy.  
  
## <a name="using-the-transition-activity-designer"></a>Pomocí návrháře aktivity přechodu  
 Návrhář aktivity přechod umožňuje nakonfigurovat přechod mezi dvěma stavy.  
  
### <a name="transition-properties-in-the-workflow-designer"></a>Vlastnosti přechodu v Návrháři pracovních postupů  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Transition> vlastnosti, které se dá nastavit pomocí návrháře pracovních postupů a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.Transition.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.Transition> Návrhář aktivity. Výchozí hodnota je **T1**. Hodnota se dá upravit v tabulce vlastností v hlavičce návrháře rozšířené přechod a v záhlaví části akce v Návrháři rozšířené přechodu. <xref:System.Activities.Activity.DisplayName%2A> Se používá v cestě, která se zobrazí v horní části návrháře pracovních postupů.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|  
|<xref:System.Activities.Statements.Transition.Condition%2A>|False|Pokud je k dispozici, určuje výraz, který se musí vyhodnotit **True** před ovládací prvek předává do cílového stavu. Tento stav se dá upravit v tabulce vlastností a v Návrháři rozšířené přechodu. Více podmínek v sdílené přechod jsou vyhodnocovány v pořadí, ve kterém se zobrazí v Návrháři přechod. **Poznámka:** Všimněte si, že pokud <xref:System.Activities.Statements.Transition.Condition%2A> přechodu se vyhodnocuje **False** (nebo všechny podmínky přechod sdílené aktivační událost vyhodnocení **False**), bude přechodu není dojde k a bude ho přeplánovat všechny aktivační události pro všechny přechody ze stavu. V tomto kurzu, nemůže tato situace nastat z důvodu způsob, jak jsou nakonfigurované podmínky (máme konkrétní akce na tom, jestli odhad správný nebo nesprávné).|  
|**Zdroj**|Hodnota TRUE|Označuje stav, ze kterého pochází tento přechod. Kliknutím na jméno stavu zdroje přepínačů návrháře zobrazení rozšířené zobrazení tohoto stavu. Tato hodnota nastavena při přechodu je vytvořena a nelze je změnit.|  
|<xref:System.Activities.Statements.Transition.Trigger%2A>|False|Určuje aktivity, jejichž dokončení zahájí přechodu. Pokud chcete nastavit tuto aktivitu, přetáhněte ji na aktivitu ze **sada nástrojů** a umístěte jej do **aktivační událost** části přechodu.|  
|<xref:System.Activities.Statements.Transition.Action%2A>|False|Určuje aktivity, která se spustí po dokončení aktivity aktivační události a <xref:System.Activities.Statements.Transition.Condition%2A>, pokud existuje, vyhodnotí jako **true**. Tato aktivita se spustí, až po přechodu do cílového stavu, <xref:System.Activities.Statements.State.Exit%2A> aktivita pro zdroj stavu, pokud existuje, je spuštěna. Po rozbalení návrháře přechod tato hodnota se dá nastavit tak, že přetáhnete aktivitu z **sada nástrojů** a vyřadit ho do **akce** části přechodu. Může existovat více akcí pro jediný přechod. Jednotlivé akce lze rozšířit a sjednané a můžete seřadit kliknutím na tlačítko nahoru nebo dolů šipka na akci pokud existuje více akcí v přechodu.|  
|**Cílový**|Hodnota TRUE|Označuje stav, která stavu počítač přejde do po dokončení přechodu. To odpovídá <xref:System.Activities.Statements.Transition.To%2A> vlastnost přechodu v objektovém modelu. Kliknutím na název cílového stavu přepínačů návrháře zobrazení rozšířené zobrazení tohoto stavu. Tato hodnota nastavena při přechodu je vytvořen a přetáhněte šipku, která se připojuje přechod do stavu cílového v Návrháři lze změnit.|  
  
### <a name="creating-transitions"></a>Vytváření přechody  
 Přechody jsou vytvořeny tak, že přetáhnete řádku z jednoho stavu do jiného, nebo vyřazením stavu na trojúhelníčky, které se zobrazí při přetažení jeden stav přes jiný stav. K vytvoření přechodu přetažením, najeďte myší na hranu stavu zdroje a přetáhněte řádku ze zdrojového na cílový stav. K vytvoření přechodu pádem, stav cílového a pozastavte ukazatel myši nad stavu zdroje, přetažení ji na jeden z čtyři trojúhelníčky, které se zobrazují kolem stavu zdroje. Cílový stav může být buď nový stav přetažením z **sada nástrojů**, nebo existující stavu přetažením z Návrháře pracovních postupů.  
  
> [!NOTE]
>  Jednoho stavu ve stavu počítač může mít až 76 přechody vytvořené pomocí návrháře pracovních postupů. Limit přechody stavu vytvořen vně návrháře pracovních postupů pro je omezena pouze systémové prostředky.  
  
 Přechody sdílené aktivační události jsou sadu přechody, které sdílejí stejnou aktivační událost. Aktivační události sdílené umožňuje podmíněného postup k určení stavu na základě vyhodnocení výrazů, které jsou nakonfigurované pro více přechody, které sdílejí společné aktivační událost. Pokud chcete přidat další akce pro přechod a vytvořit sdílený přechodu, klikněte na kruh označující začátek požadované přechodu a přetáhněte ji do požadovaného stavu. Nový přechod budou sdílet stejnou aktivační událost jako počáteční přechodu, ale bude mít jedinečný podmínku a akce. Sdílené přechody můžete také vytvořit z v Návrháři přechod kliknutím **přidat sdílený aktivační událost přechod** v dolní části návrháře přechod a pak vybrat požadovanou cílového stavu z  **Dostupné stavy připojení** rozevíracího seznamu.  
  
## <a name="see-also"></a>Viz také  
 [StateMachine](../workflow-designer/statemachine-activity-designer.md)   
 [FinalState](../workflow-designer/finalstate-activity-designer.md)   
 [Stav](../workflow-designer/state-activity-designer.md)