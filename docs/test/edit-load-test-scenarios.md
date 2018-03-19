---
title: "Úpravy scénářů zátěžových testů v sadě Visual Studio | Microsoft Docs"
ms.date: 10/03/2016
ms.topic: article
helpviewer_keywords:
- load tests, scenarios
- load tests, user activities
- load tests, modeling scenarios
ms.assetid: fec04f2e-bf38-4d44-b2ec-fa50f58fd0d9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 5b4abcb0b75e379df360c045527790a708c55c6e
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="edit-load-test-scenarios"></a>Úpravy scénářů zátěžových testů

Zátěžový test *scénář* Určuje vzor zatížení, kombinace testů, kombinace prohlížeče a kombinace sítí. Scénáře jsou důležité, protože ty umožňují konfigurace testů k simulaci komplexní, realistické úlohy.

Může být například testování web elektronického obchodu, která má Internetu, front-endu používá o stovky souběžných zákazníků procházející přes mnoho rychlosti připojení a použití různých prohlížečích. Stejné lokalitě také může mít funkce správy, která je použita vnitřní zaměstnanci aktualizace produktů a zobrazení statistik. Tyto interní uživatele by obvykle přístup k webu pomocí stejného prohlížeče a vysokorychlostní připojení k síti LAN. Můžete chtít zapouzdření vlastnosti tyto dvě různé skupiny uživatelů v různých scénářích. Každý scénář může obsahovat typ virtuálního uživatele. V takovém případě scénáře zátěžového testu provádět představují virtuální zákazníky a jiné scénáře můžete provést představují virtuální interní uživatele webové stránky.

## <a name="scenario-components"></a>Součásti scénáře

Všechny možnosti počáteční konfigurace a nastavení, které zadáte, když vytvoříte zátěžový test, může upravit později v editoru načíst otestovat. Můžete také přidat nové scénáře, spusťte nastavení a sady čítačů pro zátěžový test.

![Scénářů zátěžových testů](../test/media/loadtesteditinscenarios.png)

Scénáře obsahují následující komponenty:

|||
|-|-|
|Termín|Definice|
|Kombinace prohlížeče|Simuluje, že virtuální uživatelé přístup k webu prostřednictvím řady různých webových prohlížečů.|
|Vzor zatížení|Určuje počet virtuálních uživatelů, kteří jsou aktivní během zátěžového testu a rychlost, jakou jsou spuštění noví uživatelé. Příklad: krok, konstanty a na základě cíle.|
|Model kombinace testů|Určuje pravděpodobnost spuštění testu dané ve scénáři zátěžového testu virtuálním uživatelem. Příklad: 20 % šance ke spuštění TestA a 80 % šance spustit TestB. Model kombinace testů by měla odpovídat cílů svůj test pro konkrétní scénář.|
|Poměr testů|Kombinace testů je výběr webové výkonu a jednotka testy, které tvoří scénář a distribuci tyto testy.|
|Kombinace sítí|Simuluje, že virtuální uživatelé přístup k webu prostřednictvím řady různých síťových připojení. Kombinace sítí nabízí možnosti, které zahrnují LAN, kabelový modem a další možnosti.|

Scénář má několik dalších vlastností, které můžete upravit pomocí editoru zátěžových testů. Další informace najdete v tématu [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Přidat pozastaví umělé zásahem ze strany ve vašem scénáři:** vezměte v úvahu doby se používají k simulaci lidského chování, jež způsobuje lidí, kteří budou čekat mezi interakce s webovou stránku. Dob uvažování dojít mezi požadavků v testu výkonnosti webu a mezi iterací testů ve scénáři zátěžového testu. Pomocí časů přemýšlení v zátěžovém testu může být užitečné při vytváření přesnější simulace zatížení.|-   [Úpravy dob uvažování pro simulaci prodlev při interakci s lidským webové stránky](../test/edit-think-times-in-load-test-scenarios.md)|
|**Zadejte počet virtuálních uživatelů pro váš scénář:** můžete konfigurovat vlastnosti vzor zatížení k určení, jak se upraví zatížení simulované uživatelů během zátěžového testu. Získat tří vzorů předdefinované zatížení: Konstanta, krok a na základě cíle. Zvolte vzor zatížení a upravit vlastnosti k odpovídající úrovně cílů testu zatížení.|-   [Úpravy vzorů zatížení pro modelování aktivit virtuálních uživatelů](../test/edit-load-patterns-to-model-virtual-user-activities.md)|
|**Konfigurace pravděpodobnost virtuálních uživatelů ve scénáři spuštění testu:** můžete použít kombinace testů, které určuje pravděpodobnost spuštění testu dané ve scénáři zátěžového testu virtuálním uživatelem. To umožňuje více reálně simulovat zatížení. Místo nutnosti jenom jeden pracovní postup prostřednictvím aplikací, může mít několik pracovních postupů, která je blíž aproximace o tom, jak koncoví uživatelé komunikovat s vašimi aplikacemi.|-   [Úpravy modelů kombinací](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)|
|**Přidat nebo odebrat z scénáře zátěžového testu výkonu nebo jednotka testu webu:** lze přidávat nebo odebírat testu výkonu nebo jednotka webu z ve scénáři zátěžového testu. Zátěžový test obsahuje jeden nebo více scénářů, z nichž každý obsahuje jeden nebo více testů výkonu nebo jednotka Web.|-   [Úpravy kombinace testů](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**Nakonfigurujte požadované sítě kombinace pro váš scénář:** pomocí kombinace sítí, můžete simulovat zatížení sítě tím realisticky ve scénáři zátěžového testu. Zatížení je generována pomocí heterogenní kombinaci různých typů sítě místo jeden typ jedné sítě. Můžete vytvořit blíže aproximace o tom, jak koncoví uživatelé komunikovat s vašimi aplikacemi. Model kombinace sítě by mělo reflektovat cílů tento scénář.|-   [Určení typů virtuálních sítí](../test/specify-virtual-network-types-in-a-load-test-scenario.md)|
|**Vyberte vhodnou kombinaci webového prohlížeče pro váš scénář:** pomocí kombinace prohlížeče, můžete simulovat zatížení webové více reálně ve scénáři zátěžového testu. Zatížení je generována pomocí heterogenní směs prohlížeče místo jeden jednoho prohlížeče. Můžete vytvořit blíže aproximace prohlížečů, které budou použity s vašimi aplikacemi.|-   [Určení typů webových prohlížečů](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**Konfigurace nastavení iterací testů pro váš scénář:** můžete upravit scénáře zátěžového testu ke konfiguraci nastavení iterací testů pomocí editoru načíst testování a v okně Vlastnosti. Ve výchozím nastavení je scénáři nastavit se žádné maximálního počtu testovacích iterací. Volitelně můžete nakonfigurovat maximální počet opakování ve scénáři a jak dlouho chcete pozastavit mezi nimi.|-   [Konfigurace iterací testů ve scénářích](../test/configure-test-iterations-in-a-load-test-scenario.md)|
|**Konfigurace nastavení zpoždění pro váš scénář:** pomocí editoru načíst testování a okna vlastností, můžete nastavit zpoždění před zahájením scénáři v zátěžovém testu. Příklad, kdy můžete chtít použít **čas spuštění zpoždění** vlastnost je, pokud je třeba jeden scénář zahájíte vytváření položek, které využívá jiný scénář. Může pozdržet náročné scénář povolit vytváření scénář k naplnění některá data.|-   [Konfigurace zpoždění pro spuštění scénáře](../test/configure-scenario-start-delays.md)|
|**Zadejte vzdálené počítače používat ve scénáři zátěžového testu:** poté, co vytvoříte zátěžový test, můžete upravit vlastnosti vaše scénáře zátěžového testu označíte, které testovacích agentů, které chcete zahrnout. Další informace najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).|-   [Postupy: určení použitých testovacích agentů pro použití](../test/how-to-specify-test-agents-to-use-in-load-test-scenarios.md)|

## <a name="see-also"></a>Viz také

- [Úpravy zátěžových testů](../test/edit-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)