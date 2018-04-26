---
title: Zachování zabezpečení aplikací v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- unauthorized access
- Baseline Security Analyzer
- Microsoft Baseline Security Analyzer
- security [.NET Framework], best practices
- MBSA (Microsoft Baseline Security Analyzer)
- security [.NET Framework], maintaining after deployment
ms.assetid: 621d10c1-842b-4902-be60-bb9719591751
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee7a90804c2161fe927bebc2b2f1af45862b8ccd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="maintain-security"></a>Zachování zabezpečení

Často se říká, že cenou zabezpečení je neustálá bdělost. Navzdory maximální pozornosti věnované zabezpečení během navrhování a vývoje vaší aplikace byste měli předpokládat, že se po nasazení objeví určité problémy se zabezpečením. Auditováním aplikace a analýzou protokolů událostí můžete objevit některé dříve skryté závady.

Musíte být nejen ostražití ve vztahu ke své aplikaci, ale musíte mít také přehled o aktuálních bezpečnostních hrozbách a nedostatcích v případě platformy, na které aplikace běží, a v případě ostatních produktů, na kterých vaše aplikace závisí.

[Účty, zabezpečení a ochrany osobních údajů](https://support.microsoft.com/products/microsoft-account?category=privacy#security-privacy-accounts-help=windows-8&v0h=winrttab1&v1h=win8tab1&v2h=win7tab1&v3h=winvistatab1)&mdash;získat pomoc s zabezpečení, ochrany osobních údajů a uživatelské účty, včetně informací o viry, hesla, rodičovské kontroly, brány firewall a jednotky šifrování...

[Aktualizace zabezpečení Microsoft bulletiny](https://technet.microsoft.com/security/bulletins.aspx)&mdash;Tato stránka umožňuje snadno najít dřív vydané bulletiny. Bulletiny zabezpečení jsou určeny pro odborníky v oblasti IT a poskytují podrobné informace o aktualizacích zabezpečení.

[Microsoft Baseline Security Analyzer](https://www.microsoft.com/download/details.aspx?id=7558)&mdash;Microsoft Baseline Security Analyzer (MBSA) je nástroj, který umožňuje jednotlivé domácí uživatel, podnikové uživatele nebo správce ke kontrole jedné nebo více založené na Windows počítačích běžné chyby konfigurace zabezpečení.