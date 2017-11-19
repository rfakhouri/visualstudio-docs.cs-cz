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
ms.openlocfilehash: f83fbf1427951057f2154e032fb58b178c8b39fc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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