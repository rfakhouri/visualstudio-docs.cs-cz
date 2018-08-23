---
title: Kde najdu kódy chyb systému Win32? | Dokumenty Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.errors
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86735dae123d0fdedc59f4205af349b86cc6efd0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668340"
---
# <a name="where-can-i-look-up-win32-error-codes"></a>Kde najdu kódy chyb systému Win32?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kde je možné se podívat do kódy chyb systému Win32?](https://docs.microsoft.com/visualstudio/debugger/where-can-i-look-up-win32-error-codes-q).  
  
NEZDAŘILA. H v adresáři INCLUDE výchozí instalace systému obsahuje definice chyba kódu pro funkce rozhraní Win32 API.  
  
 Kód chyby můžete vyhledat zadáním kódu v **Watch** okno nebo **QuickWatch** dialogové okno. Příklad:  
  
```  
0x80000004,hr  
```  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)



