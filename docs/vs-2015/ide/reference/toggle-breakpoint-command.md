---
title: Přepnout zarážku – příkaz | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.togglebreakpoint
helpviewer_keywords:
- ToggleBreakpoint command
- Debug.ToggleBreakPoint command
- Toggle Breakpoint command
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c7dd3bd7a4d42b8135aed034464223af53091f87
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633550"
---
# <a name="toggle-breakpoint-command"></a>Přepnout zarážku – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Přepnout zarážku – příkaz](https://docs.microsoft.com/visualstudio/ide/reference/toggle-breakpoint-command).  
  
  
V závislosti na jejím aktuálním stavu na aktuální pozici v souboru se změní na zarážku, zapnout nebo vypnout.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ToggleBreakpoint [text]  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Volitelné. Pokud je zadán text, na řádku je označena jako pojmenované zarážku. V opačném případě je řádku označena jako nepojmenované zarážky, které je podobné co se stane, když stisknete klávesu F9.  
  
## <a name="example"></a>Příklad  
 Následující příklad přepíná aktuální zarážku.  
  
```  
>Debug.ToggleBreakpoint  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



