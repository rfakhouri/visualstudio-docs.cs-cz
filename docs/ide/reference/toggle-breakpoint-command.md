---
title: "Přepnout zarážku – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.togglebreakpoint
helpviewer_keywords:
- ToggleBreakpoint command
- Debug.ToggleBreakPoint command
- Toggle Breakpoint command
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 21a763ee4b2d86a42566aa1d93b8313e5799cee7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="toggle-breakpoint-command"></a>Přepnout zarážku – příkaz
V závislosti na aktuálním stavu, do aktuálního umístění v souboru se změní zarážek zapnout nebo vypnout.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ToggleBreakpoint [text]  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Volitelné. Pokud je zadán text, řádek je označena jako s názvem zarážky. Jinak hodnota řádku je označeno nepojmenované zarážek, což je podobná co se stane po stisknutí klávesy F9.  
  
## <a name="example"></a>Příklad  
 Následující příklad Přepne aktuální zarážek.  
  
```  
>Debug.ToggleBreakpoint  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)