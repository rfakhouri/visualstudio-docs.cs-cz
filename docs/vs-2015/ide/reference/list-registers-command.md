---
title: Listovat registry – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
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
manager: jillfra
ms.openlocfilehash: 6f9eaa1299ec49cf20713723e822f8fc641401d8
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59658536"
---
# <a name="list-registers-command"></a>Listovat registry – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Základy ladění: Registr – okno](../../debugger/debugging-basics-registers-window.md)   
 [Postupy: Použití okna Registry](../../debugger/how-to-use-the-registers-window.md)
