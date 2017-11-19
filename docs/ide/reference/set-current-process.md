---
title: "Nastavit aktuální proces | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6bd4ab27a36e37e31ec348b80327b6046c5ecbd3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="set-current-process"></a>Nastavit aktuální proces
Nastaví zadaný proces jako aktivní proces v ladicím programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.SetCurrentProcess index  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Požadováno. Index proces.  
  
## <a name="remarks"></a>Poznámky  
 Můžete se připojit k více procesů při ladění, ale je v každém okamžiku v dubber aktivní pouze jeden proces. Můžete použít `SetCurrentProcess` příkazu nastavte aktivní proces.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.SetCurrentProcess 1  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)