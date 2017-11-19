---
title: "Chyba: Lokality používá IP adresu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
ms.assetid: b2b8ddc8-746d-46e3-87a6-b956b1ee048d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e1ee3e2ed3d6524749757806931fbb8c4b9a36a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-site-uses-ip-address"></a>Chyba: Server používá adresu IP
K této chybě dojde, když se ladicí program se pokusí automaticky připojit k webové aplikaci, která používá IP adresu. K tomu dojde, pokud změníte **identifikaci webu** k **použít konkrétní IP adresu** ve službě IIS.  
  
 Pro automatické připojte k práci, budete muset vytvořit projekt s konkrétní IP adresu, nikoli jen název počítače. Ladicí program, jinak se změní název počítače localhost, což způsobí selhání odeslat příkaz debug do služby IIS.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Místo toho připojit pomocí ruční (v nabídce ladění zvolte **připojit k procesu**).  
  
     —nebo—  
  
2.  Změna **identifikace serveru webové služby IIS** nastavení.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)