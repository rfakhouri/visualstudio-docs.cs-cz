---
title: Kukátko – příkaz | Dokumentace Microsoftu
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
- debug.watch
helpviewer_keywords:
- Watch command
- Debug.Watch command
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d06e15f23a8f75e4a771b9db1991f5aba2ffc0d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671168"
---
# <a name="watch-command"></a>Kukátko – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kukátko – příkaz](https://docs.microsoft.com/visualstudio/ide/reference/watch-command).  
  
  
Vytvoří a otevře zadanou instanci **Watch** okna. Můžete použít **Watch** okna k výpočtu hodnoty proměnných, výrazů a registry, chcete-li tyto hodnoty upravit a uložit výsledky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.Watch[index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Požadováno. Číslo instance okna kukátka.  
  
## <a name="remarks"></a>Poznámky  
 `index` Musí být celé číslo. Platné hodnoty jsou 1, 2, 3 nebo 4.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.Watch1  
```  
  
## <a name="see-also"></a>Viz také  
 [Automatické hodnoty a místní hodnoty Windows](../../debugger/autos-and-locals-windows.md)   
 [Postupy: Úprava hodnoty v okně proměnné](http://msdn.microsoft.com/library/36f464ab-c900-4c0b-9ab3-557b3d9cdab5)   
 [Postupy: použití dialogového okna QuickWatch](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



