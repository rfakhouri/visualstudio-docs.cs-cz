---
title: Vytváření přenosných datových souborů z příkazového řádku pro profilaci | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 01b373fbe8a9aa0d7154f03855bb95472edf6b28
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53959712"
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
  
   \<Cesta ><strong>VSPerfReport \<</strong> verzi souboru VSP >   **/packsymbols**  
  
   Ve výchozím nastavení. *vsps* soubor má název základní názvem. *Vsp* souboru. Můžete zadat alternativní název pomocí **výstup** možnost.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Chcete-li vytvořit souhrnné datového souboru profilování  
  
- V okně příkazového řádku zadejte následující příkaz:  
  
   \<Cesta ><strong>VSPerfReport \<</strong> verzi souboru VSP > **/summaryfile** [**/Output:**\<název souboru >]  
  
   Ve výchozím nastavení. *vsps* soubor má název základní názvem. *Vsp* souboru. Můžete zadat alternativní název pomocí **výstup** možnost.