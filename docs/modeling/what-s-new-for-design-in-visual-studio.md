---
title: Co&#39;s nový návrh v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4e476e7f5107fb6ecfaced44342179d3365aec98
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="what39s-new-for-design-in-visual-studio"></a>Co&#39;s nový návrh v sadě Visual Studio

## <a name="live-dependency-validation"></a>Ověření za provozu závislostí

Odebrání nežádoucí závislostí, je důležitou součástí správy vaše technické pohledávky.
Za provozu ověření závislostí je nyní zahrnuty, poskytuje přesné informace o problémech a využívání plně z nových funkcí v seznamu chyb a editoru.

![Ověření za provozu závislostí v akci](media/dep-validation-whatsnew-01.png)

Chcete-li ověření závislostí zjistitelná a přístupnější, změna terminologie z "Diagram vrstev" do "Závislosti diagramu" došlo ke změně prostředí pro vytváření.

**Architektura** nabídky teď obsahuje příkaz, který přímo vytvořit diagram závislost:

![Za provozu závislost položky v nabídce architektura](media/dep-validation-whatsnew-02.png)

... a názvy vlastností, které vrstvy v diagramu závislostí a jejich popisy se změnily tak, aby byly smysluplnější:

![Názvy vlastností za provozu závislostí aktualizovat](media/dep-validation-whatsnew-03.png)

Nyní uvidíte dopad změny okamžitě ve výsledcích analýzy pro aktuální kód v řešení pokaždé, když uložíte diagramu. Nemusíte už čekat na dokončení příkazu "Závislosti ověření".

Další podrobnosti najdete v tématu [tomto příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/07/live-architecture-dependency-validation-in-visual-studio-15-preview-5/). 
 
## <a name="uml-designers-have-been-removed"></a>Odebrali jsme Designer UML

Návrháři UML byly odebrány z této verze sady Visual Studio Enterprise.

* Diagramy UML se nyní zobrazí jako soubory XML
* Průzkumník modelu UML již neexistuje.
* Modelování projektu, který odkazuje se již nepoužívají pro ověření závislostí
* V Průzkumníku řešení uzlu "Vrstvu odkazů" se už nezobrazuje.
* Akce sestavení "Ověřit" v diagramu závislosti (vrstvy) se už používá – sestavovací úlohy byla odebrána. 
* Struktura projektu bude zachována pro účely odezvy mezi verzemi
* Můžete stále otevřete, vytvořit, upravit a Uložit diagram závislostí (Layer) ve formátu XML
* Pracovní položky sady TFS propojit s diagram závislostí (Layer) nejsou dostupné na návrhovou plochu
* Zpětné odkazy z DSL nebo vrstva se už nepodporuje. 
* Rozšíření UML v sadě SDK modelování již není podporována.

Však podpora vizualizace architektuře .NET a C++ kód je k dispozici prostřednictvím [code mapy](map-dependencies-across-your-solutions.md)a mezi významná vylepšení k ověření závislostí popsané výše.

Pokud jste významné uživatel UML návrhářů, můžete dál používat Visual Studio 2015 nebo dřívějších verzí rozhodnete alternativní nástroj pro vaše potřeby UML.

Další podrobnosti najdete v tématu [tomto příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/14/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/). 

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

<a name="VersionSupport"></a>
##  <a name="version-support-for-architecture-and-modeling-tools"></a>Podpora verzí pro architektura a modelování nástroje  

Visual Studio je k dispozici v několika verzích. Ne všechny z nich poskytovat podporu pro architektura a modelování nástroje. Následující tabulka uvádí dostupnost jednotlivých nástrojů.  
  
|**Funkce**|**Enterprise**|**Professional**|**Community**|**Express**|  
|-----------------|--------------------|----------------------|-------------------|-----------------|  
|**Mapy kódu**|Ano|Další informace v poznámce (1)|-|-|  
|**Diagramy závislostí**|Ano|Další informace v poznámce (2)|Další informace v poznámce (2)|-|  
|**Přesměruje grafy** (diagramy DGML)|Ano|Ano|Ano|-|  
|**Klonování kódu**|Ano|-|-|-|  
  
Poznámka: (1): Podporuje pouze čtení map kódu, filtrování map kódu, přidávání nových obecné uzlů a vytvoření nového směrované graf z výběru.

(2). Poznámka: Podporuje pouze čtení diagramy závislostí.
