---
title: -Log (devenv.exe) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bfd6d9ac2493e4caca95538140fb9af78db8e074
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667329"
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [-Log (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/log-devenv-exe).  
  
  
Zaznamená veškerou aktivitu do souboru protokolu pro řešení potíží. Tento soubor se zobrazí poté, co jste volat `devenv /log` alespoň jednou. Ve výchozím nastavení je soubor protokolu:  
  
 *% APPDATA %* \Microsoft\VisualStudio\\*verze*\ActivityLog.xml  
  
 kde *verze* je verze sady Visual Studio. Můžete ale zadat jiný název a cesta k souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /log Path\NameOfLogFile  
```  
  
## <a name="remarks"></a>Poznámky  
 Tento přepínač musí být uvedeny na konci příkazového řádku po všech ostatních přepínačích.  
  
 Protokol je zapsán pro všechny instance sady Visual Studio, které jste voláno s přepínačem/log. To není protokolu instance sady Visual Studio, který jste vyvolán bez přepínače.  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)



