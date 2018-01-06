---
title: "Přejděte do definice a funkce Náhled definice | Microsoft Docs"
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code editor, go to definition
- code editor, peek definition
- go to definition
- peek definition
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: db67f01ff2a58ee856e4588df8770fc4edef8ca2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="go-to-definition-and-peek-definition"></a>Přejděte do definice a funkce Náhled definice  
Přejít k definici a prohlížení definice funkce umožňují snadno zobrazit definici typ nebo člen.

## <a name="go-to-definition"></a>Přechod na definici  
Přejít k definici funkce přejde na zdroj typ nebo člen a výsledek otevře novou záložku. Pokud se uživatel klávesnice, umístěte ukazatel myši na text někde v názvu symbolu a stiskněte klávesu **F12**. Pokud používáte myši, vyberte buď **přejít k definici** z místní nabídky nebo pomocí **Ctrl + kliknutí** funkce popsané níže.  

### <a name="ctrl-click-go-to-definition"></a>CTRL + kliknutí přechod na definici  
V aplikaci Visual Studio 2017 verzi 15.4 je jednodušší způsob myši uživatelům rychle se dostat k přejít k definici. Po stisknutí klávesy se můžete kliknout symboly **Ctrl** při přechodu myší nad typ nebo člen. Chcete-li rychle přejít k definici symbol, stiskněte **Ctrl** klíče a potom klikněte na jeho. Je to snadné!

![Myši kliknutím na Přejít do definice animace](../ide/media/click_gotodef.gif)

Můžete změnit modifikační klávesy pro kliknutí myší **přejít k definici** přechodem na **nástroje**, **možnosti**, **textového editoru**, **Obecné**a vyberte buď **Alt** nebo **Ctrl + Alt** z **použití modifikační klávesy** rozevíracího seznamu. Můžete také zakázat kliknutí myší **přejít k definici** zrušením zaškrtnutí políčka **povolit myši klikněte na provést přejít k definici** zaškrtávací políčko.  

![Povolení kliknutí myší přechod na definici](../ide/media/editor_options_mouse_click_gotodef.png)  

## <a name="peek-definition"></a>Funkce Náhled definice
Funkce Náhled definice funkce umožňuje zobrazit náhled definici typu, aniž byste museli opustit vaše aktuální umístění v editoru. Pokud se uživatel klávesnice, umístěte ukazatel myši na text někde uvnitř typ nebo člen název a stiskněte klávesu **Alt + F12**. Pokud používáte myši, můžete si vybrat **funkce Náhled definice** v místní nabídce. V aplikaci Visual Studio 2017 verze 15,4 a novější je nový způsob zobrazení funkce Náhled definice pomocí myši. První, přejděte na **nástroje**, **možnosti**, **textového editoru**, **Obecné**. Vyberte možnost **otevřít v zobrazení funkce Náhled definice** a klikněte na tlačítko **OK** zavřete **možnosti** dialogové okno.  

![Nastavení možnosti kliknutí myší funkce Náhled definice](../ide/media/editor_options_peek_view.png)  

Potom stiskněte klávesu **Ctrl** (nebo libovolného modifikační klávesy je vybraný v **možnosti**) a klikněte na typ nebo člen.  

![Funkce Náhled definice animace](../ide/media/peek_definition.gif)

Pokud jste prohlížet jinou definici z automaticky otevíraném okně, začněte s popisem cesty cesty, která můžete přejít pomocí kružnice a šipek, které jsou uvedeny výše automaticky otevřeném okně.  

Další informace najdete v tématu [postupy: zobrazení a úpravy kódu podle pomocí funkce Náhled definice (Alt + F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md).  

## <a name="see-also"></a>Viz také  
[Navigace v kódu](../ide/navigating-code.md)  
[Postupy: Zobrazení a úpravy kódu s použitím funkce Náhled definice (Alt+F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)  
