---
title: 'Postupy: Hledání zprávy v zobrazení zpráv | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Message Search dialog box
- Messages view
- messages, searching for
ms.assetid: 732b7ccc-54ea-41db-823b-2b96e3e4083e
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 34f50b457dcc8b6db8e48e7072e8956fa78f6a7a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54761679"
---
# <a name="how-to-search-for-a-message-in-messages-view"></a>Postupy: Hledání zprávy v zobrazení zpráv
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete vyhledat konkrétní zprávy v zobrazení zpráv s použitím jeho popisovač, typ nebo ID zprávy jako kritéria hledání. Některou z těchto – nebo ke kombinaci – bude platný vyhledávací kritéria. Je taky možné specifikovat Počáteční směr hledání. Atributy zprávu aktuálně vybranou se předem načtou pole v dialogovém okně.  
  
### <a name="to-search-for-a-message-in-messages-view"></a>Hledání zprávy v zobrazení zpráv  
  
1. Uspořádat okna tak tohoto nástroje Spy ++ a aktivní [zobrazení zpráv](../debugger/messages-view.md) okna jsou viditelné.  
  
2. Z **hledání** nabídce zvolte **najít zprávu**.  
  
    [Dialogové okno hledání zpráv](../debugger/message-search-dialog-box.md) otevře.  
  
3. Přetáhněte **tažením nástroje hledání** požadované období. Při přetahování nástroj, **hledání zpráv** dialogové okno zobrazí podrobnosti o vybrané okno.  
  
    – nebo –  
  
    Pokud máte popisovač okna jejichž zprávy, které chcete prověřit, zadejte ho do **zpracování** textového pole.  
  
    – nebo –  
  
    Pokud víte, typ nebo ID zprávy, které chcete, vyberte z **typ** a **zpráva** rozevíracích nabídek a zrušte **zpracování** textového pole.  
  
4. Zrušte zaškrtnutí všech polí, u kterých nechcete k určení hodnot.  
  
   > [!TIP]
   >  Chcete-li přehlednost obrazovky, vyberte **skrýt Spy** možnost. Tato možnost ukrývá hlavním nástroje Spy ++ okně byste museli opustit pouze **najít okno** dialogové okno viditelné nad vaší aplikace. Obnovení hlavního okna nástroje Spy ++, po kliknutí na **OK** nebo **zrušit**, nebo pokud zrušíte výběr **skrýt Spy ++** možnost.  
  
5. Zvolte **nahoru** nebo **dolů** pro počáteční směr hledání.  
  
6. Klikněte na **OK**.  
  
   Pokud je nalezen odpovídající zprávu, je zvýrazněn v okně zobrazení zprávy. Zobrazit [zobrazení zpráv](../debugger/messages-view.md).
