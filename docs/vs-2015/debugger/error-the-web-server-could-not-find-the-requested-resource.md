---
title: 'Chyba: Webový Server nenalezl požadovaný prostředek | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 1ceeaf30-918c-42bb-ace1-96944530fef3
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b3904a9fcb2e15190018dbc4caabe925690e023f
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66263712"
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>Chyba: Webový server nemohl najít požadovaný prostředek.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Kvůli požadavky na zabezpečení služby IIS vrátilo Obecná chyba.  
  
 Jednou z možných příčin je konfigurace zabezpečení serveru. Služba IIS 6.0 a starší verze umožňuje aplikace doplňku, označované jako URLScan, filtrujte požadavky podezřelé nebo poškozený. Služba IIS 7.0 má integrované filtrování požadavků k tomuto účelu. V obou případech příliš omezující požadavek filtrování můžete zabránit sady Visual Studio ladění serveru.  
  
 Existuje mnoho možných příčin této chyby. Některé nejčastější příčiny patří potíže s instalaci služby IIS nebo konfigurace, konfiguraci webového serveru nebo oprávnění v systému souborů. Přístup k prostředku s prohlížečem, který můžete vyzkoušet. V závislosti na konfiguraci služby IIS, budete muset použít místní prohlížeč na serveru nebo zkontrolujte protokol chyb služby IIS k získání podrobné chybové zprávy.  
  
 Další informace o řešení potíží s IIS najdete v tématu [správu služby IIS a správu](http://go.microsoft.com/fwlink/?LinkId=255872).  
  
## <a name="see-also"></a>Viz také  
 [Nástroj UrlScan zabezpečení](/iis/extensions/working-with-urlscan/urlscan-3-reference)   
 [Chyba: Webový server je zamčený, a proto blokuje příkaz DEBUG.](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)
