---
title: XDCMake – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- vc.task.xdcmake
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- XDCMake task (MSBuild (Visual C++))
- MSBuild (Visual C++), XDCMake task
ms.assetid: a7de9c64-903a-4a02-85f3-f37672270f25
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dab82b3ddf2bc39d1253321a335e1fe838235819
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="xdcmake-task"></a>XDCMake – úloha
Zabalí nástroj dokumentace XML (xdcmake.exe), která sloučí soubory komentář (projektový) dokumentu XML do souboru .xml.  
  
 Projektový soubor se vytvoří při poskytování dokumentační komentáře ve Visual C++ zdrojového kódu a kompilace pomocí [/doc](/cpp/build/reference/doc-process-documentation-comments-c-cpp) – možnost kompilátoru. Další informace najdete v tématu [referenční dokumentace nástroje XDCMake](/cpp/ide/xdcmake-reference), [stránky vlastností nástroje Generátor dokumentů XML](/cpp/ide/xml-document-generator-tool-property-pages)a možnost Nápověda příkazového řádku (**/?**) pro xdcmake.exe.  
  
## <a name="remarks"></a>Poznámky  
 Ve výchozím nastavení nástroj xdcmake.exe podporuje několik možností příkazového řádku. Další možnosti jsou podporované, když zadáte **/staré** možnost příkazového řádku.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **XDCMake** úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**AdditionalDocumentFile**|Volitelné **řetězec []** parametr.<br /><br /> Určuje jeden nebo více dalších soubory sloučit.<br /><br /> Další informace najdete v tématu **další soubory dokumentu** popis v [stránky vlastností nástroje Generátor dokumentů XML](/cpp/ide/xml-document-generator-tool-property-pages). Viz také **/staré** a **/Fs** možnosti příkazového řádku pro xdcmake.exe.|  
|**AdditionalOptions**|Volitelné **řetězec** parametr.<br /><br /> Seznam možností jako zadaného na příkazovém řádku. Například "*/option1 /option2 /option#*". Tento parametr použijte k určení možnosti, které nejsou reprezentovány jakékoliv **XDCMake** parametr úloh.<br /><br /> Další informace najdete v tématu [referenční dokumentace nástroje XDCMake](/cpp/ide/xdcmake-reference), [stránky vlastností nástroje Generátor dokumentů XML](/cpp/ide/xml-document-generator-tool-property-pages)a Nápověda příkazového řádku (**/?**) pro xdcmake.exe.|  
|**DocumentLibraryDependencies**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true` a aktuální projekt má závislost na projekt statické knihovny (LIB) v řešení, soubory pro tento projekt knihovny jsou součástí výstup souboru .xml aktuálního projektu.<br /><br /> Další informace najdete v tématu **závislosti knihovny dokumentů** popis v [stránky vlastností nástroje Generátor dokumentů XML](/cpp/ide/xml-document-generator-tool-property-pages).|  
|**Výstupní soubor**|Volitelné **řetězec** parametr.<br /><br /> Přepíše výchozí název výstupního souboru. Výchozí název je odvozená od název první projektový soubor, který se zpracovává.<br /><br /> Další informace najdete v tématu **/out:** `filename` možnost [referenční dokumentace nástroje XDCMake](/cpp/ide/xdcmake-reference). Viz také **/staré** a **/Fo** možnosti příkazového řádku pro xdcmake.exe.|  
|**ProjectName**|Volitelné **řetězec** parametr.<br /><br /> Název aktuálního projektu.|  
|**SlashOld**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, umožňuje xdcmake.exe Další možnosti.<br /><br /> Další informace najdete v tématu **/staré** možnost příkazového řádku pro xdcmake.exe.|  
|**Zdroje**|Požadované `ITaskItem[]` parametr.<br /><br /> Definuje pole MSBuild zdrojového souboru položek, které je možné využívat a vygenerované úlohami.|  
|**SuppressStartupBanner**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.<br /><br /> Další informace najdete v tématu **/nologo** možnost [referenční dokumentace nástroje XDCMake](/cpp/ide/xdcmake-reference).|  
|**TrackerLogDirectory**|Volitelné **řetězec** parametr.<br /><br /> Určuje adresář pro protokol sledovací modul.|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)