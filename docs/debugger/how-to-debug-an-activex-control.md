---
title: 'Postupy: ladění ovládacího prvku ActiveX | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.controls.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- testing [Visual Studio], test containers
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- data-bound controls, ActiveX
- test container
- containers, specifying for debug sessions
- ActiveX controls, debugging
- testing [Visual Studio], ActiveX controls
ms.assetid: bbc02cf7-a7e6-44fe-99af-87a43e1d7251
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8892d83bb92198b9e8f1b7df1293a06f27d27716
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-debug-an-activex-control"></a>Postupy: Ladění ovládacího prvku ActiveX
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, vyberte v nabídce Nástroje pro nastavení importu a exportu. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
 Chcete-li ladit vaše ovládací prvek ActiveX, musíte zadat (spustitelné) pro spuštění ovládacího prvku kontejner.  
  
### <a name="to-specify-a-container-for-the-debug-session"></a>K určení kontejneru pro relaci ladění  
  
1.  V Průzkumníku řešení vyberte projekt.  
  
2.  Z **zobrazení** nabídce zvolte **stránky vlastností**.  
  
3.  V **stránek vlastností projektu** dialogové okno, otevřete **vlastnosti konfigurace** složky a vyberte **ladění**.  
  
4.  V části **ladění** kategorie, vyhledejte **příkaz** vlastnost.  
  
5.  Zadejte název cesty pro příslušný kontejner. Například C:\Program Files\Internet Explorer\IEXPLORE. SOUBOR EXE.  
  
6.  Pokud zadáte Internet Explorer jako kontejner a používáte aktivní plochu, zadejte `/new` v **argumenty příkazu** pole.  
  
7.  Click **OK**.  
  
     Pokud nezadáte kontejner ve **stránek vlastností projektu** dialogové okno, můžete zadat kontejner, abyste před zahájením ladění. Když vyberete provedení příkazu spusťte ladění, [spustitelný soubor pro dialogové okno ladění relace](../debugger/executable-for-debugging-session-dialog-box.md) se zobrazí. V dialogovém okně zadejte název cesty kontejneru.  
  
## <a name="see-also"></a>Viz také  
 [ActiveX – ovládací prvky](/cpp/mfc/activex-controls)   
 [Testování vlastností a událostí pomocí testovacího kontejneru](/cpp/mfc/testing-properties-and-events-with-test-container)   
 [COM a prvků ActiveX ladění](../debugger/com-and-activex-debugging.md)   
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)