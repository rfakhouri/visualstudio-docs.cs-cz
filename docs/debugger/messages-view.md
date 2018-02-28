---
title: "Zobrazení zpráv | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.externaltools.spyplus.messagesview
helpviewer_keywords:
- Messages view
ms.assetid: 14c2a786-c23a-4b2d-acad-8c32a856c70d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c421b7c22bed32e6c60d30098b2c19e0d71a0af3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="messages-view"></a>Zobrazení zpráv
Každé okno má datového proudu k přidružených zpráv. Okno zobrazení zprávy zobrazí tento datový proud zpráv. Popisovač okna, kód zprávy a zpráva se zobrazí. Můžete vytvořit zobrazení zprávy pro přístup z více vláken nebo proces stejně. To vám umožní zobrazit zprávy odeslané do vlastní konkrétní proces nebo podproces, který je obzvláště užitečné pro zaznamenání zprávy oken inicializace všechny systémy windows.  
  
 Typické okno zobrazení zprávy, zobrazí se dole. Všimněte si, že první sloupec popisovač okna a druhý sloupec obsahuje kód zprávy (podrobně [kódy zpráv](../debugger/message-codes.md)). Dekódované zpráva parametry a návratové hodnoty jsou na pravé straně.  
  
 ![Spy & č. 43; & č. 43; Zobrazení zpráv](../debugger/media/spy--_messagesview.png "nástroje Spy ++ _MessagesView")  
Zobrazení zpráv nástroje Spy ++  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-open-a-messages-view-for-a-window-process-or-thread"></a>Chcete-li otevřít zobrazení zprávy pro okno, procesu nebo přístup z více vláken  
  
1.  Přesunout fokus [zobrazení oken](../debugger/windows-view.md), [zobrazení procesů](../debugger/processes-view.md), nebo [zobrazení vláken](../debugger/threads-view.md) okno.  
  
2.  Najít uzel pro položku jejichž zprávy, které chcete prověřit a vyberte jej.  
  
3.  Z **Spy** nabídce zvolte **zprávy protokolu**.  
  
     [Dialogové okno možností zpráv](../debugger/message-options-dialog-box.md) otevře.  
  
4.  Vyberte možnosti pro zprávu, kterou chcete zobrazit.  
  
5.  Stiskněte klávesu **OK** k zahájení protokolování zpráv.  
  
     Otevře se okno zobrazení zprávy a **zprávy** nabídky se přidá do panelu nástrojů nástroje Spy ++. V závislosti na vybrané možnosti se zprávy začít, streamování do aktivního okna zobrazení zprávy.  
  
6.  Pokud máte dostatek zprávy, zvolte **zastavení protokolování** z **zprávy** nabídky.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Řízení zobrazení zpráv](../debugger/how-to-control-messages-view.md)  
 Vysvětluje, jak spravovat zobrazení zpráv.  
  
 [Otevření zobrazení zpráv z vyhledávacího okna](../debugger/how-to-open-messages-view-from-find-window.md)  
 Vysvětluje, jak k otevření zobrazení zpráv z dialogového okna Najít.  
  
 [Hledání zprávy v zobrazení zpráv](../debugger/how-to-search-for-a-message-in-messages-view.md)  
 Vysvětluje, jak vyhledat konkrétní zprávu v zobrazení zpráv.  
  
 [Spuštění a zastavení displeje protokolu zpráv](../debugger/how-to-start-and-stop-the-message-log-display.md)  
 Vysvětluje, jak spuštění a zastavení protokolování zpráv.  
  
 [Kódy zpráv](../debugger/message-codes.md)  
 Definuje kódy pro zprávy, které jsou uvedené v zobrazení zpráv.  
  
 [Zobrazení vlastností zpráv](../debugger/how-to-display-message-properties.md)  
 Jak zobrazit další informace o zprávu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Zobrazení nástroje Spy++](../debugger/spy-increment-views.md)  
 Popisuje zobrazení stromů nástroje Spy ++ systému windows, zprávy, procesy a vláken.  
  
 [Použití nástroje Spy++](../debugger/using-spy-increment.md)  
 Nabízí nástroje Spy ++ a vysvětluje, jak lze použít.  
  
 [Dialogové okno možností zpráv](../debugger/message-options-dialog-box.md)  
 Slouží k výběru zprávy, které jsou uvedeny v aktivním zobrazení zprávy.  
  
 [Dialogové okno hledání zpráv](../debugger/message-search-dialog-box.md)  
 Použít k vyhledání uzlu pro konkrétní zprávy v zobrazení zpráv.  
  
 [Dialogové okno vlastností zpráv](../debugger/message-properties-dialog-box.md)  
 Slouží k zobrazení vlastností zpráv vybraném v zobrazení zpráv.  
  
 [Referenční dokumentace nástroje Spy++](../debugger/spy-increment-reference.md)  
 Obsahuje části popisující každého nástroje Spy ++ nabídky a dialogové okno pole.