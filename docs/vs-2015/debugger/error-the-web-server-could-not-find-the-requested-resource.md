---
title: 'Chyba: Webový Server nelze najít požadovaný prostředek | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 1ceeaf30-918c-42bb-ace1-96944530fef3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc41673da6157306cd0e4e66070717d5745d6218
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627432"
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>Chyba: Webový server nenalezl požadovaný prostředek.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: Webový Server nenalezl požadovaný prostředek](https://docs.microsoft.com/visualstudio/debugger/error-the-web-server-could-not-find-the-requested-resource).  
  
Kvůli požadavky na zabezpečení služby IIS vrátilo Obecná chyba.  
  
 Jednou z možných příčin je konfigurace zabezpečení serveru. Služba IIS 6.0 a starší verze umožňuje aplikace doplňku, označované jako URLScan, filtrujte požadavky podezřelé nebo poškozený. Služba IIS 7.0 má integrované filtrování požadavků k tomuto účelu. V obou případech příliš omezující požadavek filtrování můžete zabránit sady Visual Studio ladění serveru.  
  
 Existuje mnoho možných příčin této chyby. Některé nejčastější příčiny patří potíže s instalaci služby IIS nebo konfigurace, konfiguraci webového serveru nebo oprávnění v systému souborů. Přístup k prostředku s prohlížečem, který můžete vyzkoušet. V závislosti na konfiguraci služby IIS, budete muset použít místní prohlížeč na serveru nebo zkontrolujte protokol chyb služby IIS k získání podrobné chybové zprávy.  
  
 Další informace o řešení potíží s IIS najdete v tématu [správu služby IIS a správu](http://go.microsoft.com/fwlink/?LinkId=255872).  
  
## <a name="see-also"></a>Viz také  
 [Nástroj UrlScan zabezpečení](http://www.microsoft.com/technet/security/tools/urlscan.mspx)   
 [Chyba: Webový Server byl uzamčen a blokuje příkaz DEBUG.](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)



