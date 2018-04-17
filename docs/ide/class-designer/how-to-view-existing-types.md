---
title: 'Postupy: zobrazení existujících typů (návrhář tříd) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.CannotShowBaseType
helpviewer_keywords:
- types [Visual Studio], visualizing
- types [Visual Studio], class diagrams
- class diagrams, types
ms.assetid: de110a4e-5b51-4a40-9dee-615df4d8f999
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a1d8ff3ee7f58e59081dc555160ce284ddea835
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-view-existing-types-class-designer"></a>Postupy: Zobrazení existujících typů (návrhář tříd)
Pokud chcete zobrazit stávající typ a její členy, přidejte do diagramu tříd jeho tvaru.  
  
Můžete vidět místní a odkazované typy. V aktuálně otevřeném projektu existuje místní typ a je pro čtení i zápis. Odkazovaný typ existuje v jiném projektu nebo v odkazovaném sestavení a je jen pro čtení.  
  
Postup návrhu nové typy v diagramech tříd, najdete v [postupy: vytváření typů pomocí návrháře tříd](how-to-create-types.md).  
  
### <a name="to-see-types-in-a-project-on-a-class-diagram"></a>Zobrazení typů v projektu v diagramu tříd  
  
1.  Z projektu v okně Průzkumník řešení otevřete existující soubor diagramu tříd (.cd). Nebo pokud neexistuje žádný diagram tříd, přidejte do projektu nový diagram tříd. V tématu [postupy: Přidání diagramů tříd do projektů](how-to-add-class-diagrams-to-projects.md).  
  
2.  Z okna Průzkumník řešení přetáhněte soubor zdrojového kódu do diagramu tříd.  
  
    > [!WARNING]
    >  Pokud má vaše řešení projekt, který sdílí kód mezi více aplikacemi, můžete přetáhnout soubory nebo kód na diagramu tříd pouze z těchto zdrojů:  
    >   
    >  -   Projekt aplikace, který obsahuje diagram  
    > -   Sdílený projekt, který byl importován pomocí projekt aplikace  
    > -   Odkazovaný projekt  
    > -   Sestavení  
  
    Tvary, které představují typy definované v souboru zdrojového kódu, se zobrazí v diagramu na pozici, kam jste soubor přetáhli.  
  
V projektu lze také zobrazit typy přetažením jednoho nebo více typů z uzlu projektu v zobrazení tříd do diagramu tříd.  
  
> [!TIP]
> Pokud zobrazení tříd není otevřený, otevřete zobrazení tříd z **zobrazení** nabídky.
  
Pokud chcete zobrazit typy na výchozí umístění v diagramu, vyberte jeden nebo více typů v zobrazení tříd, klikněte pravým tlačítkem na vybrané typy a zvolte **zobrazení diagramu tříd**.  
  
> [!NOTE]
>  Pokud v projektu existuje zavřený diagram tříd obsahující daný typ, diagram tříd se otevře a zobrazí tvar typu. Pokud ale v projektu neexistuje žádný diagram tříd obsahující daný typ, Návrhář tříd vytvoří v projektu nový diagram tříd a otevře jej pro zobrazení typu.  
  
Při prvním zobrazení typu v diagramu se jeho tvar ve výchozím nastavení zobrazí sbalený. Tvar můžete rozbalit a zobrazit jeho obsah.  
  
### <a name="to-display-the-contents-of-a-project-in-a-class-diagram"></a>K zobrazení obsahu projektu v diagramu tříd  
  
1.  V Průzkumníku řešení nebo zobrazení tříd, klikněte pravým tlačítkem na projekt a zvolte **zobrazení**, zvolte **zobrazení diagramu tříd**.  
  
     Vytvoří se automaticky vyplněný diagram tříd.  
  
## <a name="see-also"></a>Viz také
[Postupy: zobrazení dědičnosti mezi typy](how-to-view-inheritance-between-types.md)   
[Postupy: přizpůsobení diagramů tříd](how-to-customize-class-diagrams.md)   
[Zobrazování typů a vztahů](viewing-types-and-relationships.md)