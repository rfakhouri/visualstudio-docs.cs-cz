---
title: Tisk – příkaz | Dokumentace Microsoftu
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
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e518b3c6ffc3520b408e7c1bfb1fd1703e40a8de
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667953"
---
# <a name="print-command"></a>Tisk – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [příkaz Tisk](https://docs.microsoft.com/visualstudio/ide/reference/print-command).  
  
  
Vyhodnotí výraz a zobrazí zadaný text.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.Print text  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Požadováno. Výraz k vyhodnocení nebo text k zobrazení.  
  
## <a name="remarks"></a>Poznámky  
 Otazník (?) můžete použít jako alias pro tento příkaz. Ano například příkaz  
  
```  
>Debug.Print expA  
```  
  
 lze také zapsat  
  
```  
>? expA  
```  
  
 Obě verze tohoto příkazu vrátí aktuální hodnotu výrazu `expA`.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.Print varA  
```  
  
## <a name="see-also"></a>Viz také  
 [Ohodnotit příkaz – příkaz](../../ide/reference/evaluate-statement-command.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



