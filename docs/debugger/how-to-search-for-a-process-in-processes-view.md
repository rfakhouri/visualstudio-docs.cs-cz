---
title: 'Postupy: Hledání procesu v zobrazení procesů | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Processes view
- processes, searching for
ms.assetid: 7cb97b37-4a95-4f1b-9eee-4910aa9c115b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2c9cd618768268b5c0bc4e3e99fbffd4fd65e874
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56715086"
---
# <a name="how-to-search-for-a-process-in-processes-view"></a>Postupy: Hledání procesu v zobrazení procesů
Můžete vyhledat konkrétního procesu v zobrazení procesů pomocí jeho ID nebo modul řetězec proces jako kritéria hledání. Můžete také zadat počáteční směr hledání. Pole v dialogovém okně se zobrazí atributy vybraný proces strom procesu.

### <a name="to-search-for-a-process-in-processes-view"></a>Hledání procesu v zobrazení procesů

1. Uspořádat okna tak tohoto nástroje Spy ++ a aktivní [zobrazení procesy](../debugger/processes-view.md) okna jsou viditelné.

2. Z **hledání** nabídce zvolte **najít proces**

    [Dialogové okno hledání procesů](../debugger/process-search-dialog-box.md) otevře.

3. Zadejte ID procesu nebo řetězce modulu, jako kritéria hledání.

4. Zrušte zaškrtnutí všech polí, u kterých nechcete k určení hodnot.

   > [!TIP]
   >  Pokud chcete najít všechny procesy vlastní modul, zrušte **procesu** pole a zadejte název modulu v **modulu** pole. Pak pomocí **najít další** chcete pokračovat ve vyhledávání pro procesy.

5. Zvolte **nahoru** nebo **dolů** pro počáteční směr hledání.

6. Klikněte na **OK**.

   Pokud je nalezen odpovídající proces, je zvýrazněn **zobrazení procesů** okna.