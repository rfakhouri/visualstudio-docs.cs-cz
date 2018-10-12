---
title: Řetězce používané jako klíče pro vyhledání modulu Plug-in správy zdrojového kódu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, strings used for finding
ms.assetid: c1e31f76-42a1-4c3d-afb2-664044ef12fd
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5f49ac150af84cdd5dfae52e905cb353722b0ed0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49243630"
---
# <a name="strings-used-as-keys-for-finding-a-source-control-plug-in"></a>Řetězce, které slouží jako klíče pro vyhledání modulu plug-in pro správu zdrojového kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Klíče pro přístup k registru najdete informace o ovládacím prvku modulu plug-in jsou následující řetězce.  
  
 `STR_SCC_PROVIDER_REG_LOCATION`, `STR_PROVIDERREGKEY`, `STR_SCCPROVIDERPATH`, a `STR_SCCPROVIDERNAME` jsou klíče registru nebo hodnoty použité k registraci knihovny DLL jako modul plug-in správy zdrojového kódu pro Visual Studio.  
  
 `SCC_PROJECTNAME_KEY`, `SCC_PROJECTAUX_KEY`, `SCC_KEY, SCC_FILE_SIGNATURE`, a `SCC_STATUS_FILE` se používají k popisu formátu MSSCCPRJ. SCC souboru.  
  
## <a name="string-keys-and-values"></a>Řetězec klíče a hodnoty  
  
|Key|Hodnota|  
|---------|-----------|  
|`STR_SCC_PROVIDER_REG_LOCATION`|Software\SourceCodeControlProvider|  
|`STR_PROVIDERREGKEY`|ProviderRegKey|  
|`STR_SCCPROVIDERPATH`|SCCServerPath|  
|`STR_SCCPROVIDERNAME`|SCCServerName|  
|`STR_SCC_INI_SECTION`|Správa zdrojového kódu|  
|`STR_SCC_INI_KEY`|SourceCodeControlProvider|  
|`SCC_PROJECTNAME_KEY`|SCC_Project_Name|  
|`SCC_PROJECTAUX_KEY`|SCC_Aux_Path|  
|`SCC_STATUS_FILE`|MSSCCPRJ. SCC|  
|`SCC_KEY`|SCC|  
|`SCC_FILE_SIGNATURE`|Soubor zdrojového kódu ovládacího prvku|  
|`SCC_NSE`|Rozšíření Namespace|  
|`SCC_NSE_PREFIX`|Předpona protokolem|  
|`SCC_NSE_DisableOpenSCC`|DisableOpenFromSourceControl|  
|`STR_SCCHELPCOLLECTION`|HelpCollection|  
|`STR_UI_LANGUAGE`|UILanguage|  
|`STR_SRCSAFE_ROOT_KEY`|Software\Microsoft\SourceSafe|  
  
## <a name="see-also"></a>Viz také  
 [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)   
 [Postupy: Instalace modulu Plug-in správy zdrojového kódu](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [Soubor MSSCCPRJ.SCC](../extensibility/mssccprj-scc-file.md)

