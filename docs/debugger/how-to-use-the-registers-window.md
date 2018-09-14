---
title: Zobrazení hodnot registru v ladicím programu sady Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.registers
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- registers, debugging
- register contents
- flags, Registers window
- register groups
- debugging [Visual Studio], Registers window
- Registers window
ms.assetid: 2918ffa2-562f-40d6-9053-ef321bbeb767
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ceadd2f131a75e01cec67c21dca0d7837b02738a
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551844"
---
# <a name="view-register-values-and-use-the-registers-window-in-the-visual-studio-debugger"></a>Zobrazit hodnoty registrace a použití okna registry v ladicím programu sady Visual Studio
Okno registrů je k dispozici pouze v případě, že je povoleno ladění úrovni adres v **možnosti** dialogovém okně **ladění** uzlu **Obecné** kategorie.  
  
 **Zaregistruje** okně se zobrazí obsah registru. Pokud uchováváte **zaregistruje** okna průběhu prostřednictvím programu open, můžete zobrazit registr hodnoty změnit, jak se spustí váš kód. Hodnoty, které se změnily nedávno se zobrazí červeně. Můžete upravit hodnot registru. Další informace najdete v tématu [postupy: Úprava hodnoty zaregistrovat](../debugger/how-to-edit-a-register-value.md).  
  
 K odebrání nepotřebných prvků, **zaregistruje** okno uspořádá registry do skupiny, které se liší podle platformy a procesor typu. Můžete zobrazit nebo skrýt skupin, jak chcete. Další informace najdete v tématu [postupy: zobrazení a skrytí registrovat skupiny](../debugger/how-to-display-and-hide-register-groups.md).  
  
 Podrobný úvod ke konceptům za registry a o okně registr, najdete v části [základní informace o ladění: okno registrů](../debugger/debugging-basics-registers-window.md).  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-display-the-registers-window"></a>Chcete-li zobrazit okno registrů  
  
-   Na **ladění** nabídce zvolte **Windows**a klikněte na tlačítko **zaregistruje** (nebo zvolte **Ctrl** + **Alt**   +  **G**).  
  
     Ladicí program musí být spuštěná nebo v režimu pozastavení.  
  
    > [!NOTE]
    >  Informace o registru není k dispozici pro skript nebo aplikace SQL.  
  
## <a name="see-also"></a>Viz také  
 [Základní informace k ladění: Okno registrů](../debugger/debugging-basics-registers-window.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Základní informace k ladění: Okno Registry](../debugger/debugging-basics-registers-window.md)