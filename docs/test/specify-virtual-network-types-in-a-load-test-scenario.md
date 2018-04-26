---
title: Určení typů virtuálních sítí ve scénáři zátěžového testu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, adding networks
- load tests, removing networks
- load tests, virtual networks
- network mix
ms.assetid: 3c4f7874-081a-4ec4-9510-4d6d7d863a11
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: a3c4a4e6db97e99d2ec2df5b27c6fd8293a182f5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="specify-virtual-network-types-in-a-load-test-scenario"></a>Určení typů virtuálních sítí ve scénáři zátěžového testu

*Sítě kombinace* poskytuje způsob k simulaci zatížení více reálně ve scénáři zátěžového testu. Zatížení je generována pomocí heterogenní kombinaci různých typů sítě místo jeden typ jedné sítě. Můžete vytvořit blíže aproximace o tom, jak koncoví uživatelé komunikovat s vašimi aplikacemi.

 Kombinace sítí určuje pravděpodobnost virtuální uživatel, který se spouští danou *síťový profil*. Profil sítě je simulace šířky pásma sítě na aplikační vrstvu. Není ho simulovat latence.

 Když vytvoříte zátěžový test, můžete chtít simulaci, který má být vygenerován zatížení prostřednictvím více než jeden typ síťového připojení. Kombinace sítí nabízí několik typů sítě. Různé sítě jsou simulated. Pokud vyberete možnost, jako `Cable-DSL 1.5Mbps`, dobu čekání jsou vloženy do testovací k simulaci vybrané šířky pásma.

 Kombinace sítí funguje jako další možnosti kombinaci. Typ sítě je vybrané náhodně související s virtuálním uživatelem, založené na kombinaci sítě. Tento uživatel testy se spouštějí pomocí určitý typ sítě, podle pravděpodobnost, které jste zadali v kombinaci.

 Po určení kombinace sítí, můžete přidávat a odebírat typy sítí. Můžete také změnit rozdělení kombinace sítí pomocí ovládacího prvku kombinaci.

 Ovládací prvek kombinace umožňuje snadno upravit distribuční sítí ve scénáři.

 Další informace najdete v tématu [o kombinaci řídicí](../test/specify-virtual-network-types-in-a-load-test-scenario.md).

## <a name="true-network-emulation"></a>Skutečné emulace sítě s

 Visual Studio použije softwarový skutečné emulace sítě s pro všechny typy testu včetně zátěžové testy. Skutečné emulace sítě s simuluje síťové podmínky přímé manipulace s síťových paketů. Emulátor true sítě můžete emulují chování drátové a bezdrátové sítě pomocí spolehlivé fyzického propojení, jako je například na Ethernetu. Následující atributy sítě jsou součástí skutečné emulace sítě s:

-   Operace round-trip čas přes síť (latence)

-   Množství dostupné šířky pásma

-   Chování služby Řízení front

-   Ztráta paketů

-   Změna pořadí paketů

-   Chyba šíření.

Skutečné emulace sítě s taky poskytuje flexibilitu při filtrování síťových paketů na základě IP adresy nebo protokoly, například TCP, UDP a protokolu ICMP.

Skutečné emulace sítě s lze vývojáři aplikací založených na síti a testerům, sada emulovat požadované testovacím prostředí, vyhodnocení výkonu, předpovědi dopad změny nebo rozhodnutí o technologii optimalizace. V porovnání s výskytu test hardwaru, skutečné emulace sítě s je výrazně levnější a flexibilnější řešení.

## <a name="to-add-new-networks-to-a-scenario"></a>Chcete-li přidat nové sítě pro určitý scénář

1.  Během procesu určení kombinace sítí scénáři, zvolte **přidat**.

     Nový záznam sítě se přidá k mřížce.

    > [!NOTE]
    > K zobrazení **upravit kombinace sítí** dialogové okno pole, klikněte pravým tlačítkem na existující scénář a pak zvolte **upravit kombinace sítí**.

2.  V **typ sítě** sloupce, vyberte šipku nové položky. Vyberte typ požadované sítě.

3.  (Volitelné) Upravte ovládacího prvku kombinace určení distribučních testu. Další informace najdete v tématu [o kombinaci řídicí](../test/specify-virtual-network-types-in-a-load-test-scenario.md).

4.  Až dokončíte přidávání sítí, vyberte **OK**.

## <a name="to-remove-networks-from-a-scenario"></a>Odebrání sítě scénáři

1.  Otevřete zátěžový test.

2.  Klikněte pravým tlačítkem na scénář, ze kterého chcete odebrat síť a vyberte **upravit kombinace sítí**. **Upravit kombinace sítí** se zobrazí dialogové okno.

3.  V mřížce vyberte síť a potom vyberte **odebrat**.

4.  (Volitelné) Upravte ovládacího prvku kombinace určení distribučních testu. Další informace najdete v tématu [o kombinaci řídicí](../test/specify-virtual-network-types-in-a-load-test-scenario.md).

5.  Po dokončení odebírání sítí, zvolte **OK**.

## <a name="about-the-mix-control"></a>O ovládacím prvku kombinaci

 Ovládací prvek kombinace umožňuje nastavit procento zatížení, která se distribuuje mezi testy, typu prohlížeče nebo typy sítí ve scénáři zátěžového testu. Nastavte procentní hodnoty posunutím jezdce. Úprava kombinace pro typy sítí určuje pravděpodobnost s určitým síťovým profil ve scénáři zátěžového testu virtuálním uživatelem.

 Při přesunutí jezdce procento hodnoty dostupné všechny položky změnit. Pokud máte více než dvě položky, velikost, můžete přidat nebo odebrat je rovnoměrně rozdělené mezi další položky. Je možné toto chování potlačit. Pokud vyberete políčko ve sloupci zámek pro konkrétní položky, zamknete tak zadaný procentuální hodnotu pro tuto položku. Pak, když přesouváte jezdce, velikost, můžete přidat nebo odebrat se použije pouze na všechny zbývající odemknout položky.

 **Distribuovat** tlačítko se používá k přidělení procentní hodnoty rovnoměrně mezi všechny položky. Například pokud máte tři položky, výběr **distribuovat** nastaví procentní hodnoty 34, 33 a 33.

> [!WARNING]
> **Distribuovat** tlačítko přepíše všechny položky, které jsou zamčené.

 Je také možné zadejte procentní hodnoty přímo do **%** sloupec místo pomocí posuvníků. Pokud zadáte hodnotu v procentech přímo, nebude automaticky upravte ostatní položky.

> [!NOTE]
> Posuvníků jsou zakázané, když celkové nepřidá až o 100 %, nebo při procentní hodnoty do **%** sloupce jsou desetinných míst.

Když ručně zadáte procentní hodnoty, měli byste si ověřit, že součet všech položek je 100 %. Při ukládání kombinaci, pokud součet není 100 %, vyzve tak, aby přijímal procentuální hodnoty, jako jsou, nebo se vrátit a jejich nastavení. Pokud zvolíte možnost je přijmout, protože se jedná o, bude poměrně rozložen na 100 %.  Například pokud máte dvě položky a je ručně nastavte na 80 % a 40 %, první položka bude nastavena pro 66.67 % (80 dělený 120) a druhá položka bude nastavena pro 33,33 % (40 dělený 120).