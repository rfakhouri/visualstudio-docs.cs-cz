---
title: 'Postupy: přístup k a omezit aktuální výběr | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, accessing the current selection
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 81036e04abc9eac2cbed2879839e95cce52166fc
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="how-to-access-and-constrain-the-current-selection"></a>Postupy: Přístup k aktuálnímu výběru a jeho omezení
Když píšete příkaz nebo gesto obslužnou rutinu pro váš jazyk specifické pro doménu, můžete určit, jaký element klepli pravým tlačítkem myši uživatele. Některé tvary nebo pole můžete také zabránit ve výběru. Například můžete uspořádat, že když uživatel klikne na ikonu dekoratéra, obrazec, který jej obsahuje místo něho se vybere. Omezíte-výběr tímto způsobem snižuje počet obslužných rutin, které máte k zápisu. Také umožňuje jednodušší pro uživatele, který můžete klikněte kamkoli do tvaru bez nutnosti vyhnout dekoratéra.  
  
## <a name="accessing-the-current-selection-from-a-command-handler"></a>Přístup k aktuálním výběru z obslužná rutina příkazu  
 Set – třída příkaz pro specifické pro doménu jazyk obsahuje obslužné rutiny příkazů pro vlastní příkazy. <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> Třída, ze kterého je odvozen třídu příkazu set pro jazyk specifické pro doménu, poskytuje několik členů pro přístup k aktuální výběr.  
  
 V závislosti na příkazu obslužná rutina může být nutné výběr v Návrháři modelu, Průzkumníka modelu nebo aktivní okno.  
  
#### <a name="to-access-selection-information"></a>Pro přístup k informacím výběr  
  
1.  <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> Třída definuje následující členy, které lze použít pro přístup k aktuální výběr.  
  
    |Člen|Popis|  
    |------------|-----------------|  
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsAnyDocumentSelectionCompartment%2A> – Metoda|Vrátí `true` Pokud je některý elementů vybrané v Návrháři modelu prostředí obrazce; jinak `false`.|  
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsDiagramSelected%2A> – Metoda|Vrátí `true` Pokud diagramu je vybraný v Návrháři modelu, jinak hodnota `false`.|  
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsSingleDocumentSelection%2A> – Metoda|Vrátí `true` Pokud přesně jeden element je vybraný v Návrháři modelu, jinak hodnota `false`.|  
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsSingleSelection%2A> – Metoda|Vrátí `true` Pokud přesně jeden element je vybraný v okně aktivní, jinak hodnota `false`.|  
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.CurrentDocumentSelection%2A> Vlastnost|Získá kolekci elementů vybrané v Návrháři model jen pro čtení.|  
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.CurrentSelection%2A> Vlastnost|Získá kolekci elementů vybraný v aktivní okno jen pro čtení.|  
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.SingleDocumentSelection%2A> Vlastnost|Získá prvek primární výběru v Návrháři modelu.|  
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.SingleSelection%2A> Vlastnost|Získá prvek primární výběru aktivního okna.|  
  
2.  <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet.CurrentDocView%2A> Vlastnost <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> třída poskytuje přístup k <xref:Microsoft.VisualStudio.Modeling.Shell.DiagramDocView> objekt, který reprezentuje okně návrháře modelu a poskytuje další přístup vybrané elementy v Návrháři modelu.  
  
3.  Kromě toho generovaný kód definuje vlastnost okno Průzkumníka nástroj a ve vlastnosti explorer výběr v příkazu set – třída pro jazyk specifické pro doménu.  
  
    -   Vlastnost okno Průzkumníka nástroj vrací instanci třídy okno Průzkumníka nástroj pro jazyk specifické pro doménu. Odvozená třída okno nástroje Průzkumník z <xref:Microsoft.VisualStudio.Modeling.Shell.ModelExplorerToolWindow> třídy a představuje Průzkumníka modelu pro jazyk specifické pro doménu.  
  
    -   `ExplorerSelection` Vlastnost vrací vybraný prvek v okně Průzkumníka modelu pro jazyk specifické pro doménu.  
  
## <a name="determining-which-window-is-active"></a>Určení, které okno je aktivní  
 <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> Obsahuje rozhraní definuje členy, které poskytují přístup k aktuální stav výběru v prostředí. Můžete získat <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> objekt ze třídy balíček nebo třídu příkazu set pro jazyk specifické pro doménu prostřednictvím `MonitorSelection` vlastnost definovanou v základní třídě jednotlivých. Balíček třída odvozená z <xref:Microsoft.VisualStudio.Modeling.Shell.ModelingPackage> třídy a příkaz set – třída odvozená z <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> třídy.  
  
#### <a name="to-determine-from-a-command-handler-what-type-of-window-is-active"></a>Určuje z obslužná rutina příkazu, jaký typ okna je aktivní  
  
1.  <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.MonitorSelection%2A> Vlastnost <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> vrací <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> objekt, který poskytuje přístup k aktuální stav výběru v prostředí.  
  
2.  <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService.CurrentSelectionContainer%2A> Vlastnost <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> rozhraní získá aktivní výběr kontejneru, který může lišit od aktivní okno.  
  
3.  Přidejte že následující vlastnosti pro příkaz set – třída pro vás specifické pro doménu jazyk, který chcete určit, jaký typ okna je aktivní.  
  
    ```csharp  
    // using Microsoft.VisualStudio.Modeling.Shell;  
  
    // Returns true if the model designer is the active selection container;  
    // otherwise, false.  
    protected bool IsDesignerActive  
    {  
        get  
        {  
            return (this.MonitorSelection.CurrentSelectionContainer  
                is DiagramDocView);  
        }  
    }  
  
    // Returns true if the model explorer is the active selection container;  
    // otherwise, false.  
    protected bool IsExplorerActive  
    {  
        get  
        {  
            return (this.MonitorSelection.CurrentSelectionContainer  
                is ModelExplorerToolWindow);  
        }  
    }  
    ```  
  
## <a name="constraining-the-selection"></a>Omezíte-výběr  
 Přidáním výběr pravidel, můžete řídit prvky, které jsou vybrané, když uživatel vybere element v modelu. Například pokud chcete umožnit uživatelům počet elementů považovat za jedné jednotky, můžete použít pravidlo výběru.  
  
#### <a name="to-create-a-selection-rule"></a>K vytvoření pravidla, výběr  
  
1.  Vytvořte soubor vlastního kódu v projektu DSL  
  
2.  Definice třídy výběr pravidla, která je odvozená od <xref:Microsoft.VisualStudio.Modeling.Diagrams.DiagramSelectionRules> třídy.  
  
3.  Přepsání <xref:Microsoft.VisualStudio.Modeling.Diagrams.DiagramSelectionRules.GetCompliantSelection%2A> metoda třídy výběr pravidla použít kritéria výběru.  
  
4.  Přidejte třídu definice pro třídu ClassDiagram do souboru vlastní kód.  
  
     `ClassDiagram` Třída odvozená z <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram> třídy a je definována v generovaného kódu souboru Diagram.cs, v projektu DSL.  
  
5.  Přepsání <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.SelectionRules%2A> vlastnost `ClassDiagram` třídy vracení pravidlo vlastního výběru.  
  
     Výchozí implementaci <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.SelectionRules%2A> vlastnost získá objekt výběru pravidlo, který nelze změnit výběr.  
  
### <a name="example"></a>Příklad  
 Soubor následující kód vytvoří výběr pravidlo, které rozšiřuje výběr zahrnout všechny instance každé obrazce domén, které bylo původně vybrali.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
namespace CompanyName.ProductName.GroupingDsl  
{  
    public class CustomSelectionRules : DiagramSelectionRules  
    {  
        protected Diagram diagram;  
        protected IElementDirectory elementDirectory;  
  
        public CustomSelectionRules(Diagram diagram)  
        {  
            if (diagram == null) throw new ArgumentNullException();  
  
            this.diagram = diagram;  
            this.elementDirectory = diagram.Store.ElementDirectory;  
        }  
  
        /// <summary>Called by the design surface to allow selection filtering.  
        /// </summary>  
        /// <param name="currentSelection">[in] The current selection before any  
        /// ShapeElements are added or removed.</param>  
        /// <param name="proposedItemsToAdd">[in/out] The proposed DiagramItems to  
        /// be added to the selection.</param>  
        /// <param name="proposedItemsToRemove">[in/out] The proposed DiagramItems  
        /// to be removed from the selection.</param>  
        /// <param name="primaryItem">[in/out] The proposed DiagramItem to become  
        /// the primary DiagramItem of the selection. A null value signifies that  
        /// the last DiagramItem in the resultant selection should be assumed as  
        /// the primary DiagramItem.</param>  
        /// <returns>true if some or all of the selection was accepted; false if  
        /// the entire selection proposal was rejected. If false, appropriate  
        /// feedback will be given to the user to indicate that the selection was  
        /// rejected.</returns>  
        public override bool GetCompliantSelection(  
            SelectedShapesCollection currentSelection,  
            DiagramItemCollection proposedItemsToAdd,  
            DiagramItemCollection proposedItemsToRemove,  
            DiagramItem primaryItem)  
        {  
            if (currentSelection.Count == 0 && proposedItemsToAdd.Count == 0) return true;  
  
            HashSet<DomainClassInfo> itemsToAdd = new HashSet<DomainClassInfo>();  
  
            foreach (DiagramItem item in proposedItemsToAdd)  
            {  
                if (item.Shape != null)  
                    itemsToAdd.Add(item.Shape.GetDomainClass());  
            }  
            proposedItemsToAdd.Clear();  
            foreach (DomainClassInfo classInfo in itemsToAdd)  
            {  
                foreach (ModelElement element  
                    in this.elementDirectory.FindElements(classInfo, false))  
                {  
                    if (element is ShapeElement)  
                    {  
                        proposedItemsToAdd.Add(  
                            new DiagramItem((ShapeElement)element));  
                    }  
                }  
            }  
  
            return true;  
        }  
    }  
  
    public partial class ClassDiagram  
    {  
        protected CustomSelectionRules customSelectionRules = null;  
  
        protected bool multipleSelectionMode = true;  
  
        public override DiagramSelectionRules SelectionRules  
        {  
            get  
            {  
                if (multipleSelectionMode)  
                {  
                    if (customSelectionRules == null)  
                    {  
                        customSelectionRules = new CustomSelectionRules(this);  
                    }  
                    return customSelectionRules;  
                }  
                else  
                {  
                    return base.SelectionRules;  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet>   
 <xref:Microsoft.VisualStudio.Modeling.Shell.ModelingPackage>   
 <xref:Microsoft.VisualStudio.Modeling.Shell.DiagramDocView>   
 <xref:Microsoft.VisualStudio.Modeling.Shell.ModelExplorerToolWindow>   
 <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService>   
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.DiagramSelectionRules>   
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>