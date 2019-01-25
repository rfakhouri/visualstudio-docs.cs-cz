---
title: Rychlé kukátko – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d8ee0de9cad23b6208c9b015c65a8d9494821eae
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54789804"
---
# <a name="quick-watch-command"></a>Rychlé kukátko – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
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
 [Postupy: Pomocí dialogového okna QuickWatch](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
