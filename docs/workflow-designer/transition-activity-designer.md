---
title: Návrhář postupu provádění – Návrhář aktivity Transition
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.Transition.UI
ms.assetid: f6e8b5cc-7fb8-4699-9703-f3c9fc7cc316
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 62de732d4f2aed819681c0d2141df4ba0553ffe2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55033614"
---
# <a name="transition-activity-designer"></a>Návrhář aktivity Transition

A <xref:System.Activities.Statements.Transition> představuje přechod mezi dvěma stavy.

## <a name="using-the-transition-activity-designer"></a>Návrhář aktivity Transition pomocí

Návrhář aktivity transition umožňuje nakonfigurovat přechod mezi dvěma stavy.

### <a name="transition-properties-in-the-workflow-designer"></a>Vlastnosti přechodu v Návrháři postupu provádění

Následující tabulka ukazuje <xref:System.Activities.Statements.Transition> vlastnosti, které lze nastavit pomocí návrháře pracovních postupů a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Statements.Transition.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.Transition> návrháře aktivit. Výchozí hodnota je **T1**. Hodnotu lze upravit v mřížce vlastností v hlavičce návrháře rozšířené přechodu a v záhlaví oddílu akce v Návrháři rozšířené přechodu. <xref:System.Activities.Activity.DisplayName%2A> Se používá v navigace s popisem cesty, který se zobrazí v horní části návrháře postupu provádění.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.Transition.Condition%2A>|False|Pokud jsou k dispozici, určuje výraz, který se musí vyhodnotit na **True** před řízení je předáno cílový stav. Tato podmínka se dá upravit v mřížce vlastností a v Návrháři rozšířené přechodu. Více podmínek ve sdílené přechodu se vyhodnocují v pořadí, v jakém jsou uvedeny v návrháři pro přechod. **Poznámka:**  Všimněte si, že pokud <xref:System.Activities.Statements.Transition.Condition%2A> přechodu vyhodnocen **False** (nebo vyhodnotit všechny podmínky sdílené spouštěcí události přechodu **False**), nedojde, přechod a všechny aktivační události pro všechny Přechod ze stavu bude znovu naplánována. V tomto kurzu, nemůže tato situace nastat z důvodu způsob, jakým jsou podmínky nakonfigurované (máme konkrétní akce pro Určuje, zda je odhad správný nebo není správná).|
|**Zdroj**|Pravda|Označuje stav, ze kterého pochází tohoto přechodu. Kliknutím na název stavu zdroje návrháře zobrazení přepne na rozbalené zobrazení tohoto stavu. Tato hodnota nastavena, při přechodu je vytvořen a nedá se změnit.|
|<xref:System.Activities.Statements.Transition.Trigger%2A>|False|Určuje aktivity, jejíž dokončení zahájí přechodu. Pokud chcete nastavit tuto aktivitu, přetáhněte aktivitu z **nástrojů** a umístěte ho do **aktivační událost** části přechodu.|
|<xref:System.Activities.Statements.Transition.Action%2A>|False|Určuje, který se spouští po aktivitu spouštěcí události dokončení aktivity a <xref:System.Activities.Statements.Transition.Condition%2A>, pokud jsou k dispozici, je vyhodnocen jako **true**. Tato aktivita se spustí, až po přechod k určení stavu, <xref:System.Activities.Statements.State.Exit%2A> aktivity pro stav zdroje, pokud jsou k dispozici, je proveden. Po rozbalení návrháře přechod tuto hodnotu můžete nastavit přetažením aktivity z **nástrojů** a vyřadit ho do **akce** části přechodu. Může existovat více akcí pro jeden přechod. Jednotlivé akce lze rozšířit a uzavřeny a můžete seřadit kliknutím na tlačítko nahoru nebo šipku, která se zobrazí na akci pokud existuje více akcí v přechodu.|
|**cíl**|Pravda|Označuje stav, který stavový počítač přejde do po dokončení přechodu. To odpovídá <xref:System.Activities.Statements.Transition.To%2A> vlastnost přechodu v objektovém modelu. Kliknutím na název cílový stav zobrazení návrháře přepne na rozbalené zobrazení tohoto stavu. Tato hodnota nastavena, při přechodu je vytvořen a můžete změnit přetažením na šipku, která se připojuje k přechodu do stavu cílového v návrháři.|

### <a name="creating-transitions"></a>Vytváření přechody

Přechody se vytvoří, přetažením řádku z jednoho stavu do druhého nebo přetažením stavu na trojúhelníky, které se zobrazí, pokud státu přesune jiný stav. Přetažením vytvoříte přechod, najeďte myší na okraj stavu zdroje a přetáhněte čáru ze zdrojového na cílový stav. Vytvořit přechod pomocí přetažení, přetáhněte cílový stav najeďte myší stavu zdroje a umístěte ho na jednu ze čtyř trojúhelníků, které se zobrazí kolem stavu zdroje. Cílový stav může být buď nový stav přetáhnout z **nástrojů**, nebo stávající stav kvůli usnadnění použití vypsány v Návrháři pracovních postupů.

> [!NOTE]
> Jeden stav stavového stroje. může mít až 76 přechody vytvořené pomocí návrháře postupu provádění. Omezení přechodů pro stav pro pracovní postupy vytvořené mimo návrháře je omezen pouze systémové prostředky.

Sdílené spouštěcí události přechody jsou sadu přechody, které sdílejí stejnou aktivační událost. Sdílené spouštěcí události umožňuje podmíněný průběh na cílový stav. na základě vyhodnocení výrazů, které jsou nakonfigurované pro více přechodů, které sdílejí společné aktivační událost. Přidání další akce k přechodu a vytvořit sdílené přechod, klikněte na kruh, který označuje začátek požadované přechodu a přetáhněte ho do požadovaného stavu. Nový přechod budou sdílet stejnou spouštěcí událost jako počáteční přechodu, ale bude mít jedinečné podmínku a akce. Sdílené přechody lze také vytvořit z v rámci přechodu návrháře kliknutím **přidat sdílené triggeru, přechod** v dolní části návrháře přechod a pak vyberete požadovanou cílovou stavu z  **Dostupné stavy připojení** rozevíracího seznamu.

## <a name="see-also"></a>Viz také:

- [StateMachine](../workflow-designer/statemachine-activity-designer.md)
- [FinalState](../workflow-designer/finalstate-activity-designer.md)
- [Stav](../workflow-designer/state-activity-designer.md)