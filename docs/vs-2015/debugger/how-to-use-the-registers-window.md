---
title: 'Postupy: Použití okna registry | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.registers
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- registers, debugging
- register contents
- flags, Registers window
- register groups
- debugging [Visual Studio], Registers window
- Registers window
ms.assetid: 2918ffa2-562f-40d6-9053-ef321bbeb767
caps.latest.revision: 42
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 233092af638824c462a6d9a47865a1c6f5fd9397
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697470"
---
# <a name="how-to-use-the-registers-window"></a>Postupy: Použití okna registry
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Okno registrů je k dispozici pouze v případě, že je povoleno ladění úrovni adres v **možnosti** dialogovém okně **ladění** uzlu **Obecné** kategorie.  
  
 **Zaregistruje** okně se zobrazí obsah registru. Pokud uchováváte **zaregistruje** okna průběhu prostřednictvím programu open, můžete zobrazit registr hodnoty změnit, jak se spustí váš kód. Hodnoty, které se změnily nedávno se zobrazí červeně. Můžete upravit hodnot registru. Další informace najdete v tématu [jak: Úprava hodnoty registru](../debugger/how-to-edit-a-register-value.md).  
  
 K odebrání nepotřebných prvků, **zaregistruje** okno uspořádá registry do skupiny, které se liší podle platformy a procesor typu. Můžete zobrazit nebo skrýt skupin, jak chcete. Další informace najdete v tématu [jak: Zobrazení a skrytí nabídky registrovat skupiny](../debugger/how-to-display-and-hide-register-groups.md).  
  
 Podrobný úvod ke konceptům za registry a o okně registr, najdete v části [základní informace o ladění: Registr – okno](../debugger/debugging-basics-registers-window.md).  
  
> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-display-the-registers-window"></a>Chcete-li zobrazit okno registrů  
  
- Na **ladění** nabídce zvolte **Windows**a klikněte na tlačítko **zaregistruje**.  
  
     Ladicí program musí být spuštěná nebo v režimu pozastavení.  
  
    > [!NOTE]
    > Informace o registru není k dispozici pro skript nebo aplikace SQL.  
  
## <a name="see-also"></a>Viz také  
 [Základy ladění: Registr – okno](../debugger/debugging-basics-registers-window.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Základy ladění: Okno Registry](../debugger/debugging-basics-registers-window.md)
