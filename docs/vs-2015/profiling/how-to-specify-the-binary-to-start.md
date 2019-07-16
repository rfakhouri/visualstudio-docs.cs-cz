---
title: 'Postupy: Určení binárního souboru ke spuštění | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
ms.assetid: ba77fcf4-8d78-49f1-b8f3-7dd0acf84306
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 919e84393cf4aef929a504aadbefe905afe24bfb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203426"
---
# <a name="how-to-specify-the-binary-to-start"></a>Postupy: Zadání binárního souboru ke spuštění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pro binární soubory profilu například knihovny DLL, je třeba zadat informace v  **\<cíl > stránky vlastností** dialogové okno. Tato informace indikuje, kde najít projekt knihovny DLL volající aplikace.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
### <a name="to-specify-the-executable-to-start"></a>K určení spustitelného souboru spusťte  
  
1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na cílový binární soubor a potom klikněte na tlačítko **vlastnosti**.  
  
2. V **stránky vlastností** dialogové okno, klikněte na tlačítko **spuštění** vlastnosti.  
  
3. Vyberte **přepsat vlastnosti projektu** zaškrtávací políčko.  
  
4. V **spustitelný soubor ke spuštění** textové pole, zadejte umístění souboru.  
  
5. V **argumenty** textové pole, zadejte argumenty, které jsou vyžadovány pro spuštění aplikace.  
  
6. V **pracovní adresář** textové pole, zadejte umístění adresáře.  
  
7. Klikněte na **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
