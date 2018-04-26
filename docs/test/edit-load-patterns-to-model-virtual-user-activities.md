---
title: Vzory zátěže testování v sadě Visual Studio zátěže
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, load patterns
- load tests, scenarios
- load tests, virtual users
ms.assetid: 0ba0363b-7f50-4bde-a919-0e3bce7bc115
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e9babedd5920f81dd4a0e2bc244acb21f0965d22
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="edit-load-patterns-to-model-virtual-user-activities"></a>Úpravy vzorů zatížení pro modelování aktivit virtuálních uživatelů

Vlastnosti vzor zatížení zadejte, jak se upraví zatížení simulované uživatelů během zátěžového testu. Visual Studio poskytuje tři vzory předdefinované zatížení: Konstanta, krok a na základě cíle. Zvolte vzor zatížení a upravit vlastnosti k odpovídající úrovně cílů testu zatížení.

Vzor zatížení je součástí scénáře. Scénáře, spolu s jejich vzorů definované zatížení tvoří zátěžový test.

> [!NOTE]
> Ve všech vzory zatížení zatížení, která generuje Visual Studio je simulované zatížení virtuálních uživatelů.

## <a name="load-patterns"></a>Vzory zátěže

### <a name="constant"></a>Konstanta

 Vzor konstantní zatížení slouží k určení zatížení uživatele, který se nemění během zátěžového testu. Při spuštění testu kouře na webovou aplikaci, můžete chtít nastavit světla, konstantní zatížení 10 uživatelů.

#### <a name="constant-load-pattern-considerations"></a>Aspekty vzor konstantní zatížení

 Vzor konstantní zatížení slouží ke spouštění stejné zatížení uživatele během spuštění zátěžového testu. Být opatrní při používání vzor konstantní zatížení, která má počet vysoké uživatelů; to proto může umístit nepřiměřený a reálné poptávky na server nebo servery na začátku zátěžový test. Například pokud zátěžového testu obsahuje testu webu, který začíná požadavek na domovskou stránku a nastavit zátěžového testu s konstantní zatížení 1 000 uživatelů, zátěžového testu budou odesílat prvních 1000 požadavků na domovskou stránku co nejrychleji. Toto nemusí být realistické simulace reálného přístup k webu. Toto riziko lze snížit, zvažte použití vzor zatížení kroku, který zvýší postupně na každých 1000 uživatelů, nebo zadejte dobu zahřívání v parametrů běhu testu zatížení. Pokud je zadán warm-up období, zátěžový test automaticky zvýší zatížení postupně během období warm-up 1.0. Další informace najdete v tématu [zpoždění spuštění scénáře konfigurace](../test/configure-scenario-start-delays.md).

### <a name="step"></a>Krok

 Vzor zatížení kroku slouží k určení zatížení uživatele, který se zvyšuje s časem až zatížení definovaný maximální uživatele. Pro zanoříte se zatížením, zadejte **počáteční počet uživatelů**, **maximální počet uživatelů**, **krok trvání (v sekundách)**, a **počet uživatelů krok**.

 Například krok zatížení s **počáteční uživatele** , počet **maximální počet uživatelů** 100 **krok trvání (v sekundách)** 10 a **počet uživatelů krok** 1 vytvoří vzor zatížení uživatele, který začíná na 1, zvýší o 1 každých 10 sekund, dokud nebude dosaženo 100 uživatelů.

> [!NOTE]
> Pokud doba trvání celkový testu je kratší než čas, které jsou potřeba ke kroku až zatížení maximální uživatele, test přestane po uplynulá doba trvání a nedojde k dosažení maximální počet uživatelů cíl.


 Cílem kroku můžete zvýšit zatížení, dokud nebude server dosáhne bod, kde se výrazně snižuje výkon. Když se zátěž zvyšuje, server nakonec dostatek prostředků. Zatížení krok je vhodný způsob, jak určit počet uživatelů, na kterých k tomu dochází. S taktování zatížení máte také monitorovat agenta prostředky úzce a ujistěte se, že agentů můžete generovat požadované zatížení.

 Normálně by měly provádět několik spustí, které mají různé krok doby a počty krok uživatele tak, aby můžete získat dobrý měření u daného zatížení. Načítání často, zobrazit počáteční Špička pro každý krok, protože jsou přidáni uživatelé. Podniku zatížení v tomto kurzu umožňuje měřit výkon systému po systém obnovuje z počáteční Špička.

#### <a name="step-load-pattern-considerations"></a>Aspekty vzor zatížení kroku

 Vzor zatížení kroku slouží ke zvýšení zatížení na serverech, jako zatížení test spustí tak, abyste viděli, jak výkon se liší jako zvyšuje zatížení uživatele. Například pokud chcete zobrazit, jak provést serveru nebo serverů při rostoucí zátěži uživatele na 2 000 uživatelů, můžete spustit 10 hodin zátěžový test pomocí vzor zatížení kroku, který má následující vlastnosti:

-   Počáteční počet uživatelů: 100

-   Maximální počet uživatelů: 2 000

-   Krok trvání (v sekundách): 1 800

-   Krok doběhu doba (v sekundách): 20

-   Počet uživatelů krok: 100

 Tato nastavení, spusťte zátěžový test 30 minut (1 800 sekund) na uživatele načte 100, 200, 300 a až 2 000 uživatelů. **Čas doběhu kroku** vlastnost je vhodné zvláštní pozornost, protože je jenom jedna z těchto vlastností, která není k dispozici pro výběr v Průvodci novým testu zatížení. Tato vlastnost umožňuje zvýšení z jednoho kroku na další (například ze 100 až 200 uživatelů) dojde k postupně místo okamžitě. V příkladu zatížení uživatele by být zvýšena od 100 na 200 uživatelů po dobu 20 sekundu (zvýšení pět uživatelů za sekundu). Další informace najdete v tématu [postupy: určení vlastnosti doby doběhu kroku pro vzor zatížení kroku](../test/how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern.md).

### <a name="goal-based"></a>Na základě cíle

 Vzor na základě cílem zatížení vypadá takto: krok vzor ale upraví zatížení uživatele na základě prahových hodnot čítače výkonu a úpravy zatížení pravidelné uživatele. Cílem na základě zatížení jsou užitečné pro celou řadu různých účely:

-   Tím se maximalizuje výstup z agentů: měření klíč omezení metriky na agenta a maximalizovat tak výstup agenty. Obvykle je procesoru; Však mohou být také paměti.

-   Dosažení některé cílové úrovni prostředků, obvykle procesoru, na cílovém serveru, pak měření propustnosti na této úrovni. Můžete provést porovnání spustit spustit propustnosti zadané konzistentní úroveň využití prostředků na serveru.

-   Dosáhl cílové úrovně propustnosti na serveru.

 V následující tabulce ukazuje příklad vzor na základě cílem s následujícím nastavením vlastností:

|Skupina vlastností|Vlastnost|Hodnota|
|--------------------|--------------|-----------|
|Čítače výkonu|Kategorie|Procesor|
|Čítače výkonu|Počítače|ContosoServer1|
|Čítače výkonu|Čítač|% Času procesoru|
|Čítače výkonu|instance|_Celkem|
|Cílový rozsah pro čítače výkonu|Vysoká End|90|
|Cílový rozsah pro čítače výkonu|Nízkou End|70|
|Omezení počtu uživatelů|Počáteční počet uživatelů|1|
|Omezení počtu uživatelů|Maximální počet uživatelů|100|
|Omezení počtu uživatelů|Maximální počet uživatelů snížení|5|
|Omezení počtu uživatelů|Maximální počet uživatelů přírůstku|5|
|Omezení počtu uživatelů|Minimální počet uživatelů|1|

 Způsobit, že tato nastavení **načíst testování analyzátor** upravit zatížení uživatele od 1 do 100 během testu spustit tak, který **čítač** pro `% Processor Time` z umístění ukazatele WebServer01 mezi `70%`a `90%.`

 Velikost jednotlivých úpravu zatížení uživatele je dáno **maximální počet uživatelů přírůstek** a **maximální počet uživatelů snížení** nastavení. Omezení počtu uživatelů se nastavují **maximální počet uživatelů** a **minimální počet uživatelů** vlastnosti.

#### <a name="goal-based-load-pattern-considerations"></a>Aspekty vzor zatížení založený na cíli

 Vzor zatížení na základě cílem je užitečné, když chcete určit počet uživatelů, které mohou podporovat váš systém předtím, než dorazí do určité úrovně využití prostředků. Tato možnost funguje nejlíp, když jste našli limitující prostředků (kritický bod) již v systému.

 Předpokládejme například, že víte, že omezení prostředků ve vašem systému je využití procesoru na serveru databáze a chcete zobrazit, kolik uživatelů můžete podporované, když využití procesoru na serveru databáze je přibližně 75 procent zaneprázdněný. Můžete použít vzor na základě cílem zatížení, s cílem zachovat hodnota výkonu čítač "% času procesoru" mezi 70 až 80 procent.

 Jednou z věcí sledujte je, pokud jiný prostředek je omezení propustnosti systému. Tyto prostředky může způsobit cíl, který je zadán vzor na základě cílem zatížení nikdy nelze připojit. Kromě toho bude pokračovat zatížení uživatele roste, dokud hodnota, která je určená pro **maximální počet uživatelů** je dosaženo. Je to obvykle není požadovaná zatížení, tak buďte opatrní o výběr čítače výkonu ve vzoru zatížení založený na cíli.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Určení vzor počáteční zatížení pro zátěžový test:** Pokud vytvoříte zátěžový test pomocí nové načíst testování průvodce, můžete vybrat vzor zatížení.|-   [Změna vzor zatížení](../test/edit-load-patterns-to-model-virtual-user-activities.md#EditingLoadPatternsChanging)|
|**Úpravy vzor zatížení pro zátěžový test:** poté, co vytvoříte zátěžový test, můžete upravit vzor zatížení v editoru načíst otestovat.|-   [Postupy: určení vlastnosti doby doběhu kroku pro vzor zatížení kroku](../test/how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern.md)|
|**Určení, zda scénář otestovat virtuálních uživatelů v zatížení by měla obsahovat data ve webové mezipaměti:** můžete změnit **procento nových uživatelů** vlastnost, která má vliv na způsob, ve kterém simuluje zátěžový test webu ukládání do mezipaměti, který by provést pomocí webového prohlížeče pro virtuálních uživatelů.|-   [Postupy: Zadejte procento virtuálních uživatelů, které používají Data ve webové mezipaměti](../test/how-to-specify-the-percentage-of-virtual-users-that-use-web-cache-data.md)|
|**Určení doby doběhu kroku pro vzor zatížení kroku:** **čas doběhu kroku** vlastnost umožňuje zvýšení z jednoho kroku na další (například ze 100 až 200 uživatelů) dojde k postupně místo okamžitě.|-   [Postupy: určení vlastnosti doby doběhu kroku pro vzor zatížení kroku](../test/how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern.md)|

## <a name="changing-the-load-pattern"></a>Změna vzor zatížení

 Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností vzor zatížení související se scénářem úrovní, které splňují vaše cíle test.

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [načíst vlastnosti scénář otestovat](../test/load-test-scenario-properties.md).


 Vzor zatížení určuje počet virtuálních uživatelů během zátěžového testu a rychlost, jakou se přidají nové uživatele aktivní. Můžete zvolit ze tří vzorů k dispozici: krok vzor, konstanta a na základě cíle. Další informace najdete v tématu [určující počet virtuálních uživatelů s vzorů zatížení ve scénáři zátěžového testu](../test/edit-load-patterns-to-model-virtual-user-activities.md).

> [!NOTE]
> Můžete také změnit vlastnosti vaše zatížení programově pomocí modulu plug-in zátěžový test. Další informace najdete v tématu [postupy: vytvoření modulu Plugin pro Test zatížení](../test/how-to-create-a-load-test-plug-in.md).


### <a name="to-change-the-load-pattern"></a>Chcete-li změnit vzor zatížení

1.  Otevřete zátěžový test.

2.  V **načíst Editor testu**, ve složce scénáře, rozbalte v situaci, kterou chcete upravit vzor zatížení pro a zvolte vzor zatížení pro tento scénář.

    > [!NOTE]
    > Pomocí jiné volby slov uzlu vzor zatížení, jak je uvedeno v stromu scénář zátěžový test, odráží zatížení profilu, který jste si zvolili při vytváření zatížení otestovat. Může být buď **konstantní profil zatížení** nebo **profil zatížení kroku**.

3.  Stiskněte klávesu **F4** pro zobrazení okna Vlastnosti.

     **Vzor zatížení** a **parametry** kategorie se zobrazí v okně Vlastnosti.

4.  (Volitelné) Změna **vzor** vlastnost **vzor zatížení** kategorie.

     Voleb **vzor** jsou **krok**, **konstantní**, a **na základě cílem**. Další informace o typech vzor zatížení najdete v tématu [určující počet virtuálních uživatelů s načíst vzory ve scénáři testu zatížení](../test/edit-load-patterns-to-model-virtual-user-activities.md).

5.  (Volitelné) V **parametry** kategorie, změňte hodnoty.

    > [!NOTE]
    > Hodnoty můžete nastavit pro **parametry** lišit podle hodnoty, která byla vybrána pro **vzor** vlastnost.

6.  Po dokončení změn vlastností zvolte **Uložit** na **souboru** nabídky. Když pak spustíte zátěžový test pomocí nové vzor zatížení.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Postupy: Zadejte procento virtuálních uživatelů, které používají Data ve webové mezipaměti](../test/how-to-specify-the-percentage-of-virtual-users-that-use-web-cache-data.md)
- [Postupy: určení vlastnosti doby doběhu kroku pro vzor zatížení kroku](../test/how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern.md)