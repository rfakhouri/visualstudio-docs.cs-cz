---
title: Vytváření přenosných datových souborů z příkazového řádku pro profilaci | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5d343392c9e554c5e51325964949cd3ea13237b8
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63434292"
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>Vytváření přenosných datových souborů profilování z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chcete-li sdílet data profilování snadněji, můžete použít [VSPerfReport](../profiling/vsperfreport.md) nástroj příkazového řádku, chcete-li vložit symboly pro běh profilování do souboru .vsp.  
  
 Můžete také vytvořit předem analyzovaný soubor dat profilování (.vsps), která je menší a rychlejší načítání v integrovaném vývojovém prostředí.  
  
> [!NOTE]
> Ujistěte se, že soubory symbolů (PDB) jsou k dispozici **VSPerfReport**. Další informace najdete v tématu [jak: Zadejte umístění souborů se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
> Informace o cestě k **VSReport**, naleznete v tématu [zadání cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
> Profilování dat v souboru .vsps nelze filtrovat.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Chcete-li vložit symboly pro běh profilování do souboru dat profilování (.vsp)  
  
- V okně příkazového řádku zadejte následující příkaz:  
  
   \<Path><strong>VSPerfReport \<</strong>VSP File> **/PackSymbols**  
  
   Ve výchozím nastavení je název souboru .vsps se základním názvem souboru .vsp. Můžete zadat alternativní název pomocí **výstup** možnost.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Chcete-li vytvořit souhrnné datového souboru profilování  
  
- V okně příkazového řádku zadejte následující příkaz:  
  
   \<Cesta ><strong>VSPerfReport \<</strong> verzi souboru VSP > **/summaryfile** [**/Output:**\<název souboru >]  
  
   Ve výchozím nastavení je název souboru .vsps se základním názvem souboru .vsp. Můžete zadat alternativní název pomocí **výstup** možnost.
