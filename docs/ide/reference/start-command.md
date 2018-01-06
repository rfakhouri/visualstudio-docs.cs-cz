---
title: "Spuštění příkazu. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8eb0efae140613c6caa7bd71d72e0ce4cda37db8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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