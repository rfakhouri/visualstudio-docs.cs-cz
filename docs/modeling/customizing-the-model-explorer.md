---
title: "Přizpůsobení Průzkumníka modelu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.explorerbehavior
helpviewer_keywords:
- Domain-Specific Language Tools, Domain-Specific Language Explorer
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: eac91df1a07e54b80e88538695b1cc22353396d6
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="customizing-the-model-explorer"></a>Přizpůsobení Průzkumníka modelů
Pro vaše Návrhář jazyka domény můžete následujícím způsobem změnit vzhled a chování aplikace explorer:  
  
-   Změňte záhlaví okna.  
  
-   Změníte na kartě ikonu.  
  
-   Ikony pro uzly změňte.  
  
-   Skryjte uzly.  
  
## <a name="changing-the-window-title"></a>Změna záhlaví okna  
 Chcete-li změnit název okna generovaného Průzkumníku, vyberte **Explorer chování** v **DSL Průzkumníka**a potom v **vlastnosti** nastavte  **Název** vlastnost, která má název, který chcete.  
  
## <a name="changing-the-tab-icon"></a>Změna ikonu Karta  
 Na kartě ikonu pro aplikaci explorer můžete změnit ikonou 16 x 16 pixelů v souboru .bmp. Umístit soubor ikony ve složce \DslPackage\Resources\ a poté změňte název souboru do **ModelExplorerToolWindowBitmaps.bmp**. Například můžete změnit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] setup.ico ikonu souboru do formátu BMP a přejmenujte ji na **DSLLanguageName\DslPackage\Resources\ModelExplorerToolWindowBitmaps.bmp**. Vygenerovaný návrháře se zobrazí tato ikona na kartě aplikace explorer ukotvení společně s **Průzkumníku řešení**.  
  
## <a name="setting-custom-icons-on-explorer-nodes"></a>Nastavení vlastních ikon na Průzkumníka uzly  
 Pomocí Průzkumníka uzlu nastavení můžete přizpůsobit uzly ve vaší explorer. Následující postup ukazuje, jak přidat ikonu do uzlu.  
  
#### <a name="to-add-an-icon-to-an-explorer-node"></a>Chcete-li přidat ikonu do Průzkumníka uzlu  
  
1.  Vytvoření [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] řešení pomocí šablony řešení tok úkolů.  
  
2.  Umístění souboru .bmp, který obsahuje ikonu 16 x 16 pixelů v **Dsl\Resources** složky v řešení.  
  
3.  V **DSL Explorer**, klikněte pravým tlačítkem na **Explorer chování** a pak klikněte na **přidejte nové nastavení Explorer uzlu**.  
  
     **ExplorerNodeSettings** uzel se objeví pod uzlem **vlastní uzlu nastavení** uzlu.  
  
4.  Vyberte **ExplorerNodeSettings**a potom v **vlastnosti** nastavte **třída** k **objektu Actor**.  
  
5.  Nastavit **ikonu k zobrazení** k cestě soubor ikony.  
  
6.  Proveďte transformaci všech šablon a sestavení a spuštění řešení.  
  
7.  V Návrháři generovaného otevřete na diagram.  
  
     Průzkumníku by měl zobrazit tři **objektu Actor** uzlů, které mají vaše ikonu.  
  
> [!NOTE]
>  Pokud jste nastavili ikona uzel pro libovolný element, který se zobrazí v Průzkumníku vygenerovaný, všechny uzly Průzkumníka se zobrazí ikona. Pokud byla nastavena žádná ikona, uzly se zobrazí na výchozí ikonu.  
  
## <a name="changing-the-name-displayed-on-an-explorer-node"></a>Změna názvu, zobrazí v uzlu Explorer  
 Můžete změnit, jak jsou zobrazeny názvy prvků modelu v vaší Průzkumníku. Následující postup ukazuje, jak zobrazit název **úloh** který odkazuje **komentář** v uzlu komentář.  
  
#### <a name="to-display-a-property"></a>Chcete-li zobrazit vlastnosti  
  
1.  Otevřete řešení, které jste vytvořili v předchozím kroku.  
  
2.  Ujistěte se, že **komentář** odkazuje jenom na jednu doménu třídu nastavením násobnosti atributu role s názvem vlastnosti **témata** k 0..1. Název vlastnosti měl být **subjektu**, a měl být název relace **CommentReferencesSubject**.  
  
3.  V **DSL Explorer**, klikněte pravým tlačítkem na **Explorer chování** a pak klikněte na **přidejte nové nastavení Explorer uzlu**.  
  
     **ExplorerNodeSettings** uzel se objeví pod uzlem **vlastní uzlu nastavení** uzlu.  
  
4.  Vyberte **ExplorerNodeSettings**a potom v **vlastnosti** nastavte **třída** k **komentář**.  
  
5.  Klikněte pravým tlačítkem myši **komentář** uzel a pak klikněte na tlačítko **přidat novou cestu vlastnost**.  
  
     Zobrazí se nový uzel s názvem **vlastnost zobrazena**.  
  
6.  Vyberte **vlastnost zobrazena**a potom v **vlastnosti** okně klikněte na pole hodnota **cesta k vlastnosti**. Vyberte **komentář**, pak **CommentReferencesSubject**, pak **FlowElement**. Výsledná cesta by měla vypadat přibližně **CommentReferencesSubject.Subject/! Předmět**.  
  
7.  V poli hodnota **vlastnost**, vyberte **název**.  
  
8.  Proveďte transformaci všech šablon a sestavte a spusťte řešení.  
  
9. V Návrháři generovaného otevřete na diagram.  
  
10. Kreslení **komentář konektor** mezi komentář elementu a **Task1** element v diagramu.  
  
     Uzel Explorer by se měla zobrazovat jako komentář **Task1**.  
  
## <a name="hiding-nodes"></a>Skryté uzly  
 Uzel můžete skrýt v vaší Průzkumníku přidáním jeho cestu k **skryté uzly** uzlu **DSL Explorer**. Následující postup ukazuje, jak skrýt **komentář** uzlů.  
  
#### <a name="to-hide-an-explorer-node"></a>Chcete-li skrýt do Průzkumníka uzlu  
  
1.  Otevřete řešení, které jste vytvořili v předchozím kroku.  
  
2.  V **DSL Explorer**, klikněte pravým tlačítkem na **Explorer chování** a pak klikněte na **přidat novou cestu domény**.  
  
     A **domény cesta** uzel se objeví pod **skryté uzly**.  
  
3.  Vyberte **domény cesta**a potom v **vlastnosti** okně klikněte na pole hodnota **cesta definice**. Vyberte **FlowGraph**, pak **FlowGraphHasComments**. Výsledná cesta by měla vypadat přibližně **FlowGraphHasComments.Comments**  
  
4.  Proveďte transformaci všech šablon a sestavte a spusťte řešení.  
  
5.  V Návrháři generovaného otevřete na diagram.  
  
     Průzkumníku by měl zobrazit pouze **aktéři** uzel a nesmí zobrazit **komentáře** uzlu.  
  
## <a name="see-also"></a>Viz také

[Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)