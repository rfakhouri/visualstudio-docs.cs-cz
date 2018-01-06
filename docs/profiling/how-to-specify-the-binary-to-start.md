---
title: "Postupy: určení binárního souboru spuštění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
ms.assetid: ba77fcf4-8d78-49f1-b8f3-7dd0acf84306
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5d17c59c44dc64b2e3fa3e53553a65ee9998b7ff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-binary-to-start"></a>Postupy: Určení binárního souboru ke spuštění
K profilu binární soubory například knihovny DLL, je třeba zadat informace v  **\<cíl > stránky vlastností** dialogové okno. Tyto informace označuje, kde je volající aplikace projektu knihovny DLL.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
### <a name="to-specify-the-executable-to-start"></a>K určení spustitelného souboru spuštění  
  
1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na cílový binární soubor a pak klikněte na tlačítko **vlastnosti**.  
  
2.  V **stránky vlastností** dialogové okno, klikněte **spusťte** vlastnosti.  
  
3.  Vyberte **přepsat vlastnosti projektu** zaškrtávací políčko.  
  
4.  V **spustitelný soubor spustit** textové pole, zadejte umístění souborů.  
  
5.  V **argumenty** textové pole, zadejte argumenty, které jsou nezbytné ke spuštění aplikace.  
  
6.  V **pracovní adresář** textové pole, zadejte umístění adresáře.  
  
7.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)