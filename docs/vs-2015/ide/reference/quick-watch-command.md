---
title: Rychlé kukátko – příkaz | Dokumentace Microsoftu
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
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d340f88b83e5dce3054a264a2815fa96707a19f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669592"
---
# <a name="quick-watch-command"></a>Rychlé kukátko – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Rychlé kukátko – příkaz](https://docs.microsoft.com/visualstudio/ide/reference/quick-watch-command).  
  
  
Zobrazí zadaný nebo vybraný text v poli výraz [dialogového okna rychlého kukátka](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867). Toto dialogové okno můžete použít k výpočtu aktuální hodnotu proměnné nebo výrazu rozpoznávaných ladicí program nebo obsah registru. Kromě toho můžete změnit hodnotu kterékoli proměnné nekonstantní nebo obsah jakékoli registru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.QuickWatchq [text]  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Volitelné. Text, který má přidat **QuickWatch** dialogové okno.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `text` je tento parametr vynechán, aktuálně vybraného textu nebo word na pozici kurzoru se přidá do okna kukátka.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.QuickWatch  
```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: použití dialogového okna QuickWatch](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



