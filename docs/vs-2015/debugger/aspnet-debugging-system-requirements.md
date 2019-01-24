---
title: 'Ladění ASP.NET: Systémové požadavky | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications, system requirements
- debugging ASP.NET Web applications, security requirements
ms.assetid: 7810b9b2-debf-4271-8fc7-1df031123255
caps.latest.revision: 41
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a6f50584c5e01b97eb00a0e7f62998670d033553
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54759110"
---
# <a name="aspnet-debugging-system-requirements"></a>Ladění ASP.NET: Požadavky na systém
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto téma popisuje požadavky na software a zabezpečení pro [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] ladění scénářů:  
  
-   Místní ladění, ve kterém [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a webovou aplikaci spustit ve stejném počítači. Existují dvě verze tohoto scénáře:  
  
    -   [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Kód se nachází v systému souborů.  
  
    -   [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Kód se nachází na webu služby IIS.  
  
-   Vzdálené ladění, ve kterém [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] běží na klientském počítači a ladí webovou aplikaci, která běží na vzdáleném serveru.  
  
## <a name="security-requirements"></a>Požadavky na zabezpečení  
 Pro vzdálené ladění, místních i vzdálených počítačů musí být v nastavení domény nebo pracovní skupiny nastavení.  
  
 Chcete-li ladit [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovního procesu, musíte mít oprávnění pro ladění tohoto procesu. Ve výchozím nastavení [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikace běží jako **ASPNET** uživatele. Pokud pracovní proces je spuštěn jako **ASPNET**, nebo jako **síťová služba**, musí mít oprávnění správce pro ladění.  
  
 Název [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces se liší podle scénáře ladění a verze služby IIS. Další informace najdete v tématu [jak: Hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md).  
  
 Můžete změnit uživatelského účtu, který [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces běží pod tak, že upravíte soubor machine.config na serveru, na kterém běží služby IIS. Nejlepší způsob, jak to provést, je použít **Správce Internetové informační služby (IIS)**. Další informace najdete v tématu [jak: Spuštění pracovního procesu v rámci uživatelského účtu](../debugger/how-to-run-the-worker-process-under-a-user-account.md).  
  
 Pokud změníte [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces pro spuštění v rámci vlastní uživatelský účet není potřeba mít oprávnění správce na serveru, na kterém běží služba IIS.  
  
> [!CAUTION]
>  Před změnou [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces spuštěn pod jiným účtem, pokud je to možné důsledků zvažte [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces by měl být zneužity během spuštění pod tímto účtem. Uživatelské účty ASPNET a NETWORK SERVICE spustit s minimálními oprávněními, pokud se hacker procesu snížení možné poškození. Pokud potřebujete změnit [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces spuštěn pod účtem, který má větší oprávnění, je možné škody větší.  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací ASP.NET a AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Postupy: Spuštění pracovního procesu pod uživatelským účtem](../debugger/how-to-run-the-worker-process-under-a-user-account.md)
