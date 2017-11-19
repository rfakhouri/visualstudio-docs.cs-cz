---
title: "Chyba: RPC vyžaduje ověření. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 88362b3b-8fbe-431f-96a4-80e2d822bbc7
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3431ee286787d99e8601fbed7cad3012ffcaf68e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-rpc-requires-authentication"></a>Chyba: RPC vyžaduje ověření.
Ladicí program Visual Studio se nemůže připojit ke vzdálenému počítači. Zásada protokolu RPC je povoleno v místním počítači, což zabraňuje vzdálené ladění.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Spustit `\` *windir*`\system32\regedt32.exe`  
  
2.  Vyhledejte a odstraňte `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`.  
  
3.  Změna v registru se projeví až po restartování počítače.  
  
4.  Pokud potíže potrvají, obraťte se na správce domény o **konfigurace počítače > šablony pro správu > Systém > vzdálené volání procedur > omezení pro klienty neověřené RPC** zásady skupiny nastavení.