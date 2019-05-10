---
title: Novinky pro programátory v sadě Visual Studio 2017
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- what's new [Visual Studio], architecture and modeling
- architecture [Visual Studio], modeling
- modeling software [Visual Studio], What's New
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
monikerRange: vs-2017
ms.openlocfilehash: dc75c7414e0fff18f76d14f8f9a4e0779a9e7a2b
ms.sourcegitcommit: 6a19c5ece38a70731496a38f2ef20676ff18f8a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65476540"
---
# <a name="whats-new-for-design-in-visual-studio-2017"></a>Novinky pro programátory v sadě Visual Studio 2017

## <a name="live-dependency-validation"></a>Ověřování závislostí v reálném čase

Odebrání nechtěné závislosti je důležitou součástí správy technický dluh. Visual Studio poskytuje živé ověření závislosti, včetně přesné informace o problémech, jako je například, kde právě jsou. Závislostí v reálném čase ověření trvá úplné výhody nových funkcí v editoru a seznamu chyb.

![Ověřování závislostí v reálném čase v akci](media/dep-validation-whatsnew-01.png)

Prostředí pro vytváření změnil provádět ověřování závislostí zjistitelnější a dostupnější. Terminologie byl změněn z "Diagram vrstev" na "Diagram závislostí".

**Architektura** nabídky teď obsahuje příkaz, který přímo vytvořit diagram závislostí:

![Položka závislostí v reálném čase na nabídku architektura](media/dep-validation-whatsnew-02.png)

Popisy a názvy vlastností vrstvy se změnily tak, aby byly lépe vystihuje:

![Aktualizovat názvy vlastností závislostí v reálném čase](media/dep-validation-whatsnew-03.png)

Okamžitě uvidíte dopad změny ve výsledcích analýzy zadání stávajícího kódu v řešení pokaždé, když uložíte diagram. Nemusíte čekat na dokončení **ověření závislostí** příkazu.

Další podrobnosti najdete v tématu [tento příspěvek na blogu](https://devblogs.microsoft.com/devops/live-architecture-dependency-validation-in-visual-studio-15-preview-5/).

## <a name="uml-designers-have-been-removed"></a>Byly odebrány návrhářů UML

Byly odebrány návrhářů UML v sadě Visual Studio.

* Diagramy UML se nyní zobrazují jako soubory XML
* V Průzkumníku modelu UML již existuje.
* Modelování projektu, které odkazy se už nebude používat pro ověřování závislostí
* "Odkazy vrstvy" uzlu v Průzkumníkovi řešení se už nebude zobrazovat.
* Akce sestavení "Ověřit" na diagram závislostí (vrstvy) se už používá – úloha sestavení byla odebrána.
* Struktura projektu je zachován z důvodu verzemi mezi verzemi
* Můžete stále otevřít, vytvořit, upravit a uložení diagram závislostí (Layer) ve formátu XML
* Pracovní položky sady TFS propojené s diagram závislostí (vrstvy) nejsou dostupné na návrhové ploše
* Propojení zpět z DSL nebo vrstvě se už nepodporuje.
* Rozšíření UML v sadě SDK modelování se už nepodporuje.

Podpora pro vizualizaci architektury .NET a C++ kód je k dispozici prostřednictvím [map kódu](map-dependencies-across-your-solutions.md).

Pokud jste uživatelem významné návrhářů UML, můžete nadále při rozhodování o alternativní nástroj pro vaše potřeby UML, použijte Visual Studio 2015 nebo starší verze.

Další podrobnosti najdete v tématu [tento příspěvek na blogu](https://devblogs.microsoft.com/devops/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/).

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="a-nameversionsupport-edition-support-for-architecture-and-modeling-tools"></a><a name="VersionSupport" />Podpora edice nástroje architektury a modelování

Visual Studio je k dispozici v několika edicích. Ne všechny tyto poskytovat podporu pro architektury a nástroje modelování. V následující tabulce jsou uvedeny dostupnost jednotlivých nástrojích.

|**Funkce**|**Enterprise edition**|**Edice Professional**|**Edice Community**|
|-|-|-|-|
|**Mapy kódu**|Ano|Pouze filtrování kód mapuje podporuje čtení map kódu, přidává nové obecné uzly a vytvoření nového orientovaného grafu z výběru.|-|
|**Diagramy závislostí**|Ano|Podporuje čtení diagramů závislostí.|Podporuje čtení diagramů závislostí.|
|**Řízených grafů** (diagramy DGML)|Ano|Ano|Ano|
|**Klonování kódu**|Ano|-|-|