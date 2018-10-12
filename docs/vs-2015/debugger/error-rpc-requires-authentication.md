---
title: 'Chyba: RPC vyžaduje ověření. | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 88362b3b-8fbe-431f-96a4-80e2d822bbc7
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5643e815386541bb9045eb56cacbd68e7e9b998d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49193828"
---
# <a name="error-rpc-requires-authentication"></a>Chyba: RPC vyžaduje ověření.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio debugger se nemůže připojit ke vzdálenému počítači. Zásady protokolu RPC je povoleno v místním počítači, což znemožňuje vzdálené ladění.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Spustit `\` *windir*`\system32\regedt32.exe`  
  
2.  Vyhledejte a odstraňte `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`.  
  
3.  Změna v registru se projeví až po restartování počítače.  
  
4.  Pokud se problém nevyřeší, obraťte se na správce domény o **konfigurace počítače -> šablony pro správu - > Systém -> vzdálené volání procedury -> omezení pro klienty neověřené RPC** skupiny nastavení zásad.



