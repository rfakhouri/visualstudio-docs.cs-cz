---
title: "Postupy: přizpůsobení nabídek a panelů nástrojů v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.renametoolbar
- vs.customize.toolbars
- vs.buttoneditor
- vs.customize.commands
- vs.newtoolbar
helpviewer_keywords:
- captions, customizing toolbar
- custom toolbars [Visual Studio]
- command buttons, customizing toolbar
- labels, customizing toolbar
- images [Visual Studio], toolbar buttons
- buttons [Visual Studio], custom toolbars
- toolbars [Visual Studio], creating in the IDE
- icons [Visual Studio], customizing toolbar
- commands [Visual Studio], customizing environment
- customizing toolbars
- toolbars [Visual Studio], customizing
- toolbars [Visual Studio], customizing in the IDE
ms.assetid: b570ae2f-5302-45dc-9cc9-8d4d1ad50603
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c7c852033d5835c4da4cc7f1e3bdf5d20472439c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-menus-and-toolbars-in-visual-studio"></a>Postupy: Přizpůsobení nabídek a panelů nástrojů v sadě Visual Studio
Visual Studio můžete přizpůsobit, nejen přidávání a odebírání nabídky v řádku nabídek a panelů nástrojů, ale také přidávání a odebírání příkazy na jakékoli dané nástrojů nebo nabídky.  
  
> [!WARNING]
>  Po přizpůsobení panelu nástrojů nebo nabídky, ujistěte se, že zůstane jejího políčka vybrané v **přizpůsobit** dialogové okno. V opačném případě se vaše změny po ukončení a opětovném spuštění sady Visual Studio nezachovají.
  
## <a name="adding-removing-or-moving-a-menu-on-the-menu-bar"></a>Přidání, odebrání nebo přesunutí nabídky na řádku nabídek  
  
1.  Na řádku nabídek zvolte **nástroje**, **přizpůsobit**.  
  
     **Přizpůsobit** otevře se dialogové okno.  
  
2.  Na **příkazy** kartě, ponechte **řádku nabídek** možnost tlačítko vybrané, nechte **řádku nabídek** v seznamu vedle tato možnost vybrána a potom proveďte jednu z následujících sad pomocí následujících kroků:  
  
    -   Chcete-li přidat nabídku, zvolte **přidat nové nabídky** tlačítko, vyberte **změnit výběr** tlačítko s názvem v nabídce, která chcete přidat.  
  
        ![Přizpůsobit dialogové okno znázorňující způsob přidání nabídky](../ide/media/addmenu.png "PřidatNabídku")  
  
    -   Odebrat z nabídky, vyberte ho v **ovládací prvky** seznamu a potom vyberte **odstranit** tlačítko.  
  
    -   Chcete-li nabídky v panelu nabídek, zvolte v nabídce v **ovládací prvky** seznamu a potom vyberte **nahoru** nebo **přesunout dolů** tlačítko.  
  
## <a name="adding-removing-or-moving-a-toolbar"></a>Přidání, odebrání nebo přesunutí panelu nástrojů  
  
1.  Na řádku nabídek zvolte **nástroje**, **přizpůsobit**.  
  
     **Přizpůsobit** otevře se dialogové okno.  
  
2.  Na **nástrojů** kartu, proveďte jednu z následujících souborů kroků:  
  
    -   Chcete-li přidat panel nástrojů, zvolte **nový** tlačítko, zadejte název pro panel nástrojů, který chcete přidat a potom vyberte **OK** tlačítko.  
  
        ![Přizpůsobit dialogové okno znázorňující postup přidání panelů nástrojů](../ide/media/addtoolbar.png "AddToolbar")  
  
    -   Odebrat vlastní panel nástrojů, vyberte ho **panely nástrojů** seznamu a potom vyberte **odstranit** tlačítko.  
  
        > [!IMPORTANT]
        >  Můžete odstranit panely nástrojů, které vytvoříte, ale ne výchozí panely nástrojů.  
  
    -   Pokud chcete přesunout do jiného umístění ukotvení panelu nástrojů, vyberte ho **panely nástrojů** vyberte **změnit výběr** tlačítko a potom vyberte umístění v seznamu, který se zobrazí.  
  
        Panel nástrojů můžete také přetáhnout pomocí jeho levého okraje na libovolné místo v hlavní oblasti ukotvení.  
  
        > [!NOTE]
        >  Další informace o tom, jak zlepšit použitelnost a usnadnění panelů nástrojů najdete v tématu [postupy: nastavení možnosti usnadnění přístupu IDE](../ide/reference/how-to-set-ide-accessibility-options.md).  
  
## <a name="customizing_menu">Přizpůsobení nabídky nebo panelu nástrojů</a>
  
1.  Na řádku nabídek zvolte **nástroje**, **přizpůsobit**.  
  
    **Přizpůsobit** otevře se dialogové okno.  
  
2.  Na **příkazy** , zvolte tlačítko možnost pro typ elementu, který chcete přizpůsobit.  
  
3.  V seznamu pro daný typ prvku zvolte nabídku nebo panel nástrojů, který chcete upravit, a pak proveďte jednu z následujících skupin kroků:  
  
    -   Chcete-li přidat příkaz, zvolte **přidejte příkaz** tlačítko.  
  
        V **přidejte příkaz** dialogovém okně vyberte položku v **kategorie** vyberte položku v **příkazy** seznamu a potom vyberte **OK**tlačítko.  
  
        ![Příkaz dialogové okno Přidat v sadě Visual Studio](../ide/media/addcommand.png "addcommand –")  
  
    -   Pokud chcete odstranit příkaz, vyberte ho v **ovládací prvky** seznamu a potom vyberte **odstranit** tlačítko.  
  
    -   Chcete-li změnit pořadí příkazy, zvolte příkaz v **ovládací prvky** seznamu a potom vyberte **nahoru** nebo **přesunout dolů** tlačítko.  
  
    -   Chcete skupinu příkazů v části na vodorovném řádku, zvolte první příkaz v **ovládací prvky** seznam, vyberte **změnit výběr** tlačítko a potom vyberte **začátek skupiny** v nabídka, která se zobrazí.  
  
## <a name="resetting-a-menu-or-a-toolbar"></a>Obnovení nabídky nebo panelu nástrojů  
  
1.  Na řádku nabídek zvolte **nástroje**, **přizpůsobit**.  
  
    **Přizpůsobit** otevře se dialogové okno.  
  
2.  Na **příkazy** , zvolte tlačítko možnost pro typ elementu, který chcete obnovit.  
  
3.  V seznamu pro daný typ prvku zvolte nabídku nebo panel nástrojů, které chcete obnovit.  
  
4.  Vyberte **změnit výběr** tlačítko a potom vyberte **resetovat** v nabídce, která se zobrazí.  
  
    Můžete také obnovit všechny nabídek a panelů nástrojů výběrem **Obnovit vše** tlačítko.

## <a name="see-also"></a>Viz také
[Přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)  
[Přizpůsobení editoru](../ide/customizing-the-editor.md)