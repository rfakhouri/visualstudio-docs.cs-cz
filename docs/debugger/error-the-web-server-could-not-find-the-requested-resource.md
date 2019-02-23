---
title: 'Chyba: Webový Server nenalezl požadovaný prostředek | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c0b37e96db46a43b869867b8b5e37f857e75aff9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56705648"
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>Chyba: Webový Server nenalezl požadovaný prostředek
Kvůli požadavky na zabezpečení služby IIS vrátilo Obecná chyba.

Jednou z možných příčin je konfigurace zabezpečení serveru. Služba IIS 6.0 a starší verze umožňuje aplikace doplňku, označované jako URLScan, filtrujte požadavky podezřelé nebo poškozený. Služba IIS 7.0 má integrované filtrování požadavků k tomuto účelu. V obou případech příliš omezující požadavek filtrování můžete zabránit sady Visual Studio ladění serveru.

Další možnou příčinou této chyby je, že není spuštěná služba W3SVC pro službu IIS. Zkontrolujte, že tato služba je spuštěna (šedě) v okně služby (*services.msc*).

Existuje mnoho další možné příčiny této chyby. Některé nejčastější příčiny patří potíže s instalaci služby IIS nebo konfigurace, konfiguraci webového serveru nebo oprávnění v systému souborů. Přístup k prostředku s prohlížečem, který můžete vyzkoušet. V závislosti na konfiguraci služby IIS budete muset použít místní prohlížeč na serveru nebo zkontrolujte protokol chyb služby IIS k získání podrobné chybové zprávy.

 Další informace o řešení potíží s IIS najdete v tématu [správu služby IIS a správu](/iis/manage/provisioning-and-managing-iis/iis-management-and-administration).

## <a name="see-also"></a>Viz také
- [Chyba: Webový server je zamčený, a proto blokuje příkaz DEBUG.](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)