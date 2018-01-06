---
title: "BscMake – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.task.bscmake
- VC.Project.VCBscMakeTool.PreserveSBR
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), tasks
- BscMake task (MSBuild (Visual C++))
ms.assetid: bb98fc67-cad8-43a7-9598-60df6d734db2
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2308e1efecf01972dd494ce7ad4341e8e5d6d20e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="bscmake-task"></a>BscMake – úloha
> [!IMPORTANT]
>  BscMake je již používán Visual Studio IDE. Od verze Visual Studio 2008 je procházet informace uloženy v soubor SDF ve složce řešení automaticky.  
  
 Zabalí nástroj Microsoft procházet údržby nástroje pro konfiguraci (bscmake.exe).  Nástroj bscmake.exe vytvoří soubor informace o procházení (.bsc) ze zdrojových prohlížeč souborů (.sbr), které jsou vytvořené během kompilace. Použití **Prohlížeč objektů** k zobrazení souboru BSC programem. Další informace najdete v tématu [BscMake – odkaz](/cpp/build/reference/bscmake-reference).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **BscMake** úloh. Většina úloh parametry odpovídají možnosti příkazového řádku.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**AdditionalOptions**|Volitelné **řetězec** parametr.<br /><br /> Seznam možností jako zadaného na příkazovém řádku. Například "/*možnost 1* /*option2* /*možnost #*". Tento parametr použijte k určení možnosti, které nejsou reprezentovány jakékoliv **BscMake** parametr úloh.<br /><br /> Další informace najdete v tématu Možnosti v [možnosti BSCMAKE](/cpp/build/reference/bscmake-options).|  
|**Výstupní soubor**|Volitelné **řetězec** parametr.<br /><br /> Určuje název souboru, který přepíše výchozí název výstupního souboru.<br /><br /> Další informace najdete v tématu **/o** možnost [možnosti BSCMAKE](/cpp/build/reference/bscmake-options).|  
|**PreserveSBR**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, vynutí nonincremental sestavení. Bez ohledu na to, jestli souboru BSC existuje a zabrání ke zkrácení soubory .sbr dojde k úplné, nonincremental sestavení.<br /><br /> Další informace najdete v tématu  **/n**  možnost [možnosti BSCMAKE](/cpp/build/reference/bscmake-options).|  
|**Zdroje**|Volitelné **[ITaskItem]** parametr.<br /><br /> Definuje pole MSBuild zdrojového souboru položek, které je možné využívat a vygenerované úlohami.|  
|**SuppressStartupBanner**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.<br /><br /> Další informace najdete v tématu **/nologo** možnost [možnosti BSCMAKE](/cpp/build/reference/bscmake-options).|  
|**TrackerLogDirectory**|Volitelné **řetězec** parametr.<br /><br /> Určuje adresář pro protokol sledovací modul.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)