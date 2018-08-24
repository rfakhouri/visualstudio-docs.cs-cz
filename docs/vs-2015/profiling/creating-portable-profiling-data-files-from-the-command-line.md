---
title: Vytváření přenosných datových souborů z příkazového řádku pro profilaci | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 314dc97e5881949ee69131576932db1865969b2c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686755"
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>Vytváření přenosných datových souborů profilace z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vytváření přenosných profilace datových souborů z příkazového řádku](https://docs.microsoft.com/visualstudio/profiling/creating-portable-profiling-data-files-from-the-command-line).  
  
Chcete-li sdílet data profilování snadněji, můžete použít [VSPerfReport](../profiling/vsperfreport.md) nástroj příkazového řádku, chcete-li vložit symboly pro běh profilování do souboru .vsp.  
  
 Můžete také vytvořit předem analyzovaný soubor dat profilování (.vsps), která je menší a rychlejší načítání v integrovaném vývojovém prostředí.  
  
> [!NOTE]
>  Ujistěte se, že soubory symbolů (PDB) jsou k dispozici **VSPerfReport**. Další informace najdete v tématu [postupy: určení umístění souboru se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Informace o cestě k **VSReport**, naleznete v tématu [zadání cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profilování dat v souboru .vsps nelze filtrovat.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Chcete-li vložit symboly pro běh profilování do souboru dat profilování (.vsp)  
  
-   V okně příkazového řádku zadejte následující příkaz:  
  
     \<Cesta >**VSPerfReport \<** verzi souboru VSP >   **/packsymbols**  
  
     Ve výchozím nastavení je název souboru .vsps se základním názvem souboru .vsp. Můžete zadat alternativní název pomocí **výstup** možnost.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Chcete-li vytvořit souhrnné datového souboru profilování  
  
-   V okně příkazového řádku zadejte následující příkaz:  
  
     \<Cesta >**VSPerfReport \<** verzi souboru VSP > **/summaryfile** [**/Output:**\<název souboru >]  
  
     Ve výchozím nastavení je název souboru .vsps se základním názvem souboru .vsp. Můžete zadat alternativní název pomocí **výstup** možnost.



