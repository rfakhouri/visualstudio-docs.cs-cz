---
title: 'Postupy: pohyb v sadě Visual Studio IDE | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- environments [Visual Studio], navigation
- documents [Visual Studio], navigating
- IDE, navigation
- navigation [Visual Studio]
- files [Visual Studio], navigating between
- windows [Visual Studio], navigating
- Window.NextDocumentWindowNav
- IDE navigator
ms.assetid: 6c36b6eb-c93f-496b-af08-4199f7afd8bd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d14c3dfd566fb3383e53225b3acde69d097071b3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-move-around-in-the-visual-studio-ide"></a>Postupy: pohyb v sadě Visual Studio IDE
Integrované vývojové prostředí (IDE) byl navrženou můžete přesunout z okna a souboru do souboru několika různými způsoby v závislosti na požadavcích vaší předvolbu nebo projektu. Můžete procházet soubory lze otevřít v editoru nebo procházení všechny aktivní nástroj windows v prostředí IDE. Také můžete přepnout přímo na všechny soubor otevřete v editoru, bez ohledu na pořadí, ve kterém posledního použití. Tato funkce může pomoct zvýšit produktivitu při práci v prostředí IDE.  
  
> [!NOTE]
> Možnosti dostupné v dialogových oknech a názvy a umístění příkazy nabídky, se může lišit od co je popsaný v tomto článku, v závislosti na aktivním nastavení nebo edici. Tento článek byl napsán s **Obecné** nastavení v paměti. Chcete-li změnit nastavení, například k **Obecné** nebo **Visual C++** nastavení, vyberte **nástroje** > **nastavení importu a exportu**a potom zvolte **obnovit nastavení**.

## <a name="keyboard-shortcuts"></a>Klávesové zkratky  
Téměř každý příkaz v sadě Visual Studio má klávesové zkratky. Můžete také vytvořit vlastní zástupce. Další informace najdete v tématu [identifikace a přizpůsobení klávesových zkratek](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
## <a name="navigate-among-files-in-the-editor"></a>Pohyb mezi soubory v editoru  
Chcete-li procházet otevřen v editoru souborů můžete použít několik metod. Můžete přesouvat mezi soubory podle pořadí, ve kterém k nim přístup, použijte IDE Navigátor rychle najít všechny aktuálně otevřené soubory, nebo kód pin oblíbených souborů na kartu tak, aby byly vždy viditelné.  
  
Přejděte zpátky a předat dál cyklu procházet otevřených souborů v editoru podle pořadí, ve kterém byly přistupovali, mnohem jako back a dál udělat pro historii zobrazení v aplikaci Internet Explorer.  
  
#### <a name="to-move-through-open-files-in-order-of-use"></a>Chcete-li procházet soubory lze otevřít v pořadí podle používání  
  
-   Pokud chcete aktivovat otevřené dokumenty v pořadí, že většina nedávno přistupovala, stiskněte klávesu **Ctrl**+**-**.  
  
-   Pokud chcete aktivovat otevřené dokumenty v obráceném pořadí, stiskněte klávesu **Ctrl**+**Shift**+**-**.  
  
    > [!NOTE]
    > **Přejděte zpět** a **přejděte dál** také naleznete na **zobrazení** nabídky.  
  
Také můžete přepnout konkrétní soubor otevřete v editoru, bez ohledu na to, kdy posledního otevření souboru, pomocí **IDE Navigátor**, **Active soubory** seznamu v editoru nebo **Windows** dialogové okno.  
  
**IDE Navigátor** funguje podobně jako přepínači aplikace systému Windows. Není k dispozici z nabídek a k němu přístup pouze pomocí klávesové zkratky. Můžete buď dva příkazy pro přístup **IDE Navigátor** (zobrazené dole) k procházení souborů, v závislosti na pořadí, ve kterém chcete procházet.  
  
![Visual Studio IDE Navigátor](../ide/media/vs2015_ide_navigator.png "VS2015_IDE_Navigator")  
  
`Window.PreviousDocumentWindowNav` Umožňuje přesunout do posledního přístupu k souboru a `Window.NextDocumentWindowNav` umožňuje přesunout v obráceném pořadí. **Obecná nastavení vývoj** přiřadí **Shift**+**Alt**+**F7** k `Window.PreviousDocumentWindowNav` a **Alt**  + **F7** k `Window.NextDocumentWindowNav`.
  
> [!NOTE]
> Pokud používáte kombinaci nastavení ještě nemá kombinaci kláves zástupce, který je přiřazen tento příkaz, můžete přiřadit vlastní pomocí vlastního příkazu **klávesnice** stránky **možnosti** dialogové okno pole. Další informace najdete v tématu [identifikace a přizpůsobení klávesových zkratek](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
#### <a name="to-switch-to-specific-files-in-the-editor"></a>Přejděte na konkrétní soubory v editoru  
  
-   Stiskněte klávesu **Ctrl**+**kartě** zobrazíte **IDE Navigátor**. Podržte stisknutou **Ctrl** klíč a stiskněte klávesu **kartě** opakovaně, dokud vyberte soubor, který chcete přepnout.  
  
    > [!TIP]
    >  Pořadí, ve kterém můžete projít **Active soubory** seznamu, podržte klávesu **Ctrl**+**Shift** klíče a stiskněte klávesu **kartě**.  
  
    \- nebo –  
  
-   V pravém horním rohu editoru zvolte **Active soubory** tlačítko a pak vyberte ze seznamu přepnout do souboru.  
  
    \- nebo –  
  
-   Na řádku nabídek zvolte **okno** > **Windows**.  
  
-   V seznamu, vyberte soubor, který chcete zobrazit a potom zvolte **aktivovat**.  
  
## <a name="navigate-among-tool-windows-in-the-ide"></a>Pohyb mezi nástroj windows v prostředí IDE  
**IDE Navigátor** také umožňuje cyklicky nástroj windows, je nutné otevřít v prostředí IDE. Můžete buď dva příkazy pro přístup **IDE Navigátor** cyklicky nástroj windows, v závislosti na pořadí, ve kterém chcete procházet. `Window.PreviousToolWindowNav` Umožňuje přesunout do posledního přístupu k souboru a `Window.NextToolWindowNav` umožňuje přesunout v obráceném pořadí. **Obecná nastavení vývoj** přiřadí **Shift**+**Alt**+**F7** k `Window.PreviousDocumentWindowNav` a **Alt**  + **F7** k `Window.NextDocumentWindowNav`.
  
> [!NOTE]
> Pokud používáte kombinaci nastavení ještě nemá kombinaci kláves zástupce, který je přiřazen tento příkaz, můžete přiřadit vlastní pomocí vlastního příkazu **klávesnice** stránky **možnosti** dialogové okno pole. Další informace najdete v tématu [identifikace a přizpůsobení klávesových zkratek](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
#### <a name="to-switch-to-a-specific-tool-window-in-the-ide"></a>Přepnutí do konkrétní nástroj okna v prostředí IDE  
  
-   Stiskněte klávesu **Alt**+**F7** zobrazíte **IDE Navigátor**. Podržte stisknutou **Alt** klíč a stiskněte klávesu **F7** opakovaně, dokud vyberete okna máte v úmyslu přepnout.  
  
    > [!TIP]
    > Pořadí, ve kterém můžete projít **Active nástroj Windows** seznamu, podržte klávesu **Shift**+**Alt** klíče a stiskněte klávesu **F7**.  
  
## <a name="see-also"></a>Viz také
[Přizpůsobení rozložení oken](../ide/customizing-window-layouts-in-visual-studio.md)   
[Výchozí klávesové zkratky](../ide/default-keyboard-shortcuts-in-visual-studio.md)