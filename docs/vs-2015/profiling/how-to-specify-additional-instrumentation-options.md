---
title: 'Postupy: určení dalších možností instrumentace | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.property.advanced
helpviewer_keywords:
- instrumentation, options
- profiling tools, session options
- performance sessions, options
ms.assetid: 639afe26-8335-4bd4-8aa5-f2c607b81f07
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1726a8ad414ca6450f056044d520f73021c59f46
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666848"
---
# <a name="how-to-specify-additional-instrumentation-options"></a>Postupy: Určení dalších možností instrumentace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: určení dalších možností instrumentace](https://docs.microsoft.com/visualstudio/profiling/how-to-specify-additional-instrumentation-options).  
  
Vám umožňuje instrumentovat binární soubory z [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] integrované vývojové prostředí (IDE) nebo pomocí nástrojů příkazového řádku. Pokud jste instrumentovali binární soubor z integrovaného vývojového prostředí, můžete určit objem dat shromážděných během instrumentace zadáním dalších možností instrumentace do [VSInstr](../profiling/vsinstr.md) nástroj. Tyto možnosti jsou dostupné na cílové úrovni nebo relace. Například pokud chcete zahrnout nebo vyloučit určité funkce během procesu instrumentace, použijte možnost Další instrumentaci na cílové úrovni.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
> [!IMPORTANT]
>  Každý test, který je vložen mírně změní chování původního programu. Tato změna způsobí, že režii během analýzy. I když je odečtena aproximaci Tato dodatečná režie, má stále drobným časování dopady na aplikací s více vlákny. [VSInstr](../profiling/vsinstr.md) možnosti nápovědy řízení shromažďování dat během profilace nástroj.  
  
### <a name="to-specify-additional-instrumentation-option"></a>Chcete-li určit možnost Další instrumentace  
  
1.  V **prohlížeč výkonu**, vyberte **relace výkonu** a pak klikněte pravým tlačítkem a vyberte **vlastnosti**.  
  
2.  V **stránky vlastností**, klikněte na tlačítko **Upřesnit** vlastnosti.  
  
3.  Zadejte možnosti **dalších možností instrumentace** pole.  
  
     Například použijte /CONTROL:THREAD k určení profilování úrovně. Úplný seznam možností najdete v tématu [VSInstr](../profiling/vsinstr.md).  
  
4.  Klikněte na tlačítko **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)   
 [Profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)



