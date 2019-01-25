---
title: Moduly – příkaz seznamu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.listmodules
helpviewer_keywords:
- Debug.ListModules command
- ListModules command
- list modules command
ms.assetid: 3cb73774-6ac0-43b2-b781-75ed47175bfd
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 26c2a2c07e09863c3320c3c69b8cc093bdf39466
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54790030"
---
# <a name="list-modules-command"></a>Listovat moduly – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Seznam modulů pro aktuální proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListModules [/Address:yes|no] [/Name:yes|no] [/Order:yes|no]  
[/Path:yes|no] [/Process:yes|no] [/SymbolFile:yes|no]  
[/SymbolStatus:yes|no] [/Timestamp:yes|no] [/Version:yes|no]  
```  
  
#### <a name="parameters"></a>Parametry  
 / Adresa:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit adresy paměti modulů. Výchozí hodnota je `yes`.  
  
 / Name:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit názvy modulů. Výchozí hodnota je `yes`.  
  
 / Order:`yes|no`  
 Volitelné. Určuje, zda-li zobrazit pořadí modulů. Výchozí hodnota je `no`.  
  
 / Path:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit cesty moduly. Výchozí hodnota je `yes`.  
  
 / Process:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit procesy moduly. Výchozí hodnota je `no`.  
  
 / Souborsymbolů:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit soubory symbolů z modulů. Výchozí hodnota je `no`.  
  
 /SymbolStatus:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit symbol stavy modulů. Výchozí hodnota je `yes`.  
  
 / Časové razítko:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit časová razítka modulů. Výchozí hodnota je `no`.  
  
 / Version:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit verze modulů. Výchozí hodnota je `no`.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Tento příklad zobrazí seznam názvů modulů, adresy a časová razítka pro aktuální proces.  
  
```  
Debug.ListModules /Address:yes /Name:yes /Order:no /Path:no /Process:no /SymbolFile:no /SymbolStatus:no /Timestamp:yes /Version:no  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Postupy: Použití okna Moduly](../../debugger/how-to-use-the-modules-window.md)
