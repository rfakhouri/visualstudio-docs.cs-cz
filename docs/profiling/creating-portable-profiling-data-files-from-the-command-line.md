---
title: Vytváření přenosných datových souborů z příkazového řádku pro profilaci | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b42e34aa2ab52ffea835e6c3ef513cf3d7227a4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54926880"
---
# <a name="create-portable-profiling-data-files-from-the-command-line"></a>Vytváření přenosných datových souborů profilace z příkazového řádku
Chcete-li sdílet data profilování snadněji, můžete použít [VSPerfReport](../profiling/vsperfreport.md) vložit symboly pro běh profilování do nástroje příkazového řádku. *Vsp* souboru.  
  
 Můžete také vytvořit předem analyzovaný dat profilování (. *vsps*) soubor, který je menší a rychlejší načítání v integrovaném vývojovém prostředí.  
  
> [!NOTE]
>  Ujistěte se, že symbol (. *soubor PDB*) soubory jsou k dispozici **VSPerfReport**. Další informace najdete v tématu [jak: Zadejte umístění souborů se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Informace o cestě k **VSReport**, naleznete v tématu [zadejte cestu k nástroji příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Profilování dat v. *vsps* souboru se nedají filtrovat.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Chcete-li vložit symboly pro běh profilování do dat profilování (. *Vsp*) souboru  
  
- V okně příkazového řádku zadejte následující příkaz:  
  
   \<Path><strong>VSPerfReport \<</strong>VSP File> **/PackSymbols**  
  
   Ve výchozím nastavení. *vsps* soubor má název základní názvem. *Vsp* souboru. Můžete zadat alternativní název pomocí **výstup** možnost.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Chcete-li vytvořit souhrnné datového souboru profilování  
  
- V okně příkazového řádku zadejte následující příkaz:  
  
   \<Cesta ><strong>VSPerfReport \<</strong> verzi souboru VSP > **/summaryfile** [**/Output:**\<název souboru >]  
  
   Ve výchozím nastavení. *vsps* soubor má název základní názvem. *Vsp* souboru. Můžete zadat alternativní název pomocí **výstup** možnost.