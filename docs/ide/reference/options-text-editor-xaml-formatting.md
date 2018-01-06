---
title: "Možnosti, textový Editor, XAML, formátování | Microsoft Docs"
ms.custom: 
ms.date: 01/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XAML.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.XAML.Miscellaneous
- VS.ToolsOptionsPages.Text_Editor.XAML.Formatting.Spacing
helpviewer_keywords:
- element spacing, XAML view settings
- attribute spacing, XAML view settings
- XAML view settings, auto-formatting events
- auto-formatting events, XAML view settings
- XAML view settings, tag wrapping
- XAML view settings, auto insert
- quotation mark style, XAML view settings
- XAML formatting, WPF Designer
- XAML view settings, Toolbox
- XAML view settings, element spacing
- default view, XAML view settings
- auto insert, XAML view settings
- XAML view settings, default view
- XAML view settings, quotation mark style
- tag wrapping, XAML view settings
- WPF Designer, XAML formatting
- XAML view settings, attribute spacing
ms.assetid: ad3820b1-0d94-4807-a74c-c3467ed973a2
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: a5a3ffde718d951181d788cca5cf57a21cbff4d8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="options-text-editor-xaml-formatting"></a>Možnosti, textový editor, XAML, formátování
Použití **formátování** na stránce vlastností zadejte způsob elementů a atributů formátování v dokumentech XAML. Otevřete **možnosti** dialogové okno, klikněte na tlačítko **nástroje** nabídce a pak klikněte na tlačítko **možnosti**. Pro přístup k **formátování** vlastnost rozbalte **textového editoru**, **XAML**, **formátování** uzlu.  

> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  

## <a name="auto-formatting-events"></a>Události automatického formátování  
 Automatické formátování může dojít, když je zjištěna některý z následujících událostí.  

-   Dokončení koncová značka nebo jednoduchých značek.  

-   Dokončení počáteční značku.  

-   Vkládání ze schránky.  

-   Formátování příkazy klávesnice.  

Můžete určit, které události způsobují, automatického formátování.  

|||  
|-|-|  
|**Při dokončení koncová značka nebo jednoduchých značek**|Automatické formátování nastane po dokončení zápisu koncová značka nebo prostřednictvím jednoduchých značek. Prostřednictvím jednoduchých značek nemá žádné atributy, například `<Button />`.|  
|**Při dokončení počáteční značce**|Automatické formátování nastane po dokončení zápisu u počáteční značky.|  
|**Na vložte ze schránky**|Automatické formátování nastane, když vložíte XAML ze schránky do zobrazení jazyka XAML.|  

## <a name="quotation-mark-style"></a>Styl značky uvozovek  
 Toto nastavení určuje, zda jsou hodnoty atributu uzavřena v jednoduchých nebo dvojitých uvozovek. Toto nastavení použijte, automatického formátování a automatické dokončování IntelliSense.  

 Jakmile jednou nastavíte tuto možnost, pouze atributy následně přidat pomocí návrháře nebo ručně v zobrazení jazyka XAML se vztahuje.  

|||  
|-|-|  
|**Dvojité uvozovky (")**|Hodnoty atributů jsou uzavřené v uvozovkách.<br /><br /> `<Button Name="button1">Hello</Button>`|  
|**Jednoduché uvozovky (')**|Hodnoty atributů jsou uvedeny v jednoduchých uvozovkách.<br /><br /> `<Button Name='button1'>Hello</Button>`|  

## <a name="tag-wrapping"></a>Zalomení značky  
 Můžete zadat délku řádku zabalení značky. Pokud je povoleno zalomení značky, bude správně zabalená žádné XAML, později přidané pomocí návrháře.  

|||  
|-|-|  
|**Zalomení značky, které překročí zadané délce**|Určuje, zda jsou řádky zabalené v délka řádku určeného **délka**.|  
|**Délka**|Počet znaků, které mohou obsahovat řádek. V případě potřeby můžete některé řádky XAML překročit délka zadaný řádek.|  

## <a name="attribute-spacing"></a>Mezery atributů  
 Pomocí tohoto nastavení můžete řídit, jak jsou uspořádány atributy v dokumentu XAML  

|||  
|-|-|  
|**Zachovat vložení znaků newline a mezery mezi atributy**|Automatické formátování nové čar a mezery mezi atributy nemá vliv.<br /><br /> `<Button Height="23"   Name="button1"`<br /><br /> `Width="75">Hello</Button>`|  
|**Vložení a jedna mezera mezi atributy**|Atributy zabírají jeden řádek, pomocí jediného místa oddělení přiléhající atributy. Značka zabalení nastavení budou použita.<br /><br /> `<Button Height="23" Name="button1" Width="75">Hello</Button>`|  
|**Pozice každého atributu na samostatném řádku**|Každý atribut zabírá svůj vlastní řádek. To je užitečné, pokud existuje mnoho atributů.<br /><br /> `<Button`<br /><br /> `Height="23"`<br /><br /> `Name="button1"`<br /><br /> `Width="75">Hello</Button>`|  
|**Pozice první atribut na stejném řádku jako počáteční značce**|Pokud je zaškrtnuto, zobrazí se první atribut na stejném řádku jako počáteční značky elementu.<br /><br /> `<Button Height="23"`<br /><br /> `Name="button1"`<br /><br /> `Width="75">Hello</Button>`|  

## <a name="element-spacing"></a>Vzdálenost prvků  
 Pomocí tohoto nastavení můžete řídit, jak jsou uspořádány elementy v dokumentu XAML  

|||  
|-|-|  
|**Zachovat nové řádky v obsahu**|Prázdné řádky v obsahu elementu se neodeberou.<br /><br /> `<Grid>`<br /><br /> ``<br /><br /> ``<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> ``<br /><br /> `</Grid>`|  
|**Sbalit více prázdné řádky v obsahu na jeden řádek**|Prázdné řádky v obsahu elementu sbalené na jeden řádek.<br /><br /> `<Grid>`<br /><br /> ``<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> ``<br /><br /> `</Grid>`|  
|**Odebrat prázdné řádky v obsahu**|Budou odebrány všechny prázdné řádky v obsahu elementu.<br /><br /> `<Grid>`<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> `</Grid>`|  

## <a name="miscellaneous-section-auto-insert"></a>Různé části automatického vložení  
 Pomocí tohoto nastavení můžete řídit, kdy značky a uvozovky jsou automaticky generovány.  

|||  
|-|-|  
|**Koncové značky**|Určuje, zda elementu uzavírací značku se automaticky generuje při zavření počáteční značka s větší než znak (>).|  
|**Atribut uvozovky**|Určuje, zda nadřazených uvozovky jsou generovány, pokud je hodnota atributu vybraný z rozevíracího seznamu dokončení příkazu.|  
|**Pravými pro MarkupExtensions**|Určuje, zda rozšíření značek složená závorka (}) se automaticky vygeneruje, když zadáte otevření složených závorek znaků ({}).|  
|**Jednotlivé parametry MarkupExtension čárkami**|Určuje, zda čárkami jsou generovány, pokud zadáte více než jeden parametr v rozšíření značek.|  

## <a name="see-also"></a>Viz také  
 [XAML v grafickém subsystému WPF](/dotnet/framework/wpf/advanced/xaml-in-wpf)   
 [Postupy: Změna nastavení zobrazení XAML](http://msdn.microsoft.com/en-us/aee87c79-ca01-4f84-8fb7-a9e47048ee47)   
 [XAML a návody kódu](http://msdn.microsoft.com/en-us/b3ff41a0-a2a3-4f61-b698-ac88ec8f799c)
