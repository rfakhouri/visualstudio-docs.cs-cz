---
title: Nastavit aktuální proces | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5281d1c0d926d8d6acdedf323649216c74a4cab9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669061"
---
# <a name="set-current-process"></a>Nastavit aktuální proces
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [nastavit aktuální proces](https://docs.microsoft.com/visualstudio/ide/reference/set-current-process).  
  
  
Nastavujte určený proces jako aktivní proces v ladicím programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.SetCurrentProcess index  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Požadováno. Index procesu.  
  
## <a name="remarks"></a>Poznámky  
 Můžete se připojit k více procesům při ladění, ale pouze jeden proces je v daném okamžiku aktivní v ladicím programu. Můžete použít `SetCurrentProcess` příkaz pro nastavení aktivního procesu.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.SetCurrentProcess 1  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



