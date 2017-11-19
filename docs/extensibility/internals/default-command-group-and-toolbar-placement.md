---
title: "Výchozí příkaz, skupiny a umístění panelu nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands [Visual Studio], default groups
- toolbars [Visual Studio], default
- commands [Visual Studio], default editor
- command groups
- commands [Visual Studio], default IDE
- commands [Visual Studio], default product
ms.assetid: 35342110-d639-4577-8367-00b21dcc6f07
caps.latest.revision: "30"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c5f1ec42408e4fd7d33d9445ae09252fae8d03db
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="default-command-group-and-toolbar-placement"></a>Příkaz výchozí skupiny a umístění panelu nástrojů
Pro produkt jednotnost a stabilitu, uživatelské rozhraní zobrazí určitých skupin příkaz ve výchozím nastavení, a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] obsahuje definice pro příkazy a příkaz skupiny. VSPackages můžete také použít standardní příkazy a příkaz skupiny.  
  
 Výchozí skupiny příkaz spadají do tří kategorií: IDE příkazy, příkazy produktu a příkazů editoru.  
  
## <a name="default-ide-commands"></a>Výchozí IDE příkazy  
 Panel nástrojů IDE výchozí obsahuje příkazy, které jsou sdíleny všechny produkty, které jsou obsažené v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Patří mezi ně příkazy týkající se operací obecné projektu, například **Uložit** příkaz a **přidat položku** příkaz. VSPackages neměli přidat do ani odečtena z tohoto panelu nástrojů, s jednou výjimkou: Pokud produkt nebo VSPackage přidá nové okno nástroje, pak okna musí být přidaní do seznamu k dispozici nástroj windows na **zobrazení** nabídky. Nové produkty nebo VSPackages můžete přidat vlastní panel nástrojů.  
  
## <a name="default-product-commands"></a>Výchozí produktu příkazy  
 Každý produkt může poskytovat IDE s vlastní výchozí panel nástrojů, která obsahuje důležité a často používané příkazy. Je však nejvhodnější, používat stávající nabídek a panelů nástrojů, kdykoli je to možné a doplní podle potřeby s panelů nástrojů konkrétním úlohám.  
  
 Pole s prioritou pro panel nástrojů Určuje umístění jeho řádek. Nulové priority umístí panelu nástrojů na třetí řádek (řádek 3), pod panelu nabídek (řádek 1) a **standardní** panelu nástrojů (řádek 2). Proto se zobrazí na řádku panelů nástrojů (s prioritou + 3). Následné panely nástrojů jsou umístěny na stejném řádku, pokud je prostor; jinak se automaticky přesunou na další řádek.  
  
## <a name="default-editor-commands"></a>Výchozí příkazů editoru  
 VSPackage poskytující vlastního editoru by měl poskytovat výchozí panel nástrojů, který obsahuje nejdůležitější a často používané příkazy v této editoru. Panel nástrojů editoru by se zobrazit při editoru aktivní a skryt, pokud editor není aktivní. Tento přehled je řízena v `VisibilityConstraints Element` .vsct souboru.  
  
 Panely nástrojů editoru musí být umístěny pod panely nástrojů rozhraní IDE a produkt.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy definované IDE, nabídky a skupin](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)   
 [Jak přidat VSPackages prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)