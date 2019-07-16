---
title: Řetězce používané jako klíče pro vyhledání modulu Plug-in správy zdrojového kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, strings used for finding
ms.assetid: c1e31f76-42a1-4c3d-afb2-664044ef12fd
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 83ba843e318aac6a74d318978e42e2f81802d8ac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68160573"
---
# <a name="strings-used-as-keys-for-finding-a-source-control-plug-in"></a>Řetězce, které slouží jako klíče pro vyhledání modulu plug-in pro správu zdrojového kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Klíče pro přístup k registru najdete informace o ovládacím prvku modulu plug-in jsou následující řetězce.  
  
 `STR_SCC_PROVIDER_REG_LOCATION`, `STR_PROVIDERREGKEY`, `STR_SCCPROVIDERPATH`, a `STR_SCCPROVIDERNAME` jsou klíče registru nebo hodnoty použité k registraci knihovny DLL jako modul plug-in správy zdrojového kódu pro Visual Studio.  
  
 `SCC_PROJECTNAME_KEY`, `SCC_PROJECTAUX_KEY`, `SCC_KEY, SCC_FILE_SIGNATURE`, a `SCC_STATUS_FILE` se používají k popisu formátu MSSCCPRJ. SCC souboru.  
  
## <a name="string-keys-and-values"></a>Řetězec klíče a hodnoty  
  
|Key|Value|  
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
