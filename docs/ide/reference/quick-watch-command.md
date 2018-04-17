---
title: Rychlé kukátko – příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 75ac6c430d34dabdba3a6bebcce78c7c5b9817b7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="quick-watch-command"></a>Rychlé kukátko – příkaz
Zobrazí vybraný nebo zadaný text v poli výraz [QuickWatch](../../debugger/watch-and-quickwatch-windows.md) okno. Toto dialogové okno můžete použít k výpočtu aktuální hodnota proměnné nebo výrazu rozpoznáno ladicího programu nebo obsah registru. Kromě toho můžete změnit hodnotu proměnné jakékoli jiné const nebo obsah všech registru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.QuickWatchq [text]  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Volitelné. Text pro přidání do **QuickWatch** dialogové okno.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `text` je tento parametr vynechán, bude aktuálně vybraného textu nebo word na pozici kurzoru přidán do okna sledování.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.QuickWatch  
```  
  
## <a name="see-also"></a>Viz také  
 [Nastavovat sledování na proměnné pomocí sledování a QuickWatch Windows v sadě Visual Studio](../../debugger/watch-and-quickwatch-windows.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)