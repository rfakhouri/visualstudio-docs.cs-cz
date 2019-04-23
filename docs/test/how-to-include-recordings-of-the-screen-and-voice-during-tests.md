---
title: Záznam obrazovky a hlasu během testů
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, recording desktop video
ms.assetid: 2cefe8c2-430a-4cb4-bbe0-f3edb2e5bc03
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 663f89c65604c42b356830b3a0c6d61bdcb265e3
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085737"
---
# <a name="how-to-include-recordings-of-the-screen-and-voice-during-tests-using-test-settings"></a>Postupy: Zahrnout nahrávání obrazovky a hlasu během testů pomocí nastavení testu

Z editoru konfigurace v sadě Visual Studio můžete nakonfigurovat adaptér diagnostických dat, který zaznamenává obrazovku a hlas uživatele, který spustil test. Tento adaptér diagnostických dat uloží obrazovku a hlasovou nahrávku relace plochy během testu. Záznam je uložen s výsledkem zkoušky nebo může být připojen k chybě. Ostatní členové týmu mohou používat tento záznam k izolování problémů aplikací, které je obtížné reprodukovat.

> [!WARNING]
> Obrazovky a hlasové nahrávky nepodporují více konfigurací monitoru.

Obrazovku a hlasový záznamník lze použít s ruční nebo automatické testy. Například pokud vzdáleně spustíte programový test uživatelského rozhraní můžete zaznamenat plochu za účelem zobrazení programového testu UI za běhu. Další informace o tom, jak zachytit obrazovku a hlasový záznam vzdáleně, naleznete v tématu [jak: Nastavení testovacího agenta pro spouštění testů komunikujících s plochou](../test/how-to-set-up-your-test-agent-to-run-tests-that-interact-with-the-desktop.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-configure-screen-and-voice-recording-for-your-test-settings"></a>Konfigurace obrazovky a hlasového záznamu pro nastavení testu

1. Otevřete nastavení testu, které chcete konfigurovat pro nahrávání obrazovky a hlasu. Další informace najdete v tématu [shromažďování diagnostických dat při testování (testovací plány Azure)](/azure/devops/test/collect-diagnostic-data?view=vsts) nebo [shromažďování diagnostických informací pomocí nastavení testu](../test/collect-diagnostic-information-using-test-settings.md).

2. V nastavení testu, vyberte **Role** chcete použít pro záznam obrazovky a hlasu.

    > [!NOTE]
    > Pro ruční a automatizované testy by toto byl počítač, který spouští testy.

3. Vyberte **záznam obrazovky a hlasu** a klikněte na tlačítko **konfigurovat**.

     **Konfigurace adaptéru diagnostiky dat – záznam obrazovky a hlasu** se zobrazí dialogové okno.

     ![Konfigurace zobrazení](../test/media/testsettingvideoconfiggdr.png)

4. (Volitelné) Vyberte **povolit záznam hlasu** k zachycení zvukového obsahu v záznamu.

5. (Volitelné) Zaškrtněte políčko vedle položky **uložit záznam, pokud testovací případ proběhne úspěšně** k určení ukládání záznamu obrazovky a hlasu pro obě neúspěšných a úspěšných testech.

    > [!WARNING]
    > Pokud vyberete **uložit záznam, pokud testovací případ proběhne úspěšně**, záznam je uložen s výsledky testů, které využívají úložný prostor na serveru. Můžete použít **Test Attachment Cleaner** nástroj k vyčištění těchto příloh.

6. V části **kvalita nahrávání obrazovky**, nakonfigurujte následující možnosti rozevíracího seznamu:

    1. **Snímková frekvence:** Zadejte, kolik snímků za sekundu, které chcete použít při záznamu hlasu a obrazovky. Výchozí hodnota je 4 snímky za sekundu. Je možné zadat hodnoty v rozmezí 2 až 20.

    2. **Přenosová rychlost:** Určete, kolik kilobajtů za sekundu chcete použít při záznamu hlasu a obrazovky. Výchozí hodnota je 512. Je možné zadat hodnoty v rozmezí 512 až 10 000.

    3. **Kvalita(1-100):** Můžete určit kvalitu obrazovky a hlasu výběrem rozsahu mezi 1 a 100. Výchozí hodnota je 50 (střední).

7. Zvolte **OK**. Nastavení shromažďování diagnostického trasování jsou nyní nakonfigurováno a uloženo pro nastavení testu.

    > [!TIP]
    > Chcete-li obnovit konfiguraci adaptéru diagnostických dat, zvolte **obnovit výchozí konfiguraci** pro sadu Visual Studio a **obnovit výchozí** nástroje Microsoft Test Manager.

## <a name="see-also"></a>Viz také:

- [Shromažďování diagnostických dat při testování (Azure testovací plány)](/azure/devops/test/collect-diagnostic-data?view=vsts)
- [Shromažďování diagnostických dat v manuálních testů (Azure testovací plány)](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts)
- [Shromažďování diagnostických údajů pomocí nastavení testů](../test/collect-diagnostic-information-using-test-settings.md)
- [Spouštění ručních testů (Azure testovací plány)](/azure/devops/test/run-manual-tests?view=vsts)