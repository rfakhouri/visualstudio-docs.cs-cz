---
title: Při pokusu o spojení se vzdáleným počítačem došlo k chybě modelu DCOM. Přístup byl zamítnut. | Dokumenty Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.remote.dcom_access_denied
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cabac4997480b626714c129daef0511643ae2a50
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670511"
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Při pokusu o spojení se vzdáleným počítačem došlo k chybě modelu DCOM. Přístup byl zamítnut.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [pokusu o spojení se vzdáleným počítačem došlo k chybě modelu DCOM A. Přístup byl odepřen. ](https://docs.microsoft.com/visualstudio/debugger/a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied).  
  
Vzdálené ladění používá model DCOM ke komunikaci mezi místními a vzdálenými počítači v následujících situacích:  
  
-   Ladicí program je nastavena na **nativní režim kompatibility** nebo **spravovaný režim kompatibility** se změnami **nástroje / Možnosti / ladění** stránky  
  
-   Ladění spravovaného C++ (C + +/ CLI) kód.  
  
-   V sadě Visual Studio 2013 když **povolení nativní funkce upravit a pokračovat** se změnami **nástroje / Možnosti / ladění** stránky  
  
-   Některé třetích stran ladění scénářů  
  
 Tato chyba nastane, pokud proces sady Visual Studio se nemůže ověřit samotného (nebo zadané přihlašovací údaje byly za nedostatečné) k procesu vzdálený ladicí program přes model DCOM. Tento problém může vyřešit nejméně jednu z následujících náhradních postupů:  
  
-   Vypnout **nativní režim kompatibility** a **spravovaný režim kompatibility**.  
  
-   V sadě Visual Studio 2013 vypnout **povolení nativní funkce upravit a pokračovat**.  
  
-   Oba počítače restartujte.  
  
-   Pokud vzdálené ladění vyžaduje zadání přihlašovacích údajů, zaškrtněte možnost pro uložení přihlašovacích údajů.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)



