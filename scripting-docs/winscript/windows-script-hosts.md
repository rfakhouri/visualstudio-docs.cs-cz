---
title: Windows Script hostitele | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Script Host, implementing hosts
ms.assetid: 9d5f6471-b318-40f3-be01-d9cd0b1cdd47
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eec1824bd3ba1a8acb7e3c540656151cd4b11d1f
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58145106"
---
# <a name="windows-script-hosts"></a>Moduly Windows Script Host
Při implementaci Microsoft Windows Script host, můžete bezpečně předpokládat, že skriptovací stroj jen volá [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) rozhraní v kontextu základní vlákna tak dlouho, dokud hostitel provede následující akce:  
  
- Vybere základní podprocesu (obvykle vlákna, která obsahuje smyčky zpráv).  
  
- Vytvoří instanci skriptovací stroj v základní vlákna.  
  
- Volání skriptovací stroj metody pouze ze základní vlákna, s výjimkou tam, kde konkrétně, stejně jako v případě [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) a [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
- Objekt odeslání skriptovací stroj volá pouze z základní vlákna.  
  
- Zajistíte, že smyčka zpráv spustí v základní vlákna, pokud je zadaný popisovač okna.  
  
- Zajišťuje, že objekty v hostitelově objektu modelu pouze zdroj události v základní vlákna.  
  
  Tato pravidla jsou automaticky následovaný všichni hostitelé s jedním vláknem. S omezeným přístupem modelu popsaného výše je záměrně dojde ke ztrátě dostatečně umožňující hostitele pro přerušení zablokované skript voláním [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) z jiného vlákna (iniciovaných obslužnou rutinu CTRL + BREAK nebo podobné), nebo do adresáře duplicitní skript v nové vlákno s použitím [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
## <a name="remarks"></a>Poznámky  
 Žádná z těchto omezení platí pro hostitele, který vybere k implementaci volných vláken [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) rozhraní a volných vláken objektový model. Můžete použít takový hostitel [IActiveScript –](../winscript/reference/iactivescript.md) rozhraní z libovolného vlákna bez omezení.  
  
## <a name="see-also"></a>Viz také  
 [Skriptovací rozhraní systému Windows](../winscript/windows-script-interfaces.md)