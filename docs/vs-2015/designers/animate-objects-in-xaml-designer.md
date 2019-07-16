---
title: Animace objektů v Návrháři XAML | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7846ade8dba2ce849acf62311e508c157b07dd3e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68186760"
---
# <a name="animate-objects-in-xaml-designer"></a>Animace objektů v Návrháři XAML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete vytvořit krátké animace, které přesunout objekty nebo má dovnitř a ven vyblednout.  
  
 Pokud chcete začít, vytvořte *scénáře*. Scénář obsahuje jeden nebo více *časové osy*. Nastavte *klíčové snímky* na časové ose k označení změny vlastností. Poté při spuštění animace Blendu argument interpolaci změny vlastností za určené časové období. Výsledkem je hladký přechod. Může jakákoli vlastnost, která patří do objektu animace, v případě nevizuální vlastnosti.  
  
 Následující obrázek znázorňuje ve scénáři s názvem **MoveUp**. Na časové ose obsahuje klíčové snímky, které označení pozice X a Y obdélníku. Při spuštění této animace obdélníku přesune z jedné pozice do druhé plynule.  
  
 ![](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png "982f031a-74a3-414a-abc2-a0f41a741075")  
  
 Zjistěte, jak vytvořit animace v těchto videích.  
  
|Podívejte se na krátké video:|Naučte se:|  
|--------------------------|-------------------|  
|![Konfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvořit časové osy](http://www.popscreen.com/v/6A4eF/Microsoft-Expression-Blend-Creating-Timelines)|Vytvořit časové osy a práci s objekty na časové ose.|  
|![Konfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [přidat klíčové snímky a opakování animace](http://www.popscreen.com/v/6A4fi/Microsoft-Expression-Blend-Adding-Keyframes-and-Repeating-an-Animation)|Přidat klíčové snímky a nastavte vlastnosti na každý klíčový snímek. Potom spusťte objekty animace a sledujte hladký přechod mezi nimi.|  
|![Konfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [přidat aktivačních procedur událostí pro interaktivitu](http://www.popscreen.com/v/6A4e4/Microsoft-Expression-Blend-Adding-Event-Triggers-for-Interactivity)|Spuštění animace při výskytu události. Například spusťte jeden při načtení okna.|  
|![Konfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [animace barvy](http://www.popscreen.com/v/6A4gv/Microsoft-Expression-Blend-Animating-Colors)|Můžete změnit barvu objekt animace.|  
|![Konfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvořit a změnit cesty pohybu](http://www.popscreen.com/v/6A4fX/Microsoft-Expression-Blend-Creating-and-Modifying-Motion-Paths)|Animace objektů podél cesty.|  
|![Konfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [usnadňují klíčové snímky](http://www.popscreen.com/v/6A4dM/Microsoft-Expression-Blend-Easing-Keyframes)|Urychlení nebo zpomalení animace poblíž začátku (*usnadnění v*) nebo v blízkosti konce (*uvolnění mimo*) animace.|  
|![Konfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [animace tlačítka](http://www.popscreen.com/v/6A4fK/Microsoft-Expression-Blend-Animating-a-Button)|Vytvoření zajímavé efekty, které se zobrazí na tlačítku když uživatel na ně odkazuje.|  
|![Konfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvářet animace a pracovat s usnadnění](https://www.youtube.com/watch?v=mAJXYrwxGYo)|Animace efekty, které se zobrazí, když uživatel stiskne stisknuté v imagi kalkulačku.|  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření uživatelského rozhraní pomocí nástroje Blend pro Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)
