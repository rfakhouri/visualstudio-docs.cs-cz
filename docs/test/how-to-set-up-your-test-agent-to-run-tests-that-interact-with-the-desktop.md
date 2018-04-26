---
title: Konfigurace agenta pro testovací sady Visual Studio pro spouštění testů komunikujících s plochou
ms.date: 10/20/2016
ms.topic: conceptual
helpviewer_keywords:
- agents, configuring for interaction with desktop
ms.assetid: 3a94dd07-6d17-402c-ae8f-7947143755c9
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: d1b6655dd493a2ac62ba333f3858b299ee398f8d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-up-your-test-agent-to-run-tests-that-interact-with-the-desktop"></a>Postupy: Nastavení agenta Test Agent pro spouštění testů komunikujících s plochou

Pokud budete chtít spuštění automatizovaných testů komunikujících s plochou, musíte nastavit agenta ke spuštění jako proces místo služby. Například pokud chcete spustit vzdáleně pomocí testovacího kontroléru a agenta test programového testu uživatelského rozhraní nebo chcete spustit test a zachycení záznamu při spuštění videa, je potřeba nastavit agenta a spustit jako proces. Pokud přiřadíte agenty role v nastavení testu pomocí sady Visual Studio nebo přiřadit agenty rolí ve vašem prostředí pomocí nástroje Microsoft Test Manager, musíte změnit sadu pro všechny agenty přiřadit do rolí, které musí komunikovat s plochou.

> [!WARNING]
> Pokud používáte Microsoft Test Manager k nastavení testovacího prostředí, nainstaluje agenta nástroje test. Zadávat lze v Průvodci vytvořením prostředí, kterou chcete konfigurovat jedné z rolí ke spuštění programových testů uživatelského rozhraní.

> [!IMPORTANT]
> Počítač, který je spuštěn agent na kterém chcete spustit programové testy uživatelského rozhraní nelze zamknout nebo mít aktivní spořič.

Pokud používáte programové testy uživatelského rozhraní, které spuštění prohlížeče, účet služby pro testovacího agenta se používá ke spuštění tohoto prohlížeče. Tento účet služby musí být stejný jako uživatelský účet, který je aktivního uživatele v tomto počítači. Pokud není stejným uživatelským účtem, v prohlížeči se nespustí.

> [!IMPORTANT]
> Pokud používáte programového testu uživatelského rozhraní, která spustí prohlížeč jako součást definice sestavení, účet služby pro službu sestavení se používá ke spuštění tohoto prohlížeče. Tento účet služby musí být stejný jako uživatelský účet, který je aktivního uživatele v tomto počítači. Pokud není stejným uživatelským účtem, v prohlížeči se nespustí.

 Použijte následující postup k nastavení všech agentů, které jsou přiřazeny k roli, která provede úlohu, která musí komunikovat s plochou.

## <a name="to-set-up-an-agent-to-run-as-a-process"></a>Chcete-li nastavit agenta pro spouštění jako proces

1.  Postup konfigurace testovacího agenta instalaci spustit jako proces, přejděte na **spustit**, **všechny programy**, **Microsoft Visual Studio**, **Microsoft Visual Studio Testovací nástroje Konfigurace agenta**.

     **Konfigurace agenta Test** se zobrazí dialogové okno.

2.  Pokud chcete zobrazit stránku a vyberte spustit jako proces, zvolte **spustit možnosti**.

     Zobrazí se stránka, která vám umožní vybrat ke spuštění agenta jako procesu nebo služby.

3.  Vyberte **interaktivní proces**. Testovací agent spustí jako proces místo služby. Zvolte **Další**.

     Teď můžete zadat podrobnosti o uživateli umožňuje využít při spuštění agenta test jako proces a další možnosti.

    > [!NOTE]
    > Uživatel, který přidáte ke spuštění procesu je nutné přidat také jako člen skupiny TeamTestAgentService na počítači pro testovací kontroler pro tohoto agenta. Pokud při přidání tohoto uživatele k testovacím počítači kontroleru, je tento uživatel s aktuálním uživatelem, musíte odhlášení nebo tento počítač restartovat.

4.  Zadejte název v **uživatelské jméno**.

5.  Zadejte heslo do **heslo**.

     **Informace o účtu důležité uživatele:**

    -   Null hesla nejsou podporovány pro uživatelské účty.

    -   Pokud chcete použít nástroje IntelliTrace nebo data emulace sítě a adaptéru diagnostických, uživatelský účet musí být členem skupiny Administrators. Pokud je počítač, který je spuštěn test agent běží operační systém, který má nejmenší privilegovaný účet uživatele, musíte také spustit jako správce (se zvýšenými oprávněními). Pokud není agent uživatelské jméno ve službě agenta se pokusí přidat, který vyžaduje oprávnění k testovacímu kontroleru.

    -   Uživatel pokouší použít testovací kontroler, musí být v účtu uživatele testovací řadiče nebo nebudou moci spouštět testy řadičem.

6.  Abyste měli jistotu, že do počítače s agentem test agent lze spustit testy po restartování, můžete nastavit počítač pro automatické přihlášení jako uživatel agenta test. Vyberte **automatické přihlášení**. To bude ukládat uživatelské jméno a heslo v šifrovaném formátu v registru.

    > [!NOTE]
    > Když jsou připojeni k testovacím prostředí pomocí vzdálené plochy nebo připojení na základě hostů, může docházet často, neočekávané odpojí. Možnou příčinou dojít ke ztrátě připojení je, že je počítač nakonfigurovaný pro automatické přihlášení do sítě.

7.  Chcete-li mít jistotu, že šetřič obrazovky je zakázána, protože to může narušovat žádné automatizovaných testů, které musí komunikovat s plochou, vyberte **šetřič obrazovky zajistěte, aby je zakázána**.

    > [!WARNING]
    > Pokud automatické přihlášení nebo zakážete šetřič obrazovky jsou rizika zabezpečení. Povolením automatické protokolu v, povolíte jiných uživatelů k spuštění tohoto počítače a mohli používat účet, který automaticky přihlásí. Pokud zakážete šetřič obrazovky, počítač nemusí vyzván k přihlášení uživatele k odemknutí počítače. To umožňuje všem uživatelům přístup k počítači v případě, že mají fyzický přístup k počítači. Pokud povolíte tyto funkce na počítači, měli byste si ověřit, že tyto počítače jsou fyzicky zabezpečené. Tyto počítače jsou například umístěny ve fyzicky zabezpečeném testovacím prostředí. Pokud zrušíte výběr **šetřič obrazovky zajistěte, aby je zakázána**, nepovolí se vaše šetřič obrazovky.

     Chcete-li změnit agenta zpět ke spuštění jako služba, můžete použít tento nástroj a vyberte **služby**.

8.  Chcete-li změny použít, zvolte **použít nastavení**.

     A **souhrnné informace o konfiguraci** se zobrazí dialogové okno, které zobrazuje stav jednotlivých kroků konfigurace agenta test agent.

9. Zavřete **souhrnné informace o konfiguraci** dialogovém okně vyberte **zavřete**. Zvolte **zavřete** zavřete nástroj Test Agent konfigurace.

    > [!NOTE]
    > Není ikony v oznamovací oblasti spuštěnou na počítači pro agenta test, který je spuštěný jako proces. Zobrazuje stav agenta test. Můžete spustit, zastavit nebo restartovat agenta, pokud je spuštěn jako proces pomocí tohoto nástroje. Pokud není spuštěná, spusťte agenta test jako proces, zvolte **spustit**, **všechny programy**, **Microsoft Visual Studio**, **Microsoft Visual Studio Test Agent**.

     Pokud testovací kontroler pro tohoto agenta test je registrován s produktem Team Foundation Server, stav agenta test, který je spuštěný jako interaktivní proces se zobrazí v **řadiče** zobrazit v **testovacím Center**nástroje Microsoft Test Manager. Zobrazí se symbolem předchozí hvězdičky k označení, že je spuštěn jako interaktivní proces. Restartování tohoto testovacího agenta musíte použít nástroj, který běží na počítači agentem test agent a zda není **řadiče** zobrazení.

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)