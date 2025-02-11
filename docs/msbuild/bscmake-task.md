---
title: BscMake – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 27315682c26769ea5c529ceb21c99458c86f0220
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63385818"
---
# <a name="bscmake-task"></a>BscMake – úloha
> [!IMPORTANT]
> BscMake – se již nepoužívá v integrovaném vývojovém prostředí sady Visual Studio. Od verze Visual Studio 2008, je automaticky v uložené informace o procházení *SDF* ve *řešení* složky.

 Zabalí nástroj Microsoft procházet informace nástroje pro správu (*bscmake.exe*).  *Bscmake.exe* vytvoří nástroj informačního souboru procházení (*.bsc*) ze zdrojové soubory prohlížeče (*.sbr*), které jsou vytvořeny během kompilace. Použití **prohlížeče objektů** zobrazíte *.bsc* souboru. Další informace najdete v tématu [BscMake – referenční dokumentace](/cpp/build/reference/bscmake-reference).

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry **BscMake** úloh. Většina úkolů parametry odpovídají možnost příkazového řádku.

|Parametr|Popis|
|---------------|-----------------|
|**AdditionalOptions**|Volitelné **řetězec** parametru.<br /><br /> Seznam možností, jak je uvedeno na příkazovém řádku. Třeba /\<možnost1 > /\<možnost2 > /\<možnost #>. Tento parametr použijte k určení možností, které nejsou reprezentovány jakýkoli jiný **BscMake** parametr úlohy.<br /><br /> Další informace najdete v tématu Možnosti v [bscmakee – možnosti](/cpp/build/reference/bscmake-options).|
|**OutputFile**|Volitelné **řetězec** parametru.<br /><br /> Určuje název souboru, který přepíše výchozí název výstupního souboru.<br /><br /> Další informace najdete v tématu **/o** možnost [bscmakee – možnosti](/cpp/build/reference/bscmake-options).|
|**PreserveSBR**|Volitelné **logická** parametru.<br /><br /> Pokud `true`, vynutí nepřírůstková sestavení. Bez ohledu na to, zda dojde k úplné, nepřírůstková sestavení *.bsc* soubor existuje a zabraňuje *.sbr* soubory z vedlo ke zkrácení.<br /><br /> Další informace najdete v tématu **/n** možnost [bscmakee – možnosti](/cpp/build/reference/bscmake-options).|
|**Zdroje**|Volitelné **[] ITaskItem** parametru.<br /><br /> Definuje pole objektů položky nástroje MSBuild zdrojových souborů, které lze používat a, protože ho vygeneroval úlohy.|
|**SuppressStartupBanner**|Volitelné **logická** parametru.<br /><br /> Pokud `true`, zabraňuje zobrazování čísel zprávu o autorských právech a verze při spuštění úlohy.<br /><br /> Další informace najdete v tématu **/nologo** možnost [bscmakee – možnosti](/cpp/build/reference/bscmake-options).|
|**TrackerLogDirectory**|Volitelné **řetězec** parametru.<br /><br /> Určuje adresář protokolu sledovacího modulu.|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)