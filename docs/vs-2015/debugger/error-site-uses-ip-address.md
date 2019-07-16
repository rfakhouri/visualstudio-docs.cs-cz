---
title: 'Chyba: Server používá adresu IP | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: b2b8ddc8-746d-46e3-87a6-b956b1ee048d
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 46eace1c566a2810c5914a49654f8393f425fdee
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68155755"
---
# <a name="error-site-uses-ip-address"></a>Chyba: Server používá IP adresu.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

K této chybě dochází, když se ladicí program se pokusí o automatické připojení k webové aplikaci, která používá IP adresu. K tomu dojde, pokud změníte **identifikaci webu** k **použít konkrétní IP adresu** ve službě IIS.  
  
 Pro automatické připojení k práci, je potřeba vytvořit projekt s konkrétní IP adresu, nikoli jen název počítače. Ladicí program v opačném případě se změní název počítače na místního hostitele, což způsobí selhání odeslat příkaz debug. do služby IIS.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1. Použití ručně připojit místo toho (v nabídce ladění zvolte **připojit k procesu**).  
  
     —nebo—  
  
2. Změnit **identifikace serveru služby IIS** nastavení.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
