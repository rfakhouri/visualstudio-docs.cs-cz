---
title: Zahrnout záznam obrazovky a zvuku během testování pomocí nastavení testů v sadě Visual Studio | Microsoft Docs
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, recording desktop video
ms.assetid: 2cefe8c2-430a-4cb4-bbe0-f3edb2e5bc03
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 3888f9c07c02fa640c451f84f58243369ce1fda6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-include-recordings-of-the-screen-and-voice-during-tests-using-test-settings"></a>Postupy: Nastavení testů pro záznam obrazovky a zvuku během testování

V editoru konfigurace v sadě Visual Studio můžete nakonfigurovat adaptér diagnostických dat, který zaznamenává obrazovky a zvuku uživatele, který je spuštěn test. Tento adaptér diagnostických dat uloží obrazovky a zvuku záznam plochy relace během testu. Po uložení záznamu výsledků testů nebo ho můžete připojit k. Ostatní členové týmu lze izolovat aplikace závad, které je obtížné reprodukujte záznamu.

> [!WARNING]
> Záznamy obrazovky a zvuku nepodporují víc konfigurací monitorování.

Záznam obrazovky a zvuku lze použít s ruční nebo automatické testů. Například pokud vzdáleně spuštění programového testu uživatelského rozhraní můžete chtít záznam plochy zobrazíte programového testu uživatelského rozhraní při jeho spuštění. Další informace o zachycení obrazovky a hlasového záznamu vzdáleně najdete v tématu [postupy: nastavení se vaše testovací Agent spustit testy, které komunikovat s plochou](../test/how-to-set-up-your-test-agent-to-run-tests-that-interact-with-the-desktop.md).

## <a name="to-configure-screen-and-voice-recording-for-your-test-settings"></a>Ke konfiguraci obrazovky a hlasového záznamu pro nastavení testu

1.  Otevřete nastavení testů, které chcete nakonfigurovat pro záznam obrazovky a zvuku. Další informace najdete v tématu [shromažďování diagnostických dat při testování (VSTS)](/vsts/manual-test/collect-diagnostic-data) nebo [shromažďovat diagnostické informace využitím testovacích nastavení](../test/collect-diagnostic-information-using-test-settings.md).

2.  V nastavení testu, vyberte **Role** sloužící k záznam obrazovky a zvuku.

    > [!NOTE]
    > Pro ruční testy a automatizovaných testů bude na počítač, který spouští testy.

3.  Vyberte **obrazovky a záznam hlasu** a potom zvolte **konfigurace**.

     Adaptéru konfigurace diagnostických dat – zobrazí se dialogové okno obrazovky a záznam hlasu.

     ![Konfigurace zobrazení](../test/media/testsettingvideoconfiggdr.png "TestSettingVideoConfigGDR")

4.  (Volitelné) Vyberte **povolit záznam hlasu** k zaznamenání zvukového obsahu ve vaší záznam.

5.  (Volitelné) Zaškrtněte políčko vedle **uložit záznam v případě úspěšného testovacího případu** k určení ukládání záznamy obrazovky a zvuku pro obě se nezdařilo a předán testy.

    > [!WARNING]
    > Pokud vyberete **uložit záznam v případě úspěšného testovacího případu**, záznamu je uložen s výsledky testů, který používá prostor úložiště na serveru. Nástroj Test přílohy čisticí můžete vyčistit tyto přílohy.

6.  V části **kvality záznamu obrazovky**, nakonfigurujte následující možnosti rozevíracího seznamu:

    1.  **Obnovovací frekvence:** zadejte, kolik snímků za sekundu, které chcete použít v obrazovky a záznam hlasu. Výchozí hodnota je 4 snímků za sekundu. Můžete třeba zadat hodnoty mezi 2 a 20.

    2.  **Přenosová rychlost:** zadejte, kolik kilobajtů za sekundu pro použití v obrazovky a záznam hlasu. Výchozí hodnota je 512. Můžete třeba zadat hodnoty 512 až 10 000.

    3.  **Quality(1-100):** můžete zadat kvalitu obrazovky a hlasového záznamu výběrem rozsahu od 1 do 100. Výchozí hodnota je 50 (střední).

7.  Zvolte **OK**. Nastavení kolekce diagnostické trasování jsou nyní nakonfigurována a uložit pro testovací nastavení.

    > [!TIP]
    > Chcete-li obnovit konfiguraci pro tento adaptér diagnostických dat, zvolte **resetovat na výchozí konfiguraci** pro sadu Visual Studio a **obnovit výchozí** nástroje Microsoft Test Manager.

## <a name="see-also"></a>Viz také

- [Shromažďování diagnostických dat při testování (VSTS)](/vsts/manual-test/collect-diagnostic-data)
- [Shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)
- [Spouštění manuálních testů (VSTS)](/vsts/manual-test/getting-started/run-manual-tests)