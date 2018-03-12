---
title: "Postupy: použití editoru výraz | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ExpressionTextBox.UI
ms.assetid: b5f961dd-6dda-41a9-9cae-0383d479ef3d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: be43ad439c8868064fc7e0bab79e051abb991e0d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-use-the-expression-editor"></a>Postupy: použití editoru výraz
Editor výrazů je ovládací prvek Návrháře pracovního postupu systému Windows, který se používá v mnoha aktivit pracovního postupu jako prostředek k zadání a vyhodnocení těchto výrazů. Plnohodnotný IDE technologii IntelliSense, včetně možnosti úprav nabízí Editor výraz zabarvení, ParamInfo, chyba podtržení vlnovkou mezi dalších funkcí. Kompilátor ověří výraz poté, co je zadána. Pokud ve výrazu je neplatná, zobrazí se ikona chyby. Editor můžete otevřít také jako **Editor výrazů** dialogové okno.

 Výrazy jsou literálových hodnot nebo [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] kód svázané se argumenty nebo vlastnosti. Obsahují hodnotu elementy (např. proměnné, konstanty, literály, vlastnosti), které jsou spojené s operací yield novou hodnotu. Výrazy jsou zapsány pomocí syntaxe VB.NET i v případě, že aplikace bude v programu pomocí jazyka C#. To znamená, malá a velká písmena, nezáleží, porovnání se provádí pomocí jedné rovná se ("=") přihlašovací místo ("=="), jsou logické operátory slova "a" a "nebo" místo symboly "& &" a "&#124;&#124;", a **nic**  se používá místo **null**. Další informace o výrazy a operátory v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] a některé ukázky naleznete v části [operátory a výrazy v jazyce Visual Basic](http://go.microsoft.com/fwlink/?LinkId=186818).

 **Editor výrazů** chová následovně:

-   Pokud fokus není v editoru výrazu, vypadá jako regulární TextBlock ovládacího prvku.

-   Jakmile je zaměřená na editoru výrazu, vzhled a chování jako ovládací prvek Editor výrazů. Po jeho ztratí fokus, it znovu vypadá jako regulární TextBlock.

-   Pokud byste se zaměřit na Editor výrazů v Návrháři opětovné hostování nástroje pracovního postupu, pak se chová jako textové pole. Pokud je fokus ztratili v Návrháři pracovních postupů opětovné hostování nástroje, editoru výraz znovu vypadá jako regulární TextBlock.

> [!NOTE]
> IntelliSense pro Editor výrazu je k dispozici pouze uvnitř z [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. V obou [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] a opětovné hostování nástroje scénáře kompilátor ověří výraz po zadání se a editoru výraz zobrazuje ikonu chyby, pokud výraz je neplatný.

### <a name="using-the-expression-editor"></a>Pomocí editoru výraz

1.  V [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], otevřete projekt nového nebo stávajícího pracovního postupu.

2.  Přidání, například <xref:System.Activities.Statements.Assign> aktivitu do pracovního postupu.

    > [!NOTE]
    > Více aktivit pracovního postupu mít editory výraz. Objekty TextBlock výraz se zobrazí také v Návrháři proměnné, argument designer a návrháři dynamické argument. <xref:System.Activities.Statements.Assign> Aktivita se používá jako příklad.

3.  Klikněte na levý výraz editor v Návrhář aktivity pro <xref:System.Activities.Statements.Assign> aktivity.

     Řetězce šedé vodoznak  **\<k >** a  **\<zadejte výraz VB >** jsou výchozí textové řetězce pro výraz editory v <xref:System.Activities.Statements.Assign> aktivity.

4.  Zadejte výraz. Pokud zadáte řetězec, ujistěte se, že jste put řetězec v uvozovkách. Pokud se rozhodnete vázat argument výrazu proměnné, nechte uvozovek.

     Až skončíte, vyberte oblast nebo oblasti mimo Editor výraz přesune fokus na jinou část návrháře. To způsobí, že kompilátoru k ověření výrazu, jak je popsáno výše.

     Alternativní způsob zadejte či upravit výrazu je klikněte na tlačítko se třemi tečkami vedle názvu vlastnosti v tabulce vlastností. Otevře se **Editor výrazů** jako dialogového okna.

## <a name="see-also"></a>Viz také

- <xref:System.Activities.Presentation.View.ExpressionTextBox>