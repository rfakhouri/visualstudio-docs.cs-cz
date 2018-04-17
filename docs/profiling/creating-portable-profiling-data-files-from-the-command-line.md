---
title: Vytváření přenosných datových souborů z příkazového řádku profilaci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be653cd134eb54ab61c69553d1e0abe835ea5a59
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>Vytváření přenosných datových souborů profilace z příkazového řádku
Chcete-li sdílení profilace data jednodušší, můžete použít [vsperfreport –](../profiling/vsperfreport.md) nástroj příkazového řádku pro vložení symbolů pro profilace spustit do souboru .vsp.  
  
 Můžete také vytvořit soubor pro předem analyzovaných profilování dat (.vsps), která je menší a rychlejší spouštění v prostředí IDE.  
  
> [!NOTE]
>  Zkontrolujte, zda jsou k dispozici pro soubory symbolu (.pdb) **vsperfreport –**. Další informace najdete v tématu [postupy: určení umístění souboru se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Informace o cestě k **VSReport**, najdete v části [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Data profilování v souboru .vsps nelze filtrovat.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Chcete-li vložit symboly pro profilace spustit do souboru profilování dat (.vsp)  
  
-   V okně příkazového řádku zadejte následující příkaz:  
  
     \<Cesta >**vsperfreport – \<** VSP soubor > **/PackSymbols**  
  
     Ve výchozím nastavení je soubor .vsps stejný základní název souboru .vsp. Můžete zadat alternativní název pomocí **výstup** možnost.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>K vytvoření shrnutí datového souboru profilace  
  
-   V okně příkazového řádku zadejte následující příkaz:  
  
     \<Cesta >**vsperfreport – \<** VSP soubor > **/SummaryFile** [**/výstup:**\<název souboru >]  
  
     Ve výchozím nastavení je soubor .vsps stejný základní název souboru .vsp. Můžete zadat alternativní název pomocí **výstup** možnost.