---
title: 'Postupy: Ladění ovládacího prvku ActiveX | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
ms.openlocfilehash: 036e50fde887786736aee1e7f8565cc9708bb2e7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53924784"
---
# <a name="how-to-debug-an-activex-control"></a>Postupy: Ladění ovládacího prvku ActiveX

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte nastavení importu a exportu v nabídce Nástroje. Další informace najdete v tématu [Resetovat nastavení](../ide/environment-settings.md#reset-settings).

Chcete-li ladit ovládací prvek ActiveX, je nutné zadat (spustitelného souboru) pro ovládací prvek pro spuštění v kontejneru.

## <a name="to-specify-a-container-for-the-debug-session"></a>K určení kontejneru se pro relaci ladění

1.  V Průzkumníku řešení vyberte projekt.

2.  Z **zobrazení** nabídce zvolte **stránky vlastností**.

3.  V **stránky vlastností projektu** dialogovém okně Otevřít **vlastnosti konfigurace** a pak zvolte položku **ladění**.

4.  V části **ladění** kategorie, vyhledejte **příkaz** vlastnost.

5.  Zadejte název cesty pro kontejner. Například C:\Program Files\Internet Explorer\IEXPLORE. SOUBOR EXE.

6.  Pokud zadáte jako kontejner aplikace Internet Explorer a používáte aktivní plochu, zadejte `/new` v **argumenty příkazu** pole.

7.  Klikněte na **OK**.

     Pokud nezadáte kontejner ve službě **stránky vlastností projektu** dialogovém okně můžete zadat kontejner při zahájení ladění. Po výběru příkazu ke spuštění pro spuštění ladění, [spustitelný soubor pro dialogové okno ladění relace](../debugger/executable-for-debugging-session-dialog-box.md) se zobrazí. V dialogovém okně zadejte název cesty kontejneru.

## <a name="see-also"></a>Viz také

- [ActiveX – ovládací prvky](/cpp/mfc/activex-controls)
- [Testování vlastností a událostí pomocí testovacího kontejneru](/cpp/mfc/testing-properties-and-events-with-test-container)
- [Ladění modelů COM a prvků ActiveX](../debugger/com-and-activex-debugging.md)
- [Ladění v sadě Visual Studio](../debugger/index.md)
- [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)