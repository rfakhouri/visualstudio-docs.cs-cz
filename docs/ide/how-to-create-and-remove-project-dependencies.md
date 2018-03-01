---
title: "Postupy: vytvoření a odebrání závislostí projektu | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5fe8fe1706e6310c077399bb9300d439a7664d21
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-remove-project-dependencies"></a>Postupy: Vytváření a odebrání závislostí projektu
Při sestavování řešení, které obsahuje více projektů, může být nezbytné pro určité projekty nejprve sestavení, ke generování kódu, které používají jiné projekty. Když na projekt spotřebovává spustitelného kódu generovaných jiného projektu, projekt, který generuje kód se označuje jako závislosti projektu projekt, který využívá kód. Tyto vztahy závislosti lze definovat v **závislosti projektu** dialogové okno.  

### <a name="to-assign-dependencies-to-projects"></a>Přiřadit závislosti do projektů  

1.  V Průzkumníku řešení vyberte projektu.  

2.  Na **projektu** nabídce zvolte **závislosti projektu**.  

     **Závislosti projektu** otevře se dialogové okno.  

    > [!NOTE]
    >  **Závislosti projektu** možnost je dostupná pouze v řešení s více než jeden projekt.  

3.  Na **závislosti** vyberte projekt z **projektu** rozevírací nabídce.  

4.  V **závisí na** pole, zaškrtněte políčko jiných projektu, který musíte vytvořit před tento projekt.  

 Řešení musí obsahovat více než jeden projekt před vytvořením závislosti projektu.  

### <a name="to-remove-dependencies-from-projects"></a>Odebrání závislostí z projektů  

1.  V Průzkumníku řešení vyberte projektu.  

2.  Na **projektu** nabídce zvolte **závislosti projektu**.  

     **Závislosti projektu** otevře se dialogové okno.  

    > [!NOTE]
    >  **Závislosti projektu** možnost je dostupná pouze v řešení s více než jeden projekt.  

3.  Na **závislosti** vyberte projekt z **projektu** rozevírací nabídce.  

4.  V **závisí na** pole, zrušte zaškrtnutí políček vedle další projekty, které již nejsou závislých součástí pro tento projekt.  

## <a name="see-also"></a>Viz také  
 [Sestavování a čištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Kompilaci a sestavování](../ide/compiling-and-building-in-visual-studio.md)   
 [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
 [Správa vlastností projektů a řešení](managing-project-and-solution-properties.md)

