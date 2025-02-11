---
title: 'Ladění ASP.NET: Systémové požadavky | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 63a94f9ae6c35ef304af334737a8f206da911afd
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63402717"
---
# <a name="aspnet-debugging-system-requirements"></a>Ladění ASP.NET: Požadavky na systém
Toto téma popisuje požadavky na software a zabezpečení pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] ladění scénářů:

- Místní ladění, ve kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a webovou aplikaci spustit ve stejném počítači. Existují dvě verze tohoto scénáře:

  - [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Kód se nachází v systému souborů.

  - [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Kód se nachází na webu služby IIS.

- Vzdálené ladění, ve kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] běží na klientském počítači a ladí webovou aplikaci, která běží na vzdáleném serveru.

## <a name="security-requirements"></a>Požadavky na zabezpečení
 Pro vzdálené ladění, místních i vzdálených počítačů musí být v nastavení domény nebo pracovní skupiny nastavení.

 Chcete-li ladit [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovního procesu (hostitelem fond aplikací), musíte mít oprávnění pro ladění tohoto procesu. Ve výchozím nastavení [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace před IIS 6.0 spustit jako **ASPNET** uživatele. Ve službě IIS 6.0 a IIS 7.0 **síťová služba** účtu je výchozí nastavení. Pokud pracovní proces je spuštěn jako **ASPNET**, nebo jako **síťová služba**, musí mít oprávnění správce pro ladění.

 > [!IMPORTANT]
 > Od verze Windows Server 2008 R2, doporučujeme používat [ApplicationPoolIdentity](/iis/manage/configuring-security/application-pool-identities) jako identitu pro každý fond aplikací.

 Název [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces se liší podle scénáře ladění a verze služby IIS. Další informace najdete v tématu [jak: Hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md).

 Můžete změnit uživatelského účtu, který [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces běží pod tak, že upravíte soubor machine.config na serveru, na kterém běží služby IIS. Nejlepší způsob, jak to provést, je použít **Správce Internetové informační služby (IIS)**. Další informace najdete v tématu [jak: Spuštění pracovního procesu v rámci uživatelského účtu](../debugger/how-to-run-the-worker-process-under-a-user-account.md).

 Pokud změníte [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces pro spuštění v rámci vlastní uživatelský účet není potřeba mít oprávnění správce na serveru, na kterém běží služba IIS.

> [!CAUTION]
> Před změnou [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces spuštěn pod jiným účtem, pokud je to možné důsledků zvažte [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces by měl být zneužity během spuštění pod tímto účtem. Uživatelské účty ASPNET a NETWORK SERVICE spustit s minimálními oprávněními, pokud se hacker procesu snížení možné poškození. Pokud potřebujete změnit [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces spuštěn pod účtem, který má větší oprávnění, je možné škody větší.

## <a name="see-also"></a>Viz také

- [Ladění aplikací ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)
- [Postupy: Spuštění pracovního procesu pod uživatelským účtem](../debugger/how-to-run-the-worker-process-under-a-user-account.md)