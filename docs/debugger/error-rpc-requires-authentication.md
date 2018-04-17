---
title: 'Chyba: RPC vyžaduje ověření. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7134a52f4c219b985cff3174703cf217057a5150
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-rpc-requires-authentication"></a>Chyba: RPC vyžaduje ověření.
Ladicí program Visual Studio se nemůže připojit ke vzdálenému počítači. Zásada protokolu RPC je povoleno v místním počítači, což zabraňuje vzdálené ladění.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Spustit `\` *windir*`\system32\regedt32.exe`  
  
2.  Vyhledejte a odstraňte `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`.  
  
3.  Změna v registru se projeví až po restartování počítače.  
  
4.  Pokud potíže potrvají, obraťte se na správce domény o **konfigurace počítače > šablony pro správu > Systém > vzdálené volání procedur > omezení pro klienty neověřené RPC** zásady skupiny nastavení.