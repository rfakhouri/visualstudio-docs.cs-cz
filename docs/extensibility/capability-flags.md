---
title: Příznaky schopností | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, capability flags
ms.assetid: a3f6071c-eac8-4bcd-8ffd-8d0a2d24a252
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d9be7a6a6d1b4ff389859ac2d3ed4aef2c1b0488
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="capability-flags"></a>Příznaky schopností
SCC_CAP_*xxx* příznaky jsou bitové příznaky, které slouží k určení možností modulu plug-in Správa zdrojového kódu. SCC_EXCAP_*xxx* příznaky jsou přírůstkové příznaky, které označují rozšířené schopnosti a odkazující na celočíselnou hodnotu.  
  
|Funkce kódu|Hodnota|Popis|  
|---------------------|-----------|-----------------|  
|`SCC_CAP_REMOVE`|0x00000001L|Podporuje [SccRemove](../extensibility/sccremove-function.md) a příkaz.|  
|`SCC_CAP_RENAME`|0x00000002L|Podporuje [SccRename](../extensibility/sccrename-function.md) a příkaz.|  
|`SCC_CAP_DIFF`|0x00000004L|Podporuje [SccDiff](../extensibility/sccdiff-function.md) a příkaz.|  
|`SCC_CAP_HISTORY`|0x00000008L|Podporuje [SccHistory](../extensibility/scchistory-function.md) a příkaz.|  
|`SCC_CAP_PROPERTIES`|0x00000010L|Podporuje [SccProperties](../extensibility/sccproperties-function.md) a příkaz.|  
|`SCC_CAP_RUNSCC`|0x00000020L|Podporuje [SccRunScc](../extensibility/sccrunscc-function.md) a příkaz.|  
|`SCC_CAP_GETCOMMANDOPTIONS`|0x00000040L|Podporuje [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) a příkaz.|  
|`SCC_CAP_QUERYINFO`|0x00000080L|Podporuje [SccQueryInfo](../extensibility/sccqueryinfo-function.md) a příkaz.|  
|`SCC_CAP_GETEVENTS`|0x00000100L|Podporuje [SccGetEvents](../extensibility/sccgetevents-function.md) a příkaz.|  
|`SCC_CAP_GETPROJPATH`|0x00000200L|Podporuje [SccGetProjPath](../extensibility/sccgetprojpath-function.md) a příkaz.|  
|`SCC_CAP_ADDFROMSCC`|0x00000400L|Podporuje [SccAddFromScc](../extensibility/sccaddfromscc-function.md) a příkaz.|  
|`SCC_CAP_COMMENTCHECKOUT`|0x00000800L|Podporuje komentář na checkout.|  
|`SCC_CAP_COMMENTCHECKIN`|0x00001000L|Podporuje komentář na vrácení se změnami.|  
|`SCC_CAP_COMMENTADD`|0x00002000L|Podporuje komentář na Přidat.|  
|`SCC_CAP_COMMENTREMOVE`|0x00004000L|Podporuje komentář na odebrat.|  
|`SCC_CAP_TEXTOUT`|0x00008000L|Zapíše text do funkce poskytované IDE výstup.|  
|`SCC_CAP_ADD_STORELATEST`|0x00200000L|Podporuje ukládání souborů bez rozdílů.|  
|`SCC_CAP_HISTORY_MULTFILE`|0x00400000L|Podporuje více historie souborů.|  
|`SCC_CAP_IGNORECASE`|0x00800000L|Podporuje porovnání souborů velká a malá písmena.|  
|`SCC_CAP_IGNORESPACE`|0x01000000L|Podporuje souboru porovnání, které ignoruje prázdné znaky.|  
|`SCC_CAP_POPULATELIST`|0x02000000L|Hledání další soubory, které podporuje.|  
|`SCC_CAP_COMMENTPROJECT`|0x04000000L|Podporuje komentáře k vytvoření projektu.|  
|`SCC_CAP_DIFFALWAYS`|0x10000000L|Podporuje rozdílové ve všech stavů Pokud pod kontrolou.|  
|`SCC_CAP_GET_NOUI`|0x20000000L|Modul plug-in nepodporuje uživatelského rozhraní pro Get, ale stále může volat IDE [SccGet](../extensibility/sccget-function.md).|  
|`SCC_CAP_REENTRANT`|0x40000000L|Modul plug-in je vícenásobné a bezpečné pro přístup z více vláken. Ve verzi 1.0 žádné moduly plug-in se předpokládá, že se vícenásobné a bezpečné pro přístup z více vláken. Pokud modul plug-in 1.1 nastaví tento bit, je hostitel povolený otevřete více projektů současně.|  
  
## <a name="capability-bits-added-in-version-12"></a>Funkce Bits přidal ve verzi 1.2  
  
|Funkce kódu|Hodnota|Popis|  
|---------------------|-----------|-----------------|  
|`SCC_CAP_CREATESUBPROJECT`|0x00010000L|Podporuje [SccCreateSubProject](../extensibility/scccreatesubproject-function.md).|  
|`SCC_CAP_GETPARENTPROJECT`|0x00020000L|Podporuje [SccGetParentProjectPath](../extensibility/sccgetparentprojectpath-function.md).|  
|`SCC_CAP_BATCH`|0x00040000L|Podporuje [SccBeginBatch](../extensibility/sccbeginbatch-function.md) a [SccEndBatch](../extensibility/sccendbatch-function.md).|  
|`SCC_CAP_DIRECTORYSTATUS`|0x00080000L|Podporuje [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md).|  
|`SCC_CAP_DIRECTORYDIFF`|0x00100000L|Podporuje [SccDirDiff](../extensibility/sccdirdiff-function.md).|  
|`SCC_CAP_MULTICHECKOUT`|0x08000000L|Podporuje více rezervace na soubor a [SccIsMultiCheckoutEnabled](../extensibility/sccismulticheckoutenabled-function.md).|  
|`SCC_CAP_SCCFILE`|0x80000000L|Podporuje MSSCCPRJ. Soubor SCC (přičemž podléhá přepsání uživatele a správce) a [SccWillCreateSccFile](../extensibility/sccwillcreatesccfile-function.md).|  
  
## <a name="capability-bits-added-in-version-13"></a>Funkce Bits přidána do verze 1.3  
 Tyto příznaky jsou předávány jeden po druhém k [SccGetExtendedCapabilities](../extensibility/sccgetextendedcapabilities-function.md) funkce k určení, jestli je podporované možnosti.  
  
|Rozšířené funkce kódu|Hodnota|Popis|  
|------------------------------|-----------|-----------------|  
|`SCC_EXCAP_CHECKOUT_LOCALVER`|1|Podporuje `SCC_CHECKOUT_LOCALVER` možnost rezervace.|  
|`SCC_EXCAP_BACKGROUND_GET`|2|Podporuje [SccBackgroundGet](../extensibility/sccbackgroundget-function.md).|  
|`SCC_EXCAP_ENUM_CHANGED_FILES`|3|Podporuje [SccEnumChangedFiles](../extensibility/sccenumchangedfiles-function.md).|  
|`SCC_EXCAP_POPULATELIST_DIR`|4|Podporuje vyhledávání další adresáře.|  
|`SCC_EXCAP_QUERYCHANGES`|5|Podporuje vytváření výčtu změn souborů.|  
|`SCC_EXCAP_ADD_FILES_FROM_SCC`|6|Podporuje [SccAddFilesFromSCC](../extensibility/sccaddfilesfromscc-function.md).|  
|`SCC_EXCAP_GET_USER_OPTIONS`|7|Podporuje [SccGetUserOption](../extensibility/sccgetuseroption-function.md).|  
|`SCC_EXCAP_THREADSAFE_QUERY_INFO`|8|Podporuje volání SccQueryInfo ve více vláken.|  
|`SCC_EXCAP_REMOVE_DIR`|9|Podporuje funkci SccRemoveDir.|  
|`SCC_EXCAP_DELETE_CHECKEDOUT`|10|Můžete odstranit rezervovaných souborů.|  
|`SCC_EXCAP_RENAME_CHECKEDOUT`|11|Můžete přejmenovat rezervovaných souborů.|  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in správy zdrojového kódu](../extensibility/source-control-plug-ins.md)