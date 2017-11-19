---
title: "Animace objektů v Návrháři XAML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1f4fd45337ebd0f00362d352077cf8441e6f5afa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="animate-objects-in-xaml-designer"></a>Animace objektů v Návrháři XAML
Můžete vytvořit krátké animace, které přesun objektů nebo je objevovat a odhlášení.  
  
 Chcete-li začít, vytvořte *storyboard*. Scénář obsahuje jeden nebo více *časové osy*. Nastavit *klíčových snímků* na časové ose označit změny vlastností. Poté při spuštění animace Blend argument interpolaci změny vlastností po určenou dobu. Výsledkem je plynulý přechod. Můžete animace jakákoli vlastnost, která patří do objektu, a to ani v nevizuální vlastnosti.  
  
 Následující obrázek znázorňuje storyboard, s názvem **MoveUp**. Časová osa obsahuje klíčových snímků, které označit X a Y pomyslného obdélníku. Když je tato animace spuštěna, rámeček přesune z jednoho místa na jiný bez problémů.  
  
 ![](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png "982f031a-74a3-414a-abc2-a0f41a741075")  
  
 Naučte se vytvořit animací učíte při sledování tyto videa.  
  
|Podívejte se na krátké video:|Zjistěte, jak:|  
|--------------------------|-------------------|  
|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvořit časové osy](http://www.popscreen.com/v/6A4eF/Microsoft-Expression-Blend-Creating-Timelines)|Vytvoření časové osy a práce s objekty v časovou osu.|  
|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [přidejte klíčových snímků a opakováním animace](http://www.popscreen.com/v/6A4fi/Microsoft-Expression-Blend-Adding-Keyframes-and-Repeating-an-Animation)|Přidejte klíčových snímků a nastavte vlastnosti na každý klíčového snímku. Potom spusťte objekty animace a sledujte plynule přechod mezi nimi.|  
|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [přidat aktivačních událostí pro interaktivity](http://www.popscreen.com/v/6A4e4/Microsoft-Expression-Blend-Adding-Event-Triggers-for-Interactivity)|Animace spusťte, když dojde k události. Jeden například spusťte, když okno načte.|  
|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [animace barvy](http://www.popscreen.com/v/6A4gv/Microsoft-Expression-Blend-Animating-Colors)|Chcete-li změnit barvu objektu použijte animace.|  
|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvoření a změna cest pohybu](http://www.popscreen.com/v/6A4fX/Microsoft-Expression-Blend-Creating-and-Modifying-Motion-Paths)|Animace objektů podél cesty.|  
|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [usnadňují klíčových snímků](http://www.popscreen.com/v/6A4dM/Microsoft-Expression-Blend-Easing-Keyframes)|Urychlení nebo zpomalit animace u počátku (*nejvýraznější v*) nebo poblíž konce (*nejvýraznější out*) animace.|  
|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [animace tlačítko](http://www.popscreen.com/v/6A4fK/Microsoft-Expression-Blend-Animating-a-Button)|Na tlačítko vytvořte zajímavé důsledky, které se zobrazují, když uživatel na ně odkazuje.|  
|![Konfigurace nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvořit animace a pracovat s usnadnění](https://www.youtube.com/watch?v=mAJXYrwxGYo)|Animace důsledky, které se zobrazí po stisknutí dolů tlačítka na bitovou kopii kalkulačky.|  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)