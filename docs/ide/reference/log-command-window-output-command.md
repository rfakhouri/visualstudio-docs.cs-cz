---
title: "Protokol příkazové okno výstup příkazu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7f5dffcd68447cac398c980f0b6c0ac2319c9060
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="log-command-window-output-command"></a>Protokolovat výstup příkazového okna – příkaz
Zkopíruje všechny vstup a výstup z **příkaz** okna do souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Volitelné. Název souboru protokolu. Ve výchozím nastavení se soubor vytvoří ve složce profilu uživatele. Pokud název souboru již existuje, protokol je připojen na konec existující soubor. Pokud není zadán žádný soubor, použije se poslední zadaný soubor. Pokud žádné předchozí soubor existuje, se vytvoří výchozí soubor protokolu, názvem cmdline.log.  
  
> [!TIP]
>  Chcete-li změnit umístění pro uložení souboru protokolu, zadejte úplnou cestu k souboru, ohraničená uvozovkami, pokud cesta obsahuje mezery.  
  
## <a name="switches"></a>Přepínače  
 /on  
 Volitelné. Spuštění protokolu **příkaz** okna do zadaného souboru a připojí soubor novými informacemi.  
  
 / vypnuto  
 Volitelné. Zastaví v protokolu **příkaz** okno.  
  
 / overwrite  
 Volitelné. Pokud soubor zadaný v `filename` argument odpovídá existující soubor, soubor se přepíše.  
  
## <a name="remarks"></a>Poznámky  
 Pokud není zadán žádný soubor, vytvoří se ve výchozím nastavení cmdline.log souboru. Ve výchozím nastavení je alias pro tento příkaz protokolu.  
  
## <a name="examples"></a>Příklady  
 Tento příklad vytvoří nový soubor protokolu, cmdlog a spustí příkaz protokolu.  
  
```  
>Tools.LogCommandWindowOutput cmdlog  
```  
  
 Tento příklad zastaví protokolování příkazy.  
  
```  
>Tools.LogCommandWindowOutput /off  
```  
  
 Tento příklad obnoví protokolování příkazy v dříve použitých souboru protokolu.  
  
```  
>Tools.LogCommandWindowOutput /on  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)