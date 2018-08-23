---
title: 'Postupy: vytváření a odebrání závislostí projektu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ProjectDependenciesDlg
helpviewer_keywords:
- vs.build.projectdependencies
- project dependencies
- builds [Visual Studio], setting up
- project build configurations, dependencies
- dependencies, project
- projects [Visual Studio], dependencies
ms.assetid: e2a0a8ff-dae7-40a8-b774-b88aa5235183
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3626cc4c13600b0a6f20cc40713bd77f4527a3ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672627"
---
# <a name="how-to-create-and-remove-project-dependencies"></a>Postupy: Vytváření a odebrání závislostí projektu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: vytváření a odebrání závislostí projektu](https://docs.microsoft.com/visualstudio/ide/how-to-create-and-remove-project-dependencies).  
  
Při sestavování řešení, které obsahuje více projektů, může být nezbytné k sestavení některých projektů nejprve, pro generování kódu, které používají jiné projekty. Projekt využívá spustitelný kód vygenerovaný touto jiného projektu, projektu, který generuje kód se označuje jako závislost projektu, který využívá kód projektu. Tyto vztahy závislostí lze definovat v **závislosti projektu** dialogové okno.  
  
### <a name="to-assign-dependencies-to-projects"></a>K přiřazení závislostí do projektů  
  
1.  V Průzkumníku řešení vyberte projekt.  
  
2.  Na **projektu** nabídce zvolte **závislosti projektu**.  
  
     **Závislosti projektu** zobrazí se dialogové okno.  
  
    > [!NOTE]
    >  **Závislosti projektu** možnost dostupná jenom v řešení s více než jeden projekt.  
  
3.  Na **závislosti** kartu, vyberte projekt z **projektu** rozevírací nabídky.  
  
4.  V **závisí na** pole, zaškrtněte políčko jiný projekt, který musíte vytvořit předtím, než se tento projekt.  
  
 Řešení se musí skládat z více než jeden projekt, než budete moct vytvořit závislosti projektu.  
  
### <a name="to-remove-dependencies-from-projects"></a>Chcete-li odebrat závislosti z projektů  
  
1.  V Průzkumníku řešení vyberte projekt.  
  
2.  Na **projektu** nabídce zvolte **závislosti projektu**.  
  
     **Závislosti projektu** zobrazí se dialogové okno.  
  
    > [!NOTE]
    >  **Závislosti projektu** možnost dostupná jenom v řešení s více než jeden projekt.  
  
3.  Na **závislosti** kartu, vyberte projekt z **projektu** rozevírací nabídky.  
  
4.  V **závisí na** pole, zrušte zaškrtnutí políček vedle jiné projekty, které už nejsou závislosti tohoto projektu.  
  
## <a name="see-also"></a>Viz také  
 [Sestavování a čištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Kompilování a sestavování](../ide/compiling-and-building-in-visual-studio.md)   
 [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
 [NIB postupy: Změna vlastností projektu a nastavení konfigurace](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)



