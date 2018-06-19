---
title: Windows Script hostitelů | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 41fa898c7f0d62cd35cc1cb1c7b35eb2651c8bb6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24796425"
---
# <a name="windows-script-hosts"></a>Moduly Windows Script Host
Při implementaci Microsoft Windows Script host, můžete bezpečně předpokládat pouze volá skriptovací stroj [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) rozhraní v kontextu základní vlákno tak dlouho, dokud hostitel provede následující akce:  
  
-   Zvolí základní vlákno (obvykle podproces, který obsahuje zpráva smyčky).  
  
-   Vytvoří instanci skriptovacího stroje v základní vlákno.  
  
-   Volání skriptovací stroj metody pouze z základní vlákno, s výjimkou tam, kde konkrétně, jako v případě [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) a [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
-   Volání objektu odesílání skriptovací stroj pouze ze základní vlákno.  
  
-   Zajišťuje, že zpráva smyčky běží v základní vlákno, pokud je zadaný popisovač okna.  
  
-   Zajišťuje, že objekty v objektu hostitele modelu pouze zdroj události v základní vlákno.  
  
 Tato pravidla jsou automaticky následovaný všichni hostitelé jednovláknové. Model s omezeným přístupem popsané výše je záměrně dostatečně přijít umožňující hostitele k přerušení skript zablokované voláním [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) z jiného vlákna (iniciována obslužnou rutinu CTRL + BREAK nebo podobné), nebo na duplicitní skript v nové vlákno pomocí [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
## <a name="remarks"></a>Poznámky  
 Žádná z těchto omezení platí pro hostitele, který se rozhodne pro implementaci podprocesy [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) rozhraní a podprocesy objektového modelu. Můžete použít tyto hostitele [IActiveScript –](../winscript/reference/iactivescript.md) rozhraní z libovolného vlákna, bez omezení.  
  
## <a name="see-also"></a>Viz také  
 [Skriptovací rozhraní systému Windows](../winscript/windows-script-interfaces.md)