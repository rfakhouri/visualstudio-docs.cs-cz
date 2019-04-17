---
title: BscMake – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
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
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 05290bed3fe51c69e29d8bafef927c91c63b5249
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59667258"
---
# <a name="bscmake-task"></a>BscMake – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[DŮLEŽITÉ]
>  BscMake – se již nepoužívá v integrovaném vývojovém prostředí sady Visual Studio. Od verze Visual Studio 2008 je automaticky uložené informace o procházení v souboru .sdf ve složce řešení.  
  
 Zabalí nástroj Microsoft procházet informace nástroje pro správu (bscmake.exe).  Nástroj bscmake.exe vytvoří informačního souboru procházení (.bsc) z soubory prohlížeče (.sbr), které jsou vytvořeny během kompilace. Použití **prohlížeče objektů** soubor .bsc. Další informace najdete v tématu [BscMake – referenční dokumentace](http://msdn.microsoft.com/library/b97ad994-1355-4809-98db-6abc12c6fb13).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **BscMake** úloh. Většina úkolů parametry odpovídají možnost příkazového řádku.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**AdditionalOptions**|Volitelné **řetězec** parametru.<br /><br /> Seznam možností, jak je uvedeno na příkazovém řádku. Například "/*možnost1* /*možnost2* /*možnost #*". Tento parametr použijte k určení možností, které nejsou reprezentovány jakýkoli jiný **BscMake** parametr úlohy.<br /><br /> Další informace najdete v tématu Možnosti v [bscmakee – možnosti](http://msdn.microsoft.com/library/fa2f1e06-c684-41cf-80dd-6a554835ebd2).|  
|**OutputFile**|Volitelné **řetězec** parametru.<br /><br /> Určuje název souboru, který přepíše výchozí název výstupního souboru.<br /><br /> Další informace najdete v tématu **/o** možnost [bscmakee – možnosti](http://msdn.microsoft.com/library/fa2f1e06-c684-41cf-80dd-6a554835ebd2).|  
|**PreserveSBR**|Volitelné **logická** parametru.<br /><br /> Pokud `true`, vynutí nepřírůstková sestavení. Bez ohledu na to, jestli soubor .bsc existuje a zabrání soubory .sbr vedlo ke zkrácení dojde k úplné, nepřírůstková sestavení.<br /><br /> Další informace najdete v tématu **/n** možnost [bscmakee – možnosti](http://msdn.microsoft.com/library/fa2f1e06-c684-41cf-80dd-6a554835ebd2).|  
|**Zdroje**|Volitelné **[] ITaskItem** parametru.<br /><br /> Definuje pole objektů položky nástroje MSBuild zdrojových souborů, které lze používat a, protože ho vygeneroval úlohy.|  
|**SuppressStartupBanner**|Volitelné **logická** parametru.<br /><br /> Pokud `true`, zabraňuje zobrazování čísel zprávu o autorských právech a verze při spuštění úlohy.<br /><br /> Další informace najdete v tématu **/nologo** možnost [bscmakee – možnosti](http://msdn.microsoft.com/library/fa2f1e06-c684-41cf-80dd-6a554835ebd2).|  
|**TrackerLogDirectory**|Volitelné **řetězec** parametru.<br /><br /> Určuje adresář protokolu sledovacího modulu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
