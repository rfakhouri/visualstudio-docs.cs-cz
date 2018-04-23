---
title: 'Chyba: Webový Server nenalezl požadovaný prostředek | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
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
ms.openlocfilehash: 48d4a5845dd5e5f364d34544f57e1ef7bdfe6052
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>Chyba: Webový server nenalezl požadovaný prostředek.
Z hlediska zabezpečení služba IIS vrátila Obecná chyba.  
  
 Možnou příčinou je konfigurace zabezpečení serveru. Služby IIS 6.0 a starší verze použít rozšíření programu, označuje jako modulem URLScan filtrovat požadavky podezřelé a poškozený. IIS 7.0 má k tomuto účelu filtrování předdefinovaných požadavků. V obou případech filtrování žádostí příliš omezující zabránit v sadě Visual Studio ladění serveru.  
  
 Existuje řada možných příčin této chyby. Několik nejběžnější příčiny zahrnout problém s instalaci služby IIS nebo konfigurace, konfiguraci webového serveru nebo oprávnění systému souborů. Můžete zkusit přístupu k prostředku s prohlížečem. V závislosti na konfiguraci služby IIS, můžete chtít použít místní prohlížeč na serveru nebo zkontrolujte v protokolu chyb služby IIS k získání podrobné chybové zprávy.  
  
 Další informace o řešení potíží s IIS, naleznete v části [správu služby IIS a správa](http://go.microsoft.com/fwlink/?LinkId=255872).  
  
## <a name="see-also"></a>Viz také  
 [Nástroj UrlScan zabezpečení](http://www.microsoft.com/technet/security/tools/urlscan.mspx)   
 [Chyba: Webový Server byl uzamčen a blokuje příkaz DEBUG.](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)