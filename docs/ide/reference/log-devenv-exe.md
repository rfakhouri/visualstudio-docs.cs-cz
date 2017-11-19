---
title: -Protokolu (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cf5ab0e1949716005d12d51d06b0d915344833aa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
Zaznamená veškerou aktivitu do souboru protokolu pro řešení potíží. Tento soubor se zobrazí po jste jste volali metodu `devenv /log` alespoň jednou. Ve výchozím nastavení je soubor protokolu:  
  
 *Data aplikací %*\Microsoft\VisualStudio\\*verze*\ActivityLog.xml  
  
 kde *verze* je verzi sady Visual Studio. Ale můžete určit jiný název a cesta k souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /log Path\NameOfLogFile  
```  
  
## <a name="remarks"></a>Poznámky  
 Tento přepínač musí být uvedeny na konci příkazového řádku po všech ostatních přepínačích.  
  
 Protokol je zapsán pro všechny instance sady Visual Studio, který jste volat pomocí přepínače/log. Ho nebude protokolu instancí sady Visual Studio, která jste volána bez přepínač.  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)