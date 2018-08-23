---
title: Spustit příkaz | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6e70a682d9b9ef67e9f0372173c3396a0706cd2f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670025"
---
# <a name="start-command"></a>Spustit – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [příkazu Start](https://docs.microsoft.com/visualstudio/ide/reference/start-command).  
  
  
Zahájí projekt po spuštění ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>Arguments  
 `address`  
 Volitelné. Adresa, na kterém program pozastaví provádění kódu, podobně jako na zarážku ve zdrojovém kódu. Tento argument je platná jenom v režimu ladění.  
  
## <a name="remarks"></a>Poznámky  
 **Start** při spuštění příkazu provádí operaci RunToCursor na zadanou adresu.  
  
## <a name="example"></a>Příklad  
 Tento příklad spustí ladicí program a ignoruje všechny výjimky, ke kterým dochází.  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



