---
title: 'Postupy: Správa režimů editoru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- views, virtual space
- line numbers, displaying
- virtual space mode
- line numbers
- Code Editor, view and display options
- full screen mode
- Code Editor, modes
- views, splitting
- views, word wrapping
- fonts and size
- views, creating new windows
- views, line numbers
- views, changing mode
- views, outlining
ms.assetid: 1fb48027-d870-439f-8b72-4a0321390748
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 193afeddd553dfda54de568c92b4697e3f1a2a93
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60095539"
---
# <a name="how-to-manage-editor-modes"></a>Postupy: Správa režimů editoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Editoru kódu sady Visual Studio můžete zobrazit v různých režimech zobrazení.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="enabling-full-screen-mode"></a>Zapnutí režimu zobrazení na celé obrazovce  
 Je možné skrýt všechna okna nástrojů a zobrazit pouze okna dokumentu tím, že **zobrazení na celé obrazovce** režimu.  
  
#### <a name="to-enable-full-screen-mode"></a>Pokud chcete povolit režim zobrazení na celé obrazovce  
  
- Stisknutím klávesy ALT + SHIFT + ENTER a zadejte skript nebo ukončit **zobrazení na celé obrazovce** režimu.  
  
     --nebo--  
  
- Příkaz `View.Fullscreen` v **příkaz** okna.  
  
## <a name="enabling-virtual-space-mode"></a>Povolení režim virtuálního prostoru  
 V **virtuální prostor** režimu, budou vkládány mezery na konci každého řádku kódu. Vyberte tuto možnost na pozici poznámky na bod konzistentní vzhledem k vedle vašeho kódu.  
  
#### <a name="to-enable-virtual-space-mode"></a>Pokud chcete povolit režim virtuálního prostoru  
  
1. Vyberte **možnosti** z **nástroje** nabídky.  
  
2. Rozbalte **textový Editor** složky a zvolte **všechny jazyky** a tuto možnost nastavte, globálně nebo zvolte konkrétní jazykovou složku. (Například pokud chcete zapnout čísla řádků pouze v jazyce Visual Basic, zvolte základní, Možnosti textového editoru.)  
  
3. Vyberte **Obecné** možnosti a v části **nastavení**vyberte **povolit virtuální prostor**.  
  
    > [!NOTE]
    >  **Virtuální prostor** je povolený v **výběr sloupce** režimu. Když **virtuální prostor** není povolen režim, kurzor se přesune z konce jeden řádek přímo na první znak na další.  
  
## <a name="see-also"></a>Viz také  
 [Vlastní nastavení editoru](../ide/customizing-the-editor.md)   
 [Postupy: Rozvržení a dokování Windows](../misc/how-to-arrange-and-dock-windows.md)   
 [Písma a barvy, Prostředí, dialogové okno Možnosti](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)
