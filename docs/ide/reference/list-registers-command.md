---
title: Listovat registry – příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4bd4dac2cc8faf6d98ee130e0796254035b1ca2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 / Zobrazení [{`register`&#124;`registerGroup`}...]  
 Zobrazí hodnoty zadaného `register` nebo `registerGroup`. Pokud žádné `register` nebo `registerGroup` je zadán, zobrazí se výchozí seznam Registry. Pokud není zadán žádný přepínač, chování je stejné. Příklad:  
  
 `Debug.ListRegisters /Display eax`  
  
 je ekvivalentem  
  
 `Debug.ListRegisters eax`  
  
 Nebo jejich výpisu  
 Zobrazí všechny skupiny registru v seznamu.  
  
 Nebo si pusťte [{`register`&#124;`registerGroup`}...]  
 Přidá jeden nebo více `register` nebo `registerGroup` hodnoty do seznamu.  
  
 / Unwatch [{`register`&#124;`registerGroup`}...]  
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