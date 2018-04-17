---
title: Vytvoření adaptéru diagnostických dat pro testování v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter [Visual Studio ALM]
- Diagnostic Data Adapter
ms.assetid: b0b53fae-7007-4ad9-a604-21685937622f
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 0410fd52e115e2c2c257811e088c46a831d0082d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine"></a>Vytvoření adaptéru diagnostických dat pro shromáždění vlastních dat nebo ovlivnění testovacího počítače

Můžete chtít vytvořit vlastního adaptéru diagnostických dat pro shromáždění dat při spuštění testu, nebo můžete chtít ovlivnit testovací počítač jako součást svůj test. Například můžete chtít shromažďovat soubory protokolů, které jsou vytvořené pomocí aplikace testovaného a připojte je k si výsledky testu, nebo můžete chtít spustit testy, když je omezené místo na disku zbývající ve vašem počítači. Pomocí rozhraní API poskytované Visual Studio Enterprise, můžete napsat kód pro provádění úloh v určitých bodech v testu spustit. Například můžete provádět úlohy při spuštění spuštění testu, před a po každé jednotlivé testovací spuštění a po dokončení testu, spuštění.

Můžete zadat výchozí vstup do vašeho vlastního adaptéru diagnostických dat pomocí souboru nastavení konfigurace. Například můžete zadat informace o umístění souboru, které chcete shromažďovat a připojte k si výsledky testu nebo kolik diskových místa, které chcete být ponecháno v systému. Tato data lze nakonfigurovat pro každé nastavení testů, které vytvoříte. Je možné zobrazit a upravená pomocí editoru výchozí součástí nástroje Microsoft Test Manager nebo můžete vytvořit vlastní uživatelský ovládací prvek použít jako editor. Všechny změny provedené v konfiguraci adaptéru ve svém editoru ukládají s testovacími nastaveními.

Pokud používáte testů ze sady Visual Studio, je nutné nastavit tyto otestovat nastavení jako aktivní. Další informace o nastavení testu najdete v tématu [shromažďování diagnostických informací pomocí Test nastavení](../test/collect-diagnostic-information-using-test-settings.md).

## <a name="tasks"></a>Úlohy

 Použijte následující témata vám pomohou vytvořit adaptérů diagnostických dat:

|Úlohy|Související témata|
|-----------|-----------------------|
|**Vytvoření adaptéru diagnostických dat:** vytvoření adaptéru diagnostických dat pomocí vytvoření knihovny tříd a potom pomocí adaptéru diagnostických dat rozhraní API shromažďovat informace, které chcete nebo mít vliv na testovací systém, který používáte ke spuštění testů.|-   [Postupy: vytvoření adaptéru diagnostických dat](../test/how-to-create-a-diagnostic-data-adapter.md)|
|**Instalace adaptéru diagnostických dat vlastní:** můžete nainstalovat adaptér diagnostických dat nebo adaptér poskytované někdo jiný, zkopírováním ve správném adresáři.|-   [Postupy: instalace vlastního adaptéru diagnostických dat](../test/how-to-install-a-custom-diagnostic-data-adapter.md)|
|**Výběr vlastního adaptéru diagnostických dat pro použití při testy se spouštějí:** adaptéru diagnostických dat, který chcete použít pro nastavení testovací můžete vybrat tak, aby byl adaptér použit při spuštění testů.|-   [Shromažďování diagnostických dat při testování (VSTS)](/vsts/manual-test/collect-diagnostic-data)<br />-   [Shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)|
|**Konfigurace, jaké adaptéru diagnostických dat:** můžete nakonfigurovat nastavení, které řídí akce adaptér diagnostických dat v této konkrétní test nastavení.|-   [Postupy: vytvoření vlastního editoru dat pro adaptér diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)|

## <a name="see-also"></a>Viz také

- [Ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)