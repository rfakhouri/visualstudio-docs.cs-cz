---
title: Nastavit aktuální proces | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ed19c5b95351f8e9c34255a915fc6a446800f761
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68163344"
---
# <a name="set-current-process"></a>Nastavit aktuální proces
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nastavujte určený proces jako aktivní proces v ladicím programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.SetCurrentProcess index  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Povinný parametr. Index procesu.  
  
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
