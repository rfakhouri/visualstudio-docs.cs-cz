---
title: "Vytvoření adaptéru diagnostických dat pro testování v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Diagnostic Data Adapter [Visual Studio ALM]
- Diagnostic Data Adapter
ms.assetid: b0b53fae-7007-4ad9-a604-21685937622f
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 91f340fee26b908ea90ad540e9c9fb2fdb1acf81
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine"></a>Vytvoření adaptéru diagnostických dat pro shromáždění vlastních dat nebo ovlivnění testovacího počítače

Může být vhodné vytvořit vlastní adaptér diagnostiky dat ke sběru dat při spuštění testu nebo v průběhu testu ovlivnit testovací počítač. Může být například užitečné shromáždit soubory protokolu, které jsou vytvářeny v testované aplikaci, a připojit je k výsledkům testu, nebo spustit testy, když máte málo zbývajícího místa na disku. Pomocí rozhraní API poskytované Visual Studio Enterprise, můžete napsat kód pro provádění úloh v určitých bodech v testu spustit. Lze například provádět úkoly při spuštění testovacího běhu, před spuštěním nebo po spuštění jednotlivých testů, a když se testovací běh dokončí.

Lze zadat výchozí vstup do vlastního adaptéru diagnostiky dat pomocí souboru konfiguračních nastavení. Lze například zadat informace o umístění souboru, který chcete shromáždit a připojit k výsledkům testu, nebo o tom, kolik by mělo na disku v systému zůstat místa. Tato data lze nakonfigurovat pro každé nastavení testu, které vytvoříte. Je možné zobrazit a upravená pomocí editoru výchozí součástí nástroje Microsoft Test Manager nebo můžete vytvořit vlastní uživatelský ovládací prvek použít jako editor. Jakékoli změny provedené v konfiguraci adaptéru v editoru jsou uloženy s nastavením testu.

Pokud používáte testů ze sady Visual Studio, je nutné nastavit tyto otestovat nastavení jako aktivní. Další informace o nastavení testu najdete v tématu [shromažďování diagnostických informací pomocí Test nastavení](../test/collect-diagnostic-information-using-test-settings.md).

## <a name="tasks"></a>Úlohy

 Následující témata vám pomohou s vytvořením Adaptérů diagnostiky dat:

|Úlohy|Související témata|
|-----------|-----------------------|
|**Vytvoření adaptéru diagnostických dat:** vytvoření adaptéru diagnostických dat pomocí vytvoření knihovny tříd a potom pomocí adaptéru diagnostických dat rozhraní API shromažďovat informace, které chcete nebo mít vliv na testovací systém, který používáte ke spuštění testů.|-   [Postupy: vytvoření adaptéru diagnostických dat](../test/how-to-create-a-diagnostic-data-adapter.md)|
|**Instalace adaptéru diagnostických dat vlastní:** můžete nainstalovat adaptér diagnostických dat nebo adaptér poskytované někdo jiný, zkopírováním ve správném adresáři.|-   [Postupy: instalace vlastního adaptéru diagnostických dat](../test/how-to-install-a-custom-diagnostic-data-adapter.md)|
|**Výběr vlastního adaptéru diagnostických dat pro použití při testy se spouštějí:** adaptéru diagnostických dat, který chcete použít pro nastavení testovací můžete vybrat tak, aby byl adaptér použit při spuštění testů.|-   [Shromažďování diagnostických dat při testování (VSTS)](/vsts/manual-test/collect-diagnostic-data)<br />-   [Shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)|
|**Konfigurace, jaké adaptéru diagnostických dat:** můžete nakonfigurovat nastavení, které řídí akce adaptér diagnostických dat v této konkrétní test nastavení.|-   [Postupy: vytvoření vlastního editoru dat pro adaptér diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)|

## <a name="see-also"></a>Viz také

- [Ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)