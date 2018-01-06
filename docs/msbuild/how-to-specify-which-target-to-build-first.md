---
title: "Postupy: Zadejte, který prvního cíle k sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DefaultTargets attribute [MSBuild]
- MSBuild, specifying the defalut target
- MSBuild, DefaultTargets attribute
ms.assetid: a580ba5b-2919-42d2-ae38-1af991e0205a
caps.latest.revision: "17"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a1d5b2bbf218d35cf20638d865c6c78379c5f02b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-which-target-to-build-first"></a>Postupy: Určení prvního cíle k sestavení
Soubor projektu může obsahovat jednu nebo více `Target` prvků, které definují, jak sestavení projektu. [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) Modul sestavení první ho projektu najde a všechny závislosti, pokud soubor projektu neobsahuje `DefaultTargets` atribut `InitialTargets` pomocí příkazového řádku je zadán atribut nebo cíl **/ Cíl** přepínače.  
  
## <a name="using-the-initialtargets-attribute"></a>Používání atributu InitialTargets  
 `InitialTargets` Atribut `Project` element určuje cíl, který bude spuštěn jako první, i když cíle jsou zadány na příkazovém řádku nebo v `DefaultTargets` atribut.  
  
#### <a name="to-specify-one-initial-target"></a>Chcete-li určit jeden počáteční cíl  
  
-   Zadat výchozí cílový v `InitialTargets` atribut `Project` elementu. Příklad:  
  
     `<Project InitialTargets="Clean">`  
  
 Můžete zadat více než jeden počáteční cíl v `InitialTargets` atribut výpis cílů v pořadí a použitím středníkem k oddělení každém cíli. Cíle v seznamu se spustí sekvenčně.  
  
#### <a name="to-specify-more-than-one-initial-target"></a>Chcete-li zadat více než jeden počáteční cíl  
  
-   Počáteční cíle, oddělené středníky, v seznamu `InitialTargets` atribut `Project` elementu. Chcete-li například spustit `Clean` cíl a potom `Compile` cíle, zadejte:  
  
     `<Project InitialTargets="Clean;Compile">`  
  
## <a name="using-the-defaulttargets-attribute"></a>Pomocí defaulttargets – atribut  
 `DefaultTargets` Atribut `Project` element určuje, které cíl nebo cíle jsou vytvořeny Pokud cíl není explicitně zadat na příkazovém řádku. Pokud cíle jsou určené v obou `InitialTargets` a `DefaultTargets` atributy a žádný cíl je zadán v příkazovém řádku [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] spouští cíle zadané v `InitialTargets` atribut následuje cíle zadané v `DefaultTargets` atribut.  
  
#### <a name="to-specify-one-default-target"></a>Chcete-li určit jeden cíl výchozí  
  
-   Zadat výchozí cílový v `DefaultTargets` atribut `Project` elementu. Příklad:  
  
     `<Project DefaultTargets="Compile">`  
  
 Můžete zadat více než jeden výchozí cíl v `DefaultTargets` atribut výpis cílů v pořadí a použitím středníkem k oddělení každém cíli. Cíle v seznamu se spustí sekvenčně.  
  
#### <a name="to-specify-more-than-one-default-target"></a>Chcete-li zadat více než jeden výchozí cíl  
  
-   Výchozí cíle, oddělené středníky, v seznamu `DefaultTargets` atribut `Project` elementu. Chcete-li například spustit `Clean` cíl a potom `Compile` cíle, zadejte:  
  
     `<Project DefaultTargets="Clean;Compile">`  
  
## <a name="using-the-target-switch"></a>/ Target přepínač pomocí  
 Pokud výchozí cíl není definován v souboru projektu, nebo pokud nechcete použít výchozí cílených, můžete použít přepínač příkazového řádku **/target** k zadejte jiný cíl. Cíl nebo cíle zadaným **/target** přepínač spouštějí místo cíle určeného `DefaultTargets` atribut. Cíle zadané v `InitialTargets` atribut vždy spouští jako první.  
  
#### <a name="to-use-a-target-other-than-the-default-target-first"></a>Nejprve použít cíl než výchozí cíl  
  
-   Zadejte cíl jako první cíl pomocí **/target** přepínač příkazového řádku. Příklad:  
  
     `msbuild file.proj /target:Clean`  
  
#### <a name="to-use-several-targets-other-than-the-default-targets-first"></a>Nejprve použít několik cílů než výchozí cíle  
  
-   Seznam cílů, oddělených středníkem nebo čárkou, pomocí **/target** přepínač příkazového řádku. Příklad:  
  
     `msbuild <file name>.proj /t:Clean;Compile`  
  
## <a name="see-also"></a>Viz také
  [MSBuild](../msbuild/msbuild.md)  
 [Cíle](../msbuild/msbuild-targets.md)   
 [Postupy: Vyčištění sestavení](../msbuild/how-to-clean-a-build.md)