---
title: Kukátko – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.watch
helpviewer_keywords:
- Watch command
- Debug.Watch command
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b1a04dce73dbf2551b51f2395b3512e62daf3766
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54788187"
---
# <a name="watch-command"></a>Kukátko – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Vytvoří a otevře zadanou instanci **Watch** okna. Můžete použít **Watch** okna k výpočtu hodnoty proměnných, výrazů a registry, chcete-li tyto hodnoty upravit a uložit výsledky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.Watch[index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Povinný parametr. Číslo instance okna kukátka.  
  
## <a name="remarks"></a>Poznámky  
 `index` Musí být celé číslo. Platné hodnoty jsou 1, 2, 3 nebo 4.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.Watch1  
```  
  
## <a name="see-also"></a>Viz také  
 [Automatické hodnoty a místní hodnoty Windows](../../debugger/autos-and-locals-windows.md)   
 [Postupy: Úprava hodnoty v okně proměnné](http://msdn.microsoft.com/library/36f464ab-c900-4c0b-9ab3-557b3d9cdab5)   
 [Postupy: Pomocí dialogového okna QuickWatch](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
