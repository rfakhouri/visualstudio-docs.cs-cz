---
title: Přehled výkonnostní relace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools, performance session
- performance sessions
ms.assetid: 35752f95-a57a-4def-b64d-cf4899669e99
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0631838abf8ccea06661bbf381337d7aa62082d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="performance-session-overview"></a>Přehled výkonnostní relace
Tento přehled popisuje základní informace o vytváření profilů. Vývojáři, kteří jsou pro nové pracovní výkonu zobrazí jak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci mohou pomoci produktivitu rychle a zvýšit výkon svůj kód. Vývojáři, kteří mají zkušenosti v profilaci může získat přehled o konkrétní nástrojích pro profilaci funkce a procesy.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Profilování nástroje vám pomohou identifikovat problémy s výkonem ve zdrojovém kódu a porovnejte výkon možná řešení. Profilace průvodcích nástroje a výchozí nastavení můžete získáte okamžitý přehled o mnoho problémů s výkonem. Funkce a možnosti nástroje pro profilaci zadejte přesně řídit proces profilování. Tento ovládací prvek obsahuje přesné cílení na části kódu, shromažďování informací a časování na úrovni bloků a zahrnutí další data o výkonu procesoru a systému ve vašich datech.  
  
 Následující kroky tvoří základní proces pomocí nástrojů pro profilaci:  
  
1.  Výkonnostní relace nakonfigurujte tak, že zadáte metody shromažďování a data, která chcete shromažďovat.  
  
2.  Shromážděte data profilování spuštěním aplikace v relaci výkonu.  
  
3.  Analyzujte data a identifikovat problémy s výkonem.  
  
4.  Upravit kód v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) pro zvyšuje výkon aplikace kódu  
  
5.  Shromažďovat data profilování změněné kódu a porovnejte data profilování dat původní a změněné.  
  
6.  Vygenerujte sestavu, která dokumenty zvýšení výkonu.  
  
 Při práci s informacemi, které poskytuje profilace, byste měli mít k dispozici pro binární soubory, které chcete profil a binární soubory operačního systému Windows informací o symbolu.  
  
## <a name="configure-the-performance-session"></a>Konfigurace výkonnostní relace  
 Pro konfiguraci relace profilování, vyberte metodu, kterou chcete použít profilování a data, která chcete shromažďovat. Nástroje pro profilaci **Průvodce výkonu** může vás provede základní konfiguraci a stránky vlastností výkonnostní relace můžete přidat další možnosti:  
  
-   Profilování metody zahrnují vzorkování, trasování a přidělování paměti.  
  
-   Hodnoty data zahrnují čas procesoru a čítače výkonu operačního systému a události aplikace například chyb stránek a přechody jádra.  
  
 Výkonnostní relace v můžete nakonfigurovat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu jako součást řešení projektu, nebo profil libovolný binární soubory prostřednictvím [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Můžete zadat vlastnosti relace na stránkách vlastností výkonnostní relace nebo můžete použít Průvodce profilace.  
  
## <a name="collect-profiling-data"></a>Shromažďování dat profilaci  
 Spustit profilování data z kolekce **prohlížeč výkonu**. Můžete pozastavit a obnovit, profilace omezit množství dat, které shromažďujete. Také můžete připojit k procesu, který je již spuštěn.  
  
 Při spuštění aplikace **ovládací prvek kolekce dat** zobrazí okno [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Z **ovládací prvek kolekce dat** můžete profil konkrétní částí aplikace pomocí pozastavení a obnovení proces shromažďování. Můžete také **ovládací prvek kolekce dat** okno značky vložení do data, která se shromažďují. Značky jsou uživatelem definované datové body, které jsou zobrazeny v zobrazení profil a který mohou být použity k filtrování data profilování.  
  
 Při vypnutí cílová aplikace nástrojích pro profilaci generuje profilování datový soubor (*.vsp) a zobrazení Souhrnná sestava v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE.  
  
## <a name="analyze-the-data-and-identify-performance-issues"></a>Analýza dat a identifikovat problémy s výkonem  
 Po ukončení profilace spustit, data se analyzují a zobrazí se souhrn v nástrojích pro profilaci **Sestava výkonu** zobrazení systému windows. Profilace data se shromažďují pro zásobník volání a jednotlivých funkcí cílová aplikace. Sestava analýzy výkonu pro rozsahy dat procesy, vláken, moduly, funkce a řádků zdrojového kódu aplikace zobrazí zobrazení. Profilace dat pro funkci následující hodnoty:  
  
-   Celkový čas, který byl stráven ve funkci a v podřízených funkce, které byly volá funkci (včetně hodnoty).  
  
-   Čas, kdy byla potřebná k provedení pouze kód ve funkci (výhradní hodnoty).  
  
 Více než dvanáct různá zobrazení umožňují analyzovat data profilování nejefektivnějším způsobem. Přizpůsobení zobrazení umožňují filtrovat a řadit data a vyhledávat funkce, které mohou způsobovat problémy s výkonem. Aktivní cesta filtrování poskytuje okamžité zvýraznění Nejaktivnější cesty v zobrazení stromu volání a modulu.  
  
## <a name="modify-the-application-code"></a>Upravit kód aplikace  
 Po mají izolované jeden nebo více problémů s výkonem relevantní, můžete upravit kód pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE a pak shromažďování dat pro změny profilaci.  
  
## <a name="collect-profiling-data-again-and-compare-the-data-between-the-profiling-runs"></a>Shromažďování dat znovu profilaci a porovnávání dat mezi profilování běží  
 Zobrazení sestavy profilace porovnání nástrojů zobrazí rozdíl v modulu, funkce nebo výkonu řádek mezi dvě datových souborů profilace vybrané. Můžete zadat profilování datových hodnot, které chcete porovnat, a můžete přepínat mezi porovnání zobrazení a zobrazení jednotlivých souborů.  
  
## <a name="generate-a-report-of-the-results"></a>Vygenerování sestavy výsledků  
 Řádky všechna zobrazení sestavy výkonu můžete vložit do e-mailů a tabulek a můžete generovat sestavy, které obsahují data pro jeden nebo více zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Přehled](../profiling/overviews-performance-tools.md)   
 [Návod: Identifikace problémy s výkonem](../profiling/walkthrough-identifying-performance-problems.md)