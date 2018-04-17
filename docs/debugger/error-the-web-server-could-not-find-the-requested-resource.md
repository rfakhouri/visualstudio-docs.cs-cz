---
title: 'Chyba: Webový Server nenalezl požadovaný prostředek | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fcac96e2ffaaca86534d65ee16d51e1ce2dfa721
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>Chyba: Webový server nenalezl požadovaný prostředek.
Z hlediska zabezpečení služba IIS vrátila Obecná chyba.  
  
 Možnou příčinou je konfigurace zabezpečení serveru. Služby IIS 6.0 a starší verze použít rozšíření programu, označuje jako modulem URLScan filtrovat požadavky podezřelé a poškozený. IIS 7.0 má k tomuto účelu filtrování předdefinovaných požadavků. V obou případech filtrování žádostí příliš omezující zabránit v sadě Visual Studio ladění serveru.  
  
 Existuje řada možných příčin této chyby. Několik nejběžnější příčiny zahrnout problém s instalaci služby IIS nebo konfigurace, konfiguraci webového serveru nebo oprávnění systému souborů. Můžete zkusit přístupu k prostředku s prohlížečem. V závislosti na konfiguraci služby IIS, můžete chtít použít místní prohlížeč na serveru nebo zkontrolujte v protokolu chyb služby IIS k získání podrobné chybové zprávy.  
  
 Další informace o řešení potíží s IIS, naleznete v části [správu služby IIS a správa](http://go.microsoft.com/fwlink/?LinkId=255872).  
  
## <a name="see-also"></a>Viz také  
 [Nástroj UrlScan zabezpečení](http://www.microsoft.com/technet/security/tools/urlscan.mspx)   
 [Chyba: Webový Server byl uzamčen a blokuje příkaz DEBUG.](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)