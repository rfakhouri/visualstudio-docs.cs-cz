---
title: Při pokusu o spojení se vzdáleným počítačem došlo k chybě modelu DCOM. Přístup byl zamítnut. | Dokumenty Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0157b1ade2c38a2c10920b9674d7c9a58ac036b2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54796066"
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Při pokusu o spojení se vzdáleným počítačem došlo k chybě modelu DCOM. Přístup byl zamítnut.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vzdálené ladění používá model DCOM ke komunikaci mezi místními a vzdálenými počítači v následujících situacích:  
  
- Ladicí program je nastavena na **nativní režim kompatibility** nebo **spravovaný režim kompatibility** se změnami **nástroje / Možnosti / ladění** stránky  
  
- Ladění spravovaného C++ (C + +/ CLI) kód.  
  
- V sadě Visual Studio 2013 když **povolení nativní funkce upravit a pokračovat** se změnami **nástroje / Možnosti / ladění** stránky  
  
- Některé třetích stran ladění scénářů  
  
  Tato chyba nastane, pokud proces sady Visual Studio se nemůže ověřit samotného (nebo zadané přihlašovací údaje byly za nedostatečné) k procesu vzdálený ladicí program přes model DCOM. Tento problém může vyřešit nejméně jednu z následujících náhradních postupů:  
  
- Vypnout **nativní režim kompatibility** a **spravovaný režim kompatibility**.  
  
- V sadě Visual Studio 2013 vypnout **povolení nativní funkce upravit a pokračovat**.  
  
- Oba počítače restartujte.  
  
- Pokud vzdálené ladění vyžaduje zadání přihlašovacích údajů, zaškrtněte možnost pro uložení přihlašovacích údajů.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)
