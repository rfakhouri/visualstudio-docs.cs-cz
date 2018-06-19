---
title: 'ASP.NET ladění: Systémové požadavky | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications, system requirements
- debugging ASP.NET Web applications, security requirements
ms.assetid: 7810b9b2-debf-4271-8fc7-1df031123255
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: a0d591c9f68e5331b2047ee749fff148c8844937
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466367"
---
# <a name="aspnet-debugging-system-requirements"></a>ASP.NET Ladění: Systémové požadavky
Toto téma popisuje požadavky na software a zabezpečení pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] ladění scénáře:  
  
-   Místní ladění, ve kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a webovou aplikaci spustit ve stejném počítači. Existují dvě verze tohoto scénáře:  
  
    -   [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Kód se nachází v systému souborů.  
  
    -   [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Kód se nachází v webu služby IIS.  
  
-   Vzdálené ladění, ve kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] běží na klientském počítači a debugs webové aplikace, které běží na počítači vzdáleného serveru.  
  
## <a name="security-requirements"></a>Požadavky na zabezpečení  
 Pro vzdálené ladění, místních i vzdálených počítačů musí být v nastavení domény nebo pracovní skupiny nastavení.  
  
 Chcete-li ladit [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces (hostované ve fondu aplikací), musíte mít oprávnění k ladění tohoto procesu. Ve výchozím nastavení [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikací před jejich služby IIS 6.0 spustit jako **ASPNET** uživatele. Ve službě IIS 6.0 a IIS 7.0 **síťové služby** účet je výchozí hodnota. Pokud je pracovní proces spuštěn jako **ASPNET**, nebo jako **síťové služby**, musí mít oprávnění správce k ladění ho.

 > [!IMPORTANT]
 > Od verze Windows Server 2008 R2, doporučujeme použít [ApplicationPoolIdentity](/iis/manage/configuring-security/application-pool-identities) jako identity pro každý fond aplikací.
  
 Název [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces se liší podle ladění scénář a verze služby IIS. Další informace najdete v tématu [postupy: hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md).  
  
 Můžete změnit uživatelského účtu, který [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces spouští pod úpravou souboru machine.config. na serveru se spuštěnou službou IIS. Nejlepší způsob, jak to udělat, je použití **Správce Internetové informační služby (IIS)**. Další informace najdete v tématu [postup: Spusťte pracovní proces pod uživatelský účet](../debugger/how-to-run-the-worker-process-under-a-user-account.md).  
  
 Pokud změníte [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces spuštěn pod svůj vlastní uživatelský účet, nemusíte mít oprávnění správce na serveru se spuštěnou službou IIS.  
  
> [!CAUTION]
>  Než změníte [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces spuštěn pod jiným účtem, zvažte možné důsledky, pokud [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] by měl být pracovní proces hacker během spuštění pod tímto účtem. Uživatelské účty ASPNET a SÍŤOVOU službu spustit s minimálními oprávněními, sníží možné škody, pokud se hacker proces. Pokud je třeba změnit [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces spuštěn pod účtem, který má větší oprávnění, je možné škody větší.  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)   
 [Postupy: spuštění pracovního procesu pod účtem uživatele](../debugger/how-to-run-the-worker-process-under-a-user-account.md)