---
title: Vytváření přenosných datových souborů z příkazového řádku profilaci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 25f2faf1be7f2e8ff5c96eca16ef2de9be2514db
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815836"
---
# <a name="create-portable-profiling-data-files-from-the-command-line"></a>Vytváření přenosných datových souborů profilace z příkazového řádku
Chcete-li sdílení profilace data jednodušší, můžete použít [vsperfreport –](../profiling/vsperfreport.md) nástroj příkazového řádku pro vložení symbolů pro profilaci k. *Vsp* souboru.  
  
 Můžete také vytvořit předem analyzovaných data profilování (. *vsps*) souboru, který je menší a je rychlejší spouštění v prostředí IDE.  
  
> [!NOTE]
>  Zajistěte, aby symbol (. *pdb*) jsou k dispozici pro soubory **vsperfreport –**. Další informace najdete v tématu [postupy: určení umístění souboru se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Informace o cestě k **VSReport**, najdete v části [zadejte cestu k nástroje příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Data profilování v. *vsps* soubor nelze filtrovat.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Chcete-li vložit symboly pro profilaci k data profilování (. *Vsp*) souboru  
  
-   V okně příkazového řádku zadejte následující příkaz:  
  
     \<Cesta >**vsperfreport – \<** VSP soubor > **/PackSymbols**  
  
     Ve výchozím nastavení. *vsps* názvem souboru s názvem základní. *Vsp* souboru. Můžete zadat alternativní název pomocí **výstup** možnost.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>K vytvoření shrnutí datového souboru profilace  
  
-   V okně příkazového řádku zadejte následující příkaz:  
  
     \<Cesta >**vsperfreport – \<** VSP soubor > **/SummaryFile** [**/výstup:**\<název souboru >]  
  
     Ve výchozím nastavení. *vsps* názvem souboru s názvem základní. *Vsp* souboru. Můžete zadat alternativní název pomocí **výstup** možnost.