---
title: "Pomocí sady nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.chooseitems
- vs.toolboxpages.activexcontrols
- VS.CHOOSEITEMS.windowsuixamlcomponents
- VS.chooseitems.silverlightcomponents
- VC.EDITORS.RIBBON
- vs.customizetoolbox
- VS.chooseitems.System.Workflow_Components
- vs.chooseitems.frameworkcomponents
- VS.ToolboxPages..NET_Framework_Components
- VS.chooseitems.Microsoft.VisualStudio.Toolbox.VsToolboxPage
- vs.chooseitems.comcomponents
- vs.toolboxpages.NGWS_components
helpviewer_keywords:
- toolbox, adding items
- Visual Studio, toolbox
- toolbox, tabs
- toolbox
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c41a77a1fdb36ab8610ebc648cacb1568b330de8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-toolbox"></a>Používání sady nástrojů

V panelu nástrojů můžete použít k přidávání ovládacích prvků a dalších položek do projektu. Můžete přetáhnout a vyřadit různých ovládacích prvků na plochu návrháře používají a změnit velikost a umístění ovládacích prvků.

Sady nástrojů objeví ve spojení s návrháře zobrazení, jako je například návrháře zobrazení souboru XAML. V panelu nástrojů zobrazí pouze tyto ovládací prvky, které lze použít v Návrháři aktuální.

Verze rozhraní .NET Framework, že cílem vašeho projektu je také ovlivňuje sadu ovládacích prvků, které jsou viditelné v panelu nástrojů. Můžete nastavit projekt pro jinou verzi rozhraní .NET Framework výběrem uzlu projektu v **Průzkumníku řešení**a poté přejděte na **vlastnosti/aplikace/cílové rozhraní**.

## <a name="managing-the-toolbox-and-its-controls"></a>Správa sady nástrojů a jeho ovládacích prvků

Ve výchozím nastavení sady nástrojů sbalena na levé straně Visual Studio IDE a se zobrazí, když je přesunut kurzor. Budete moct připnout sady nástrojů (kliknutím **Pin** ikonu na panelu nástrojů prvky) tak, aby zůstane otevřený po přesunutí kurzoru. Můžete také uvolnit okno sady nástrojů a přetáhněte ji na libovolné místo na obrazovce. Lze ukotvit, vyjměte a skrytí panelu nástrojů pravým tlačítkem myši na panelu nástrojů prvky a výběrem jedné z možností.

Můžete změnit pořadí položek na kartě nástrojů nebo přidat vlastní karty a položek pomocí následujících příkazů v místní nabídce:

-   **Přejmenovat položku** -Přejmenuje vybranou položku.  
  
-   **Zobrazit všechny** -zobrazuje všechny možné ovládací prvky (nikoli pouze ty, které se vztahují k aktuální designer).  
  
-   **Zobrazení seznamu** -zobrazuje ovládacích prvků ve svislém seznamu. Pokud není zaškrtnuto, zobrazí se vodorovně ovládacích prvků.  
  
-   **Zvolte položky** -otevře **výběr položek sady nástrojů** pole, ve kterém můžete zadat položky, které se zobrazují v **sada nástrojů**. Můžete zobrazit nebo skrýt položku zaškrtnutím nebo zrušením zaškrtnutí jejího políčka.  
  
-   **Seřazení položek abecedně** -Seřadí položky podle názvu.  
  
-   **Panel nástrojů obnovit** – obnoví výchozí nastavení sady nástrojů a položky.  
  
-   **Přidat kartu** -přidá novou kartu panelu nástrojů.  
  
-   **Přesunout nahoru** -Přesune vybranou položku nahoru.  
  
-   **Přesunout dolů** -Přesune vybranou položku dolů.  

## <a name="creating-and-distributing-custom-toolbox-controls"></a>Vytváření a distribuci vlastní ovládací prvky

Můžete vytvořit vlastní sada nástrojů ovládacího prvku v jazyce Visual Basic a Visual C# a můžete spustit pomocí šablony projektu, který je založen na [Windows Presentation Foundation](../extensibility/creating-a-wpf-toolbox-control.md) nebo [Windows Forms](../extensibility/creating-a-windows-forms-toolbox-control.md). Potom můžete ovládací prvek distribuovat do ostatními členy týmu nebo publikování na webu pomocí [instalační program sady nástrojů ovládacích prvků](http://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx).

## <a name="see-also"></a>Viz také

[Psaní kódu v editoru](../ide/writing-code-in-the-code-and-text-editor.md)