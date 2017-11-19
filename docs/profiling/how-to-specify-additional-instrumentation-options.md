---
title: "Postupy: určení dalších možností instrumentace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.advanced
helpviewer_keywords:
- instrumentation, options
- profiling tools, session options
- performance sessions, options
ms.assetid: 639afe26-8335-4bd4-8aa5-f2c607b81f07
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 59bc7f5a03577c00d6c085ff1a6861e73eda2f71
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-specify-additional-instrumentation-options"></a>Postupy: Určení dalších možností instrumentace
Můžete instrumentace binárních souborů z [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] integrované vývojové prostředí (IDE) nebo pomocí nástroje příkazového řádku. Pokud jste instrumentace binárního souboru z integrovaného vývojového prostředí, můžete řídit objem dat, které jsou shromážděny během instrumentace zadáním dalších možností instrumentace na [vsinstr –](../profiling/vsinstr.md) nástroj. Tyto možnosti jsou dostupné na úrovni cíl nebo relace. Například pokud chcete zahrnout nebo vyloučit konkrétní funkce během procesu instrumentace, použijte parametr další instrumentace na cílové úrovni.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!IMPORTANT]
>  Každý test, který je vložen mírně změní chování programu původní. Tato úprava způsobí, že režii během analýzy. I když je odečten sblížení Tato dodatečná režie, má stále jemně časování důsledky pro vícevláknové aplikace. [Vsinstr –](../profiling/vsinstr.md) nástroj Možnosti nápovědy řízení shromažďování dat při vytváření profilu.  
  
### <a name="to-specify-additional-instrumentation-option"></a>Chcete-li určit možnost Další instrumentace  
  
1.  V **prohlížeč výkonu**, vyberte **výkonnostní relace** a potom klikněte pravým tlačítkem a vyberte **vlastnosti**.  
  
2.  V **vlastnosti stránky**, klikněte **Upřesnit** vlastnosti.  
  
3.  Zadejte možnosti v **dalších možností instrumentace** pole.  
  
     /CONTROL:THREAD můžete například použijte k určení profilování úrovně. Úplný seznam možností najdete v tématu [vsinstr –](../profiling/vsinstr.md).  
  
4.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)