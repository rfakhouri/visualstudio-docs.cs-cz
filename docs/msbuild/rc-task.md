---
title: RC – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- vc.task.rc
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- RC task (MSBuild (Visual C++))
- MSBuild (Visual C++), RC task
ms.assetid: 2fd26c75-a056-4dda-9f7e-2f90d3748d88
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 700d94742f06605b385577bb92d252ef54e6b3f1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="rc-task"></a>RC – úloha
Zabalí nástroj Microsoft kompilátor prostředků Windows rc.exe. **RC** úloh zkompiluje prostředky, například kurzory, ikony, rastrové obrázky, dialogová okna a písem a do souboru prostředků (.res). Další informace najdete v tématu "Kompilátor prostředků" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry RCtask. Většina úloh parametry a několik sad parametrů, odpovídají možnosti příkazového řádku.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**AdditionalIncludeDirectories**|Volitelné **řetězec []** parametr.<br /><br /> Přidá do seznamu adresáře, které se vyhledávají zahrnout soubory adresář.<br /><br /> Další informace najdete v tématu **/I** možnost [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN.|  
|**AdditionalOptions**|Volitelné **řetězec** parametr.<br /><br /> Seznam například příkazového řádku optionsor **"***nebo možnost 1 /option2 /option#*". Pomocí tohoto parametru lze zadat parametry příkazového řádku, které nejsou reprezentovány jakékoliv **RC** parametr úloh.<br /><br /> Další informace najdete v tématu Možnosti v [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN.|  
|**Jazyková verze**|Volitelné **řetězec** parametr.<br /><br /> Určuje ID národního prostředí, který představuje jazyková verze použitá v prostředcích.<br /><br /> Další informace najdete v tématu **/l** možnost [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN.|  
|**IgnoreStandardIncludePath**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, brání kompilátor prostředků kontrola proměnné prostředí zahrnout při vyhledávání pro soubory hlaviček nebo soubory prostředků.<br /><br /> Další informace najdete v tématu **/x** možnost [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN.|  
|**NullTerminateStrings**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, ukončí všechny řetězce v tabulce řetězec hodnotu null.<br /><br /> Další informace najdete v tématu **/n** možnost [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN.|  
|**PreprocessorDefinitions**|Volitelné **řetězec []** parametr.<br /><br /> Zadejte jeden nebo více preprocesoru symboly pro kompilátor prostředků. Zadejte seznam makro symboly.<br /><br /> Další informace najdete v tématu **/d** možnost [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN. Viz také **UndefinePreprocessorDefinitions** v této tabulce.|  
|**ResourceOutputFileName**|Volitelné **řetězec** parametr.<br /><br /> Určuje název souboru prostředků. Zadejte název souboru prostředků.<br /><br /> Další informace najdete v tématu **/fo** možnost [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN.|  
|**ShowProgress**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, zobrazuje zprávy, které hlásit průběh kompilátoru.<br /><br /> Další informace najdete v tématu **/v** možnost [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN.|  
|**Zdroj**|Požadované `ITaskItem[]` parametr.<br /><br /> Definuje pole MSBuild zdrojového souboru položek, které je možné využívat a vygenerované úlohami.|  
|**SuppressStartupBanner**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.<br /><br /> Další informace získáte zadáním **/?** možnost příkazového řádku a přejděte **/nologo** možnost.|  
|**TrackerLogDirectory**|Volitelné **řetězec** parametr.<br /><br /> Určuje adresář protokolu sledovací modul.|  
|**UndefinePreprocessorDefinitions**|Nedefinované symbol preprocesoru.<br /><br /> Další informace najdete v tématu **/u** možnost [pomocí RC (The RC příkazového řádku)](http://go.microsoft.com/fwlink/?LinkId=155730) na webu MSDN. Viz také **PreprocessorDefinitions** v této tabulce.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)