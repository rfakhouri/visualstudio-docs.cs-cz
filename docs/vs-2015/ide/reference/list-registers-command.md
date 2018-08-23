---
title: Listovat registry – příkaz | Dokumentace Microsoftu
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
- debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c9ff1287bb4c92d074c0a0e123d48ddb7e61cc90
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671564"
---
# <a name="list-registers-command"></a>Listovat registry – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [listovat registry – příkaz](https://docs.microsoft.com/visualstudio/ide/reference/list-registers-command).  
  
  
Zobrazí hodnotu vybraného zaregistruje a vám umožní upravit seznam registrů, které mají zobrazit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]  
[/Watch [{register|registerGroup}...]]  
[/Unwatch [{register|registerGroup}...]]  
```  
  
## <a name="switches"></a>Přepínače  
 / Zobrazit [{`register`&#124;`registerGroup`}...]  
 Zobrazí hodnoty zadaného `register` nebo `registerGroup`. Pokud ne `register` nebo `registerGroup` je zadán, zobrazí se výchozí seznam registrů. Pokud není zadán žádný přepínač, chování je stejné. Příklad:  
  
 `Debug.ListRegisters /Display eax`  
  
 je ekvivalentem  
  
 `Debug.ListRegisters eax`  
  
 / List  
 Zobrazí všechny registrovat skupiny v seznamu.  
  
 / Sledovat [{`register`&#124;`registerGroup`}...]  
 Přidá jednu nebo více `register` nebo `registerGroup` hodnoty do seznamu.  
  
 / Unwatch [{`register`&#124;`registerGroup`}...]  
 Odebere jeden nebo více `register` nebo `registerGroup` hodnot v seznamu.  
  
## <a name="remarks"></a>Poznámky  
 Alias `r` lze použít místo `Debug.ListRegisters`.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu `Debug.ListRegisters` alias `r` k zobrazení hodnot registru skupiny `Flags`.  
  
```  
r /Display Flags  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Základní informace k ladění: Okno registrů](../../debugger/debugging-basics-registers-window.md)   
 [Postupy: použití okna registry](../../debugger/how-to-use-the-registers-window.md)



