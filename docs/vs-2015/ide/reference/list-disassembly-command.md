---
title: Zobrazit zpětný překlad – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.listdisassembly
helpviewer_keywords:
- Debug.ListDisassembly command
- list disassembly command
ms.assetid: eb363e35-e86a-4121-966f-991210c27e2a
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ff87add99fb618eaa45d6f9a71a68d82149884e3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54753392"
---
# <a name="list-disassembly-command"></a>Zobrazit zpětný překlad – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Spustí proces ladění a umožňuje určit způsob zpracování chyb.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListDisassembly [/count:number] [/endaddress:expression]  
[/codebytes:yes|no] [/source:yes|no] [/symbolnames:yes|no]  
[/linenumbers:yes|no]  
```  
  
## <a name="switches"></a>Přepínače  
 Každý přepínač je možné vyvolat pomocí jeho dokončení formuláře nebo krátký tvar.  
  
 / count: `number` [nebo] sady `number` [nebo] /length: `number` [nebo] l: `number`  
 Volitelné. Počet instrukcí pro zobrazení. Výchozí hodnota je 8.  
  
 /endaddress: `expression` [nebo] / e: `expression`  
 Volitelné. Adresa, kam chcete zastavit zpětný překlad.  
  
 /codebytes:`yes` &#124; `no` [nebo] /bytes:`yes` &#124; `no` [nebo] / b:`yes`&#124;`no`  
 Volitelné. Označuje, zda chcete-li zobrazit kód bajtů. Výchozí hodnota je `no`.  
  
 / source:`yes` &#124; `no` [nebo] / s:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se má zobrazit zdrojový kód. Výchozí hodnota je `no`.  
  
 /symbolnames:`yes` &#124; `no` [nebo] /names:`yes` &#124; `no` [nebo] / n:`yes`&#124;`no`  
 Volitelné. Označuje, zda chcete-li zobrazit názvy symbolů. Výchozí hodnota je `yes`.  
  
 [/linenumbers:`yes`&#124;`no`]  
 Volitelné. Umožňuje zobrazení čísla řádků související se zdrojovým kódem. Přepínač/Source musí mít hodnotu `yes` /linenumbers přepínač.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.ListDisassembly  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkaz listovat zásobník volání](../../ide/reference/list-call-stack-command.md)   
 [Listovat vlákna – příkaz](../../ide/reference/list-threads-command.md)   
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
