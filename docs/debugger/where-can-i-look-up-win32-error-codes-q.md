---
title: Kde najdu kódy chyb systému Win32? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.errors
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81d919733f1caf654460cf342da05f2549dfa167
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476208"
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