---
title: Upgrade SCVMM 2008 R2 na SCVMM 2012 | Microsoft Docs
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Upgrade SCVMM 2008 R2 to SCVMM 2012, test lab
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 51d907dfe25d8f27065b2a4d8bbecaa3e98e42a1
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="upgrade-scvmm-2008-r2-to-scvmm-2012"></a>Upgrade SCVMM 2008 R2 na SCVMM 2012

Lab Management pro Team Foundation Server podporuje SCVMM 2008 R2 a SCVMM 2012. Pokud provádíte upgrade Team Foundation Server 2013 pro Team Foundation Server 2015 a plánujete provést upgrade SCVMM 2008 R2 na SCVMM 2012, doporučujeme, abyste po dokončení upgradu na Team Foundation Server 2015 upgrade na SCVMM 2012. Toto téma popisuje postup upgradu na SCVMM 2012 SCVMM 2008 R2, když používáte Lab Management na Team Foundation Server 2015.
Lab Management **nemá** podporu SCVMM 2016. 

**Důležité:** při upgradu SCVMM určité kroky budou způsobit výpadky pro vaše Team Foundation Server. Najdete níže uvedeného postupu.

## <a name="upgrading-to-scvmm-2012"></a>Upgrade na SCVMM 2012

1. Použití instalačního programu SCVMM 2012 upgradovat SCVMM 2008 R2 Server SCVMM 2012 serveru.

1. Upgradujte SCVMM agenty na hostitelích a sdílené složky knihovny.

1. Pomocí konzoly pro správu SCVMM ověřte všechny součásti SCVMM práce.

1. Nainstalujte konzolu správy SCVMM 2012 na všechny počítače v aplikační vrstvě Team Foundation serveru.

1. Použití **iisreset** příkaz k restartování webové služby Team Foundation Server. Potom restartujte úlohu agenta Team Foundation Server.

   **Upozornění:** tento krok bude narušit služby na serveru Team Foundation Server.

1. Upgrade dat a šablon v databázi služby collection každý projekt tak, aby byl kompatibilní s SCVMM 
   2012.

   Otevřete příkazový řádek se zvýšenými oprávněními na serveru Team Foundation Server a zadejte následující příkaz:

   **C:\\Program Files\\Microsoft Team Foundation Server 14.0\\nástroje\> /collectionName /upgradeSCVMM tfsconfig testovacího prostředí:\***

   Při použití **upgradeSCVMM** příkaz, Team Foundation Server vytvoří nový objekt šablony na vašem serveru SCVMM pro každý týmový projekt, který používá tato šablona. Tím se zajistí, aby vaše šablony upgradovali na být kompatibilní s SCVMM 2012 bez ztráty dat. Ale když se vytváří nové šablony, připojí se k názvu šablony název týmového projektu.

   **Upozornění:**  
   Pokud nový název šablony je větší než 64 znaků, způsobí chybu SCVMM. Pokud chcete tuto chybu vyřešit, musí tyto šablony zadejte kratší název. Pokud dojde k nějaké chyby nebo upozornění při spuštění tohoto příkazu, vyřešte tyto chyby další části. Pokud narazíte nejsou žádné chyby nebo upozornění, upgrade je úplný a můžete začít používat prostředí SCVMM s Lab Management.

## <a name="resolving-errors-and-warnings-when-using-the-upgradescvmm-command"></a>Vyřešte chyby a upozornění při použití příkazu upgradeSCVMM

Po použití **upgradeSCVMM** příkaz, musíte vyřešit všechny chyby nebo upozornění můžete přijímat a poté znovu spusťte příkaz před zahájením použití produktu Lab Management. **UpgradeSCVMM** příkaz vygeneruje soubor protokolu, který obsahuje informace o všechny chyby a varování, na které narazíte. Umístění souboru protokolu se zobrazí při spuštění **upgradeSCVMM** příkaz.

**Selhání SCVMM:** obdržíte chybu, která souvisí s chybu SCVMM, pomocí vaší historie úlohy SCVMM získat další informace o této chybě. Po vyřešení chyby v SCVMM znovu spustit **upgradeSCVMM** příkaz.

## <a name="see-also"></a>Viz také

* [Změna existující konfigurace služby Lab Management](https://msdn.microsoft.com/library/ee704508%28v=vs.140%29.aspx)
