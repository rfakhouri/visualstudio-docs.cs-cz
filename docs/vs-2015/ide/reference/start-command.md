---
title: Spustit příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c334f52ba080329ef5cbd6dfde1e3e3beed1dc70
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59658159"
---
# <a name="start-command"></a>Spustit – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
