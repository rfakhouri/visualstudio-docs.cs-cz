---
title: "Seznam vláken příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.listthreads
helpviewer_keywords:
- ListThreads command
- list threads command
- Debug.ListThreads command
ms.assetid: 34b665c0-d46f-4c1a-a066-b678eba5ac54
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4499bd11e60aba81b37f13f5ce95e8a17412e2d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="list-threads-command"></a>Listovat vlákna – příkaz
Zobrazí seznam vláken v aktuálním programem.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListThreads [index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Volitelné. Vybere vlákna podle jeho indexu jako aktuální vlákno.  
  
## <a name="remarks"></a>Poznámky  
 -Li zadána, `index` argument označí uvedené vlákno jako aktuální vlákno. Znak hvězdičky (*) se zobrazí v seznamu vedle aktuální vlákno.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.ListThreads   
```  
  
## <a name="see-also"></a>Viz také  
 [Listovat zásobník volání – příkaz](../../ide/reference/list-call-stack-command.md)   
 [Seznam zpětný překlad – příkaz](../../ide/reference/list-disassembly-command.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)