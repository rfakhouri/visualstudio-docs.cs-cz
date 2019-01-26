---
title: 'Návrhář postupu provádění – jak: Používání editoru výrazů'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Presentation.View.ExpressionTextBox.UI
ms.assetid: b5f961dd-6dda-41a9-9cae-0383d479ef3d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7c6d2bf026295d899f2bd0aee05eccb8013eedf0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54967255"
---
# <a name="how-to-use-the-expression-editor"></a>Postupy: Používání editoru výrazů

Editor výrazů je Návrhář postupu provádění ovládací prvek, který se používá v mnoha aktivit pracovního postupu k zadání a vyhodnocujte výrazy. Editor výrazů nabízí plnohodnotný IDE úpravy prostředí, včetně IntelliSense, zabarvení ParamInfo, podtržení vlnovkou u chyb, kromě jiných funkcí. Kompilátor ověří výraz poté, co je zadána. Pokud výraz není platný, zobrazí se ikona chyby. V editoru můžete otevřít také jako **Editor výrazů** dialogové okno.

Výrazy jsou literálními hodnotami nebo kódu jazyka Visual Basic vázán na argumenty nebo vlastnosti. Obsahující hodnoty prvků (například proměnné, konstanty, literály, vlastnosti), které jsou spojené s operacemi na novou hodnotu. Výrazy jsou zapsány pomocí syntaxe VB.NET i v případě, že aplikace je v aplikaci pomocí jazyka C#. To znamená, že malá a velká písmena, nezáleží, porovnání je provedeno pomocí jednoho stejné logické operátory jsou slova, podepsat ("=" místo "==") "a" a "nebo" namísto symboly "& &" a "||", a **nic** slouží místo **null**. Další informace o výrazy a operátory v jazyce Visual Basic a některé ukázky najdete v tématu [operátory a výrazy v jazyce Visual Basic](/previous-versions/visualstudio/visual-studio-2010/a1w3te48(v=vs.100)).

**Editor výrazů** chová takto:

- Pokud fokus není v editoru výrazů, vypadá jako na běžný ovládací prvek TextBlock.

- V editoru výrazů po výběru vypadat a jak se bude chovat jako ovládací prvek editoru výrazů. Editor výrazů regulární TextBlock vypadá znovu po ztratí fokus.

- Pokud vám soustředit se na Editor výrazů v Návrháři postupu provádění se změněným hostováním, pak se chová stejně jako textové pole. Jakmile v Návrháři postupu provádění se změněným hostováním se ztratí fokus, editoru výrazů bude vypadat jako regulární TextBlock znovu.

> [!NOTE]
> Technologie IntelliSense pro Editor výrazů je k dispozici pouze v aplikaci Visual Studio. V sadě Visual Studio a provádění se změněným hostováním scénáře kompilátor ověří výraz poté, co se zadají a editor výrazů zobrazuje ikonu chyby, pokud výraz není platný.

## <a name="use-the-expression-editor"></a>Používání editoru výrazů

1.  V sadě Visual Studio otevřete projekt nového nebo existujícího pracovního postupu.

2.  Přidání, například <xref:System.Activities.Statements.Assign> aktivitu do pracovního postupu.

    > [!NOTE]
    > Více aktivit pracovního postupu mít editory výrazu. Výraz objekty TextBlock se také zobrazují v Návrhář proměnných, Návrhář argumentů a Návrhář dynamických argumentů. <xref:System.Activities.Statements.Assign> Aktivita slouží jako příklad.

3.  Klikněte na levý výraz editoru v Návrháři aktivit pro <xref:System.Activities.Statements.Assign> aktivity.

     Šedé vodoznak řetězce  **\<k >** a  **\<zadejte výraz jazyka VB. >** jsou výchozí text řetězce pro výraz editory v <xref:System.Activities.Statements.Assign> aktivity.

4.  Při zadávání výrazu. Pokud zadáte řetězec, ujistěte se, že chcete vložit řetězec v uvozovkách. Pokud budete chtít vázat argument výrazu na proměnnou, ponechte uvozovky.

     Jakmile budete hotovi, vyberte oblast nebo oblasti mimo Editor výrazů přesune fokus na jiné části návrháře. Přesun fokusu způsobí, že kompilátor ověření výrazu, jak je popsáno výše.

     Alternativní způsob a zadat nebo upravit výraz je kliknout na tři tečky vedle názvu vlastnosti v mřížce vlastností. Vyberete symbol tří teček, otevře **Editor výrazů** jako dialogové okno.

## <a name="see-also"></a>Viz také:

- <xref:System.Activities.Presentation.View.ExpressionTextBox>