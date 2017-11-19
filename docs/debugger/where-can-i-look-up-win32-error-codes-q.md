---
title: "Kde najdu kódy chyb systému Win32? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.errors
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 508b741dcac0662d41e58b37ecaf177a2245010f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="where-can-i-look-up-win32-error-codes"></a>Kde najdu kódy chyb systému Win32?
NEZDAŘILA. H v adresáři zahrnout výchozí instalace systému obsahuje definice, kód chyby pro funkce rozhraní API Win32.  
  
 Kód chyby můžete vyhledat zadáním kódu v **sledovat** okno nebo **QuickWatch** dialogové okno. Příklad:  
  
```  
0x80000004,hr  
```  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)