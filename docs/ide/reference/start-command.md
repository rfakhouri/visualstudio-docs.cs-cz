---
title: Spuštění příkazu. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a4c372d3f384eeaa0ac137188e325ccde777cd4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="start-command"></a>Spustit – příkaz
Zahájí ladění spouštěný projekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>Arguments  
 `address`  
 Volitelné. Adresa, kdy program pozastaví spuštění, podobně jako zarážky ve zdrojovém kódu. Tento argument platí pouze v režimu ladění.  
  
## <a name="remarks"></a>Poznámky  
 **Spustit** příkaz po provedení provede operaci RunToCursor na zadanou adresu.  
  
## <a name="example"></a>Příklad  
 Tento příkaz spustí ladicího programu a ignoruje všechny výjimky, které dojít.  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)