---
title: -Log (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 18b455d3da5693e5a82dbf45e52d04b18edaef5d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199102"
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Zaznamená veškerou aktivitu do souboru protokolu pro řešení potíží. Tento soubor se zobrazí poté, co jste volat `devenv /log` alespoň jednou. Ve výchozím nastavení je soubor protokolu:  
  
 *%APPDATA%* \Microsoft\VisualStudio\\*Version*\ActivityLog.xml  
  
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
