---
title: "Postupy: přemístění instrumentovaných binárních souborů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.binaries
helpviewer_keywords:
- binaries, instrumented
- instrumentation, instrumented binaries
- instrumented binaries and relocating
- profiling tools, instrumented binaries
ms.assetid: 258f49e8-4b09-477e-a132-8fad685b66f4
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 72c15bfc5449a1dab516be217da4a76276312fd3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-relocate-instrumented-binaries"></a>Postupy: Přemístění instrumentovaných binárních souborů
Během instrumentace sondy vloženy do binárního souboru k měření výkonu aplikace. Výběrem přesunovat instrumentované binární je kopii původní binární instrumentovány a put v zadaném umístění. Tato možnost je užitečná, pokud nechcete, aby profileru přejmenovat vašeho původního binární. Pokud není přemístění binárního souboru, původní verze binárního souboru se přepíše.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
### <a name="to-relocate-instrumented-binary"></a>Instrumentované binární přesunovat  
  
1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.  
  
2.  V **stránky vlastností**, klikněte **binární** vlastnosti.  
  
3.  Vyberte **přemístění instrumentovaných binárních souborů** zaškrtávací políčko.  
  
4.  Zadejte umístění pro instrumentované binární.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [VSInstr](../profiling/vsinstr.md)