---
title: "Listovat registry – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 83f4830b79c4492337abb6052b1b2803b34b5a9b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="list-registers-command"></a>Listovat registry – příkaz
Zobrazí hodnotu vybrané zaregistruje a umožňuje upravit seznam registruje zobrazit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]  
[/Watch [{register|registerGroup}...]]  
[/Unwatch [{register|registerGroup}...]]  
```  
  
## <a name="switches"></a>Přepínače  
 / Zobrazení [{`register`&#124;`registerGroup`} ...]  
 Zobrazí hodnoty zadaného `register` nebo `registerGroup`. Pokud žádné `register` nebo `registerGroup` je zadán, zobrazí se výchozí seznam Registry. Pokud není zadán žádný přepínač, chování je stejné. Příklad:  
  
 `Debug.ListRegisters /Display eax`  
  
 je ekvivalentem  
  
 `Debug.ListRegisters eax`  
  
 Nebo jejich výpisu  
 Zobrazí všechny skupiny registru v seznamu.  
  
 Nebo si pusťte [{`register`&#124;`registerGroup`} ...]  
 Přidá jeden nebo více `register` nebo `registerGroup` hodnoty do seznamu.  
  
 / Unwatch [{`register`&#124;`registerGroup`} ...]  
 Odebere jeden nebo více `register` nebo `registerGroup` hodnoty ze seznamu.  
  
## <a name="remarks"></a>Poznámky  
 Alias `r` lze místě `Debug.ListRegisters`.  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `Debug.ListRegisters` alias `r` k zobrazení hodnot registrace skupiny `Flags`.  
  
```  
r /Display Flags  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Základní informace k ladění: Okno registrů](../../debugger/debugging-basics-registers-window.md)   
 [Postupy: použití okna registry](../../debugger/how-to-use-the-registers-window.md)