---
title: "Pořadí sestavení cíle | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: msbuild, build order
ms.assetid: f4a26339-9f9a-497a-9aa6-0797183d450d
caps.latest.revision: "18"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7768d6ba35c2116c658dcd1b7968080932b99543
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="target-build-order"></a>Pořadí sestavení cílů
Pokud vstup jeden cíl závisí na výstup jiný cíl, musejí být seřazeny cíle. Tyto atributy můžete použít k určení pořadí, ve kterém jsou spuštěny cíle:  
  
-   `InitialTargets`. To `Project` i v případě, že cíle jsou zadány na příkazovém řádku nebo v Určuje atribut cíle, které se spustí nejprve `DefaultTargets` atribut.  
  
-   `DefaultTargets`. To `Project` atribut určuje, které cíle spouštějí Pokud cíl není explicitně zadat na příkazovém řádku.  
  
-   `DependsOnTargets`. To `Target` cíle, které musí spustit před spuštěním tento cíl Určuje atribut.  
  
-   `BeforeTargets`a `AfterTargets`. Tyto `Target` atributy určují, že tento cíl měly být spuštěny před nebo po zadaného cíle (MSBuild 4.0).  
  
 Cíl je dvakrát během sestavení, nebude nikdy spuštěn, i v případě, že na něm závisí následující cíl v sestavení. Jakmile byl spuštěn na cíl, jeho příspěvkem k sestavení je dokončena.  
  
 Může mít cíle `Condition` atribut. Pokud je zadaná podmínka vyhodnocena jako `false`, cíl není spuštěn a nemá žádný vliv na sestavení. Další informace o podmínkách najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).  
  
## <a name="initial-targets"></a>Počáteční cíle  
 `InitialTargets` Atribut [projektu](../msbuild/project-element-msbuild.md) element určuje cílů, které se spustí nejprve i v případě, že cíle jsou zadány na příkazovém řádku nebo v `DefaultTargets` atribut. Počáteční cíle jsou obvykle používány pro kontrolu chyb.  
  
 Hodnota `InitialTargets` atribut může být oddělený středníkem, seřazený seznam cíle. Následující příklad určuje, že `Warm` cíle běží a potom `Eject` cíle spustí.  
  
```xml  
<Project InitialTargets="Warm;Eject" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
```  
  
 Importované projekty může mít vlastní `InitialTargets` atributy. Všechny cíle počáteční je agregován společně a spusťte v pořadí.  
  
 Další informace najdete v tématu [postup: Určete který cíl sestavení první](../msbuild/how-to-specify-which-target-to-build-first.md).  
  
## <a name="default-targets"></a>Výchozí cíle  
 `DefaultTargets` Atribut [projektu](../msbuild/project-element-msbuild.md) element určuje, které cíl nebo cíle jsou vytvořeny Pokud cíl není explicitně zadán v příkazovém řádku.  
  
 Hodnota `DefaultTargets` atribut může být oddělený středníkem, seřazený seznam výchozí cíle. Následující příklad určuje, že `Clean` cíle běží a potom `Build` cíle spustí.  
  
```xml  
<Project DefaultTargets="Clean;Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
```  
  
 Můžete přepsat výchozí cíle pomocí **/target** přepnout na příkazovém řádku. Následující příklad určuje, že `Build` cíle běží a potom `Report` cíle spustí. Když zadáte cíle tímto způsobem, jsou ignorovány všechny výchozí cíle.  
  
 `msbuild /target:Build;Report`  
  
 Pokud jsou zadané počáteční cíle a výchozí cíle a pokud nejsou zadány žádné příkazového řádku cíle, MSBuild nejprve spustí počáteční cíle a poté spustí výchozí cíle.  
  
 Importované projekty může mít vlastní `DefaultTargets` atributy. První `DefaultTargets` zjištěn atribut určuje, které výchozí cíle spustí.  
  
 Další informace najdete v tématu [postup: Určete který cíl sestavení první](../msbuild/how-to-specify-which-target-to-build-first.md).  
  
## <a name="first-target"></a>První cíl  
 Pokud pak spustí prvního cíle MSBuild nejsou žádné počáteční cíle, výchozí cíle nebo příkazového řádku cíle, zjistí v souboru projektu nebo všechny importované projektu soubory.  
  
## <a name="target-dependencies"></a>Závislosti cílů  
 Cíle můžete popsat vztahů závislosti mezi sebou. `DependsOnTargets` Atribut uvádí, že cíl závisí na jiné cíle. Například  
  
```xml  
<Target Name="Serve" DependsOnTargets="Chop;Cook" />  
```  
  
 informuje MSBuild, který `Serve` cíl závisí na `Chop` cíl a `Cook` cíl. MSBuild běží `Chop` cíl a potom spustí `Cook` cíle před jeho spuštěním `Serve` cíl.  
  
## <a name="beforetargets-and-after-targets"></a>BeforeTargets a po cíle  
 V nástroji MSBuild 4.0, můžete zadat cílový pořadí pomocí `BeforeTargets` a `AfterTargets` atributy.  
  
 Vezměte v úvahu následující skript.  
  
```xml  
<Project DefaultTargets="Compile;Link" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Compile">  
        <Message Text="Compiling" />  
    </Target>  
    <Target Name="Link">  
        <Message Text="Linking" />  
    </Target>  
</Project>  
```  
  
 K vytvoření zprostředkující cíl `Optimize` používající `Compile` cíle, ale předtím, než `Link` cíle, přidejte následující cíl kdekoli v `Project` element.  
  
```xml  
<Target Name="Optimize"   
    AfterTargets="Compile" BeforeTargets="Link">  
    <Message Text="Optimizing" />  
</Target>  
```  
  
## <a name="determining-the-target-build-order"></a>Určení pořadí sestavení cíle  
 Pořadí sestavení cílů určuje MSBuild následujícím způsobem:  
  
1.  `InitialTargets`cíle jsou spuštěny.  
  
2.  Cíle zadané na příkazovém řádku pomocí **/target** spouštějí přepínače. Pokud zadáte žádné cíle na příkazovém řádku, pak se `DefaultTargets` spouštějí cíle. Pokud ani jeden z nich je k dispozici, spusťte je prvního cíle došlo.  
  
3.  `Condition` Vyhodnotí atribut cíle. Pokud `Condition` atribut je k dispozici a vyhodnocuje `false`, cíl není spuštěn a nemá žádný další vliv na sestavení.  
  
4.  Před provedením cíl jeho `DependsOnTargets` spouštějí cíle.  
  
5.  Před provedením cíl žádné cílové, jsou uvedené v `BeforeTargets` atribut běží.  
  
6.  Před provedením cíl jeho `Inputs` atribut a `Outputs` jsou porovnávány atribut. Pokud MSBuild zjistí, že všechny výstupní soubory jsou zastaralé s ohledem na odpovídající vstupní soubor nebo soubory a potom MSBuild provede cíl. MSBuild přeskočí, jinak hodnota cíle.  
  
7.  Po cíl je proveden nebo přeskočené, všechny cíl, který uvádí v `AfterTargets` atribut běží.  
  
## <a name="see-also"></a>Viz také  
 [Cíle](../msbuild/msbuild-targets.md)