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
ms.workload: multiple
ms.openlocfilehash: eb673db29a4bb106aa4c9c4d9022293367e8ed4f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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