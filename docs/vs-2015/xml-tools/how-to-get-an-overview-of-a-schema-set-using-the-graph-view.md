---
title: 'Postupy: získání přehledu o sadě schémat pomocí zobrazení grafu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0b7c3d1d9f351e496469e5b13552ec78e1548f5c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675883"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Postupy: získání přehledu o sadě schémat pomocí zobrazení grafu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: získání přehledu schéma nastavit pomocí zobrazení grafu](https://docs.microsoft.com/visualstudio/xml-tools/how-to-get-an-overview-of-a-schema-set-using-the-graph-view).  
  
  
Toto téma popisuje způsob použití [zobrazení grafu](../xml-tools/graph-view.md) zobrazíte souhrnný přehled uzly v sadě schémat a vztahy mezi uzly.  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Vytvořte nový soubor XSD a zobrazte kořenový element v zobrazení modelu obsahu  
  
1.  Vytvořte nový soubor schématu XML a uložte soubor jako Relationships.xsd.  
  
2.  Klikněte na tlačítko **pomocí editoru XML k zobrazení a úpravě základního souboru schématu XML** odkaz na zobrazení spuštění.  
  
3.  Zkopírujte ukázkový kód XML schéma z [ukázky XML schématu: relace](../xml-tools/sample-xsd-file-relationships.md) a vložte ji nahradit kód, který byl přidán do nového souboru XSD ve výchozím nastavení.  
  
4.  Klikněte pravým tlačítkem na libovolné místo v editoru XML a vyberte **Návrhář zobrazení**.  
  
5.  Zobrazení grafu vyberte na panelu nástrojů XSD.  
  
6.  Vyberte **schéma nastaveno** uzlu Průzkumníka schémat XML a přetáhněte uzel návrhu suface zobrazení grafu. Měli byste vidět všechny globální uzly a šipky spojující uzly, které mají relace.  
  
     ![Zobrazení grafu](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")  
  
7.  Klikněte na libovolný uzel na návrhové ploše a podívejte se na panelu s popisem cesty chcete zobrazit, kde se nachází na vybraný uzel v sadě schémat.  
  
8.  Rick kliknutím na libovolný uzel elementu na desing ploše a vyberte možnost **generovat ukázkové XML** zobrazíte instance dokumentu XML.



