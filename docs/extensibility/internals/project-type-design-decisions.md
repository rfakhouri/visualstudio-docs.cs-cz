---
title: "Rozhodnutí o návrhu typ projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, project file persistence
- project types, commitment mechanics
- project types, items
- project types, design decisions
ms.assetid: f68671fe-fd7a-4e56-a0b5-330b0f1fedb1
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a6649bd45aba299514b40e74b5683368bfd92b41
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="project-type-design-decisions"></a>Rozhodnutí o návrhu typ projektu
Než vytvoříte nový typ projektu, musíte nastavit několik rozhodnutí o návrhu týkající se typu vašeho projektu. Musíte se rozhodnout, jaké typy položky, které bude obsahovat projekty, jak bude natrvalo soubory projektu a jaké závazků model budete používat.  
  
## <a name="project-items"></a>Položky projektu  
 Použije váš projekt soubory nebo abstraktní objekty? Pokud chcete použít soubory, budou se soubory na základě odkaz nebo na základě adresáře? Jsou soubory nebo abstraktní objekty probíhající jako místní nebo vzdálené?  
  
 Položky v projektu může být soubory, nebo se může být více abstraktní objekty, například objekty v databázi úložiště nebo data připojení přes Internet. Pokud položek souborů, může být projektu odkaz na základě nebo na základě adresáře projektu.  
  
 V projektech na základě referenční může vyskytovat položky ve více než jeden projekt. Skutečný soubor, který představuje položku však nachází ve pouze jeden adresář. V projektech na základě adresářů všechny položky projektu existovat struktury adresářů.  
  
 Místní položky se ukládají na stejném počítači, kde je nainstalována aplikace. Vzdálené položky mohou být uloženy na samostatný server v místní síti nebo jinde v síti Internet.  
  
## <a name="project-file-persistence"></a>Trvalost souboru projektu  
 Data se uloží v běžné systémy plochého souboru nebo v strukturovaných úložiště? Soubory se otevřou pomocí standardního editoru nebo editoru specifické pro projekt?  
  
 Zachování jejich dat, většina aplikací uložit svá data do souboru a pak přečte zpět v případě, že uživatel musí zkontrolovat nebo změnit informace.  
  
 Strukturované nazývané také složené soubory se obvykle používá při několik objekty modelu COM (Component Object) je potřeba ukládat svoje trvalou data v jednom souboru. S strukturovaných úložiště můžete sdílet několik různých softwarové součásti soubor jediný disk.  
  
 Máte několik možností ke zvážení při výběru trvalosti pro položky v projektu. Můžete provést jednu z následujících možností:  
  
-   Každý soubor uložte jednotlivě, když se změnil.  
  
-   Zaznamenat mnoho transakcí v jediném **Uložit** operaci.  
  
-   Uložit soubory místně a publikovat na serveru nebo použijte jiný přístup k ukládání položky projektu, pokud položka představuje datové připojení ke vzdálenému objektu.  
  
 Další informace o trvalosti najdete v tématu [projektu trvalost](../../extensibility/internals/project-persistence.md) a [otevírání a ukládání položky projektu](../../extensibility/internals/opening-and-saving-project-items.md).  
  
## <a name="project-commitment-model"></a>Model závazků projektu  
 Trvalá data objektů se otevřou v režimu přímého nebo zpracovaných?  
  
 Když datové objekty jsou v režimu přímého otevřené, jsou okamžitě, nebo když uživatel ručně uloží soubor začlenit i metodu změny provedené v datech.  
  
 Když datových objektů jsou otevřené pomocí transakčního režimu, změny se ukládají do dočasného umístění v paměti a nejsou potvrzené, dokud uživatel ručně vybere možnost uložení souboru. V ten moment se všechny změny musí nastat společně nebo nebudou provedeny žádné změny.  
  
## <a name="see-also"></a>Viz také  
 [Kontrolní seznam: Vytvoření nové typy projektu](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Otevření a uložení položky projektu](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Trvalost projektu](../../extensibility/internals/project-persistence.md)   
 [Prvky modelu projektu](../../extensibility/internals/elements-of-a-project-model.md)   
 [Základní součásti služby projektu modelu](../../extensibility/internals/project-model-core-components.md)   
 [Vytváření typů projektů](../../extensibility/internals/creating-project-types.md)