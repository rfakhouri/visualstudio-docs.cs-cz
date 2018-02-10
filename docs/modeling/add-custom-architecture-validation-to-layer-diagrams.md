---
title: "Přidání ověřování vlastní architektury do diagramů závislostí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, adding custom validation
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7679398e5acfc2f23d51ea7f943e35d0d82e500e
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="add-custom-architecture-validation-to-dependency-diagrams"></a>Přidání ověřování vlastní architektury do diagramů závislostí
V sadě Visual Studio můžete uživatele ověřit zdrojového kódu v projektu proti model vrstvy, aby můžete ověřit, že zdrojový kód odpovídá závislosti v diagramu závislostí. Je algoritmus standardní ověřování, ale můžete definovat vlastní rozšíření ověření.  
  
 Když uživatel vybere **ověření architektura** příkazů v diagramu závislostí, je volána metoda standardní ověřování, za nímž následuje žádné ověření rozšíření, které byly nainstalovány.  
  
> [!NOTE]
>  V diagramu závislostí je hlavním účelem ověření Porovnejte diagram s kód programu v dalších částech tohoto řešení.  
  
 Rozšíření vrstvy ověření můžete balíček do Visual Studio integrace rozšíření (VSIX), který distribuujete do jiných uživatelů v sadě Visual Studio. Vaše ověření VSIX můžete umístit buď samostatně nebo v kombinaci se ve stejné VSIX jako ostatní rozšíření. Kód validátoru musí zápisu v jeho vlastní projektu sady Visual Studio, není ve stejném projektu jako ostatní rozšíření.  
  
> [!WARNING]
>  Po vytvoření projektu ověření, zkopírujte [ukázkový kód](#example) na konci tohoto tématu a potom upravením, že na své vlastní potřebuje.  
  
## <a name="requirements"></a>Požadavky  
 V tématu [požadavky](../modeling/extend-layer-diagrams.md#prereqs).  
  
## <a name="defining-a-layer-validator-in-a-new-vsix"></a>Definování validátor vrstvy v nové VSIX  
 Nejrychlejší způsob vytváření validátor se má používat v šabloně projektů. Tento kód a VSIX manifest umístí do stejného projektu.  
  
#### <a name="to-define-an-extension-by-using-a-project-template"></a>Můžete definovat rozšíření pomocí šablony projektu  
  
1.  Vytvoření projektu v nové řešení pomocí **nový projekt** příkaz na **souboru** nabídky.  
  
2.  V **nový projekt** dialogovém **projekty modelování**, vyberte **vrstvy Návrhář ověření rozšíření**.  
  
     Vytvoří šablona dílčí projekt, který obsahuje malé příklad.  
  
    > [!WARNING]
    >  Do šablony makethe fungovat správně:  
    >   
    >  -   Upravit volání `LogValidationError` odebrat volitelné argumenty `errorSourceNodes` a `errorTargetNodes`.  
    > -   Pokud používáte vlastní vlastnosti, použijte aktualizace uvedený v [přidání vlastních vlastností do diagramů závislostí](../modeling/add-custom-properties-to-layer-diagrams.md).  
  
3.  Upravte kód, který definuje váš ověření. Další informace najdete v tématu [programování ověření](#programming).  
  
4.  K testování rozšíření, najdete v části [ladění ověření vrstev](#debugging).  
  
    > [!NOTE]
    >  Metodu bude volán jen v konkrétních případech a zarážky nebude fungovat automaticky. Další informace najdete v tématu [ladění ověření vrstev](#debugging).  
  
5.  Chcete-li nainstalovat rozšíření v hlavní instanci sady Visual Studio, nebo v jiném počítači, vyhledejte **VSIX** souboru v **bin\\\***. Zkopírujte jej do počítače, ve které chcete nainstalovat a pak na ni dvakrát kliknete. Chcete-li ho odinstalovat, použijte **rozšíření a aktualizace** na **nástroje** nabídky.  
  
## <a name="adding-a-layer-validator-to-a-separate-vsix"></a>Přidání validátor vrstvy do samostatné VSIX  
 Pokud chcete vytvořit jednu VSIX, který obsahuje validátory vrstvy, příkazy a další rozšíření, doporučujeme vytvořit jeden projekt k definování VSIX a samostatné projekty pro obslužné rutiny. 
  
#### <a name="to-add-layer-validation-to-a-separate-vsix"></a>Přidání ověření vrstev do samostatných VSIX  
  
1.  Vytvoření projektu knihovny tříd do nového nebo existujícího řešení sady Visual Studio. V **nový projekt** dialogové okno, klikněte na tlačítko **Visual C#** a pak klikněte na **knihovny tříd**. Tento projekt bude obsahovat třídu ověření vrstvy.  
  
2.  Identifikovat nebo vytvoření projektu VSIX ve vašem řešení. VSIX projekt obsahuje soubor s názvem **source.extension.vsixmanifest**. Pokud je nutné přidat projekt VSIX, postupujte takto:  
  
    1.  V **nový projekt** dialogovém okně vyberte **Visual C#**, **rozšiřitelnost**, **projektu VSIX**.  
  
    2.  V **Průzkumníku řešení**, v místní nabídce projektu VSIX **nastavit jako spouštěný projekt**.  
  
3.  V **source.extension.vsixmanifest**v části **prostředky**, přidejte projekt ověření vrstvy jako součást MEF:  
  
    1.  Zvolte **nové**.  
  
    2.  V **přidat nový prostředek** dialogové okno, sada:  
  
         **Type** = **Microsoft.VisualStudio.MefComponent**  
  
         **Zdroj** = **na projekt v aktuálním řešení**  
  
         **Projekt** = *validátoru projektu*  
  
4.  Musíte taky přidat ji jako ověření vrstev:  
  
    1.  Zvolte **nové**.  
  
    2.  V **přidat nový prostředek** dialogové okno, sada:  
  
         **Type** = **Microsoft.VisualStudio.ArchitectureTools.Layer.Validator**. To však není jednu z možností v rozevíracím seznamu. Je nutné zadat z klávesnice.  
  
         **Zdroj** = **na projekt v aktuálním řešení**  
  
         **Projekt** = *validátoru projektu*  
  
5.  Vraťte se do projektu ověření vrstvy a přidejte následující odkazy na projekt:  
  
    |**Referenční informace**|**Co můžete udělat**|  
    |-------------------|------------------------------------|  
    |Microsoft.VisualStudio.GraphModel.dll|Přečtěte si architektura grafu|  
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema.dll|Přečtěte si, že DOM kódu související s vrstvami|  
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.dll|Čtení modelu vrstvy|  
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility|Číst a aktualizovat tvarů a diagramů.|  
    |System.ComponentModel.Composition|Zadejte komponentu ověření pomocí Managed Extensibility Framework (MEF)|  
    |Microsoft.VisualStudio.Modeling.Sdk.[version]|Definujte rozšíření modelování|  
  
6.  Ukázkový kód na konci tohoto tématu zkopírujte do souboru třídy v projektu knihovny validátoru obsahuje kód pro vaše ověření. Další informace najdete v tématu [programování ověření](#programming).  
  
7.  K testování rozšíření, najdete v části [ladění ověření vrstev](#debugging).  
  
    > [!NOTE]
    >  Metodu bude volán jen v konkrétních případech a zarážky nebude fungovat automaticky. Další informace najdete v tématu [ladění ověření vrstev](#debugging).  
  
8.  Chcete-li nainstalovat VSIX hlavní instanci sady Visual Studio, nebo na jiném počítači, vyhledejte **VSIX** souboru v **bin** adresář projektu VSIX. Zkopírujte jej do počítače, ve které chcete nainstalovat VSIX. Poklikejte na soubor VSIX v Průzkumníku Windows.
  
     Chcete-li ho odinstalovat, použijte **rozšíření a aktualizace** na **nástroje** nabídky.  
  
##  <a name="programming"></a>Ověření programování  
 Můžete definovat rozšíření pro ověření vrstev, můžete definovat třídu, která má následující vlastnosti:  
  
-   Celkové formu deklaraci vypadá takto:  
  
    ```  
  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema;  
    using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;  
    using Microsoft.VisualStudio.GraphModel;  
    ...  
     [Export(typeof(IValidateArchitectureExtension))]  
      public partial class Validator1Extension :  
                      IValidateArchitectureExtension  
      {  
        public void ValidateArchitecture(Graph graph)  
        {  
           GraphSchema schema = graph.DocumentSchema;  
          ...  
      } }  
    ```  
  
-   Po zjištění k chybě, můžete ho sestavy pomocí `LogValidationError()`.  
  
    > [!WARNING]
    >  Nepoužívejte volitelné parametry `LogValidationError`.  
  
 Když uživatel vyvolá **ověření architektura** příkaz nabídky systému runtime vrstvy analýz vrstvy a jejich artefaktů k vytvoření grafu. Graf má čtyři části:  
  
-   Vrstvě modely řešení sady Visual Studio, které jsou reprezentovány jako uzly a odkazy v grafu.  
  
-   Kód, položky projektu a artefaktů, které jsou definovány v řešení a reprezentován jako uzly a odkazy, které představují závislosti zjištěné procesem analýzy.  
  
-   Odkazy z uzlů vrstvy na uzly artefaktů kódu.  
  
-   Uzly, které představují chyb zjištěných validátor.  
  
 -Li grafu byla vytvořená, se nazývá metoda standardní ověření. Po jejím dokončení, se nazývají žádné metody ověřování nainstalovaný rozšíření v neurčené pořadí. Grafu je předána na každý `ValidateArchitecture` metodu, která může kontrola grafu a zprávy o chybách, které nalezne.  
  
> [!NOTE]
>  To však není stejný jako proces ověření, které je možné v jazycích specifické pro doménu.  
  
 Metody ověřování nesmí změnit model vrstvy nebo kód, který je ověřován.  
  
 Graf modelu je definována v <xref:Microsoft.VisualStudio.GraphModel>. Jsou jeho hlavní třídy <xref:Microsoft.VisualStudio.GraphModel.GraphNode> a <xref:Microsoft.VisualStudio.GraphModel.GraphLink>.  
  
 Každý uzel a každý odkaz obsahuje jednu nebo více kategorií, které určují typ elementu nebo vztah, který reprezentuje. Uzly typické grafu mají následujících kategorií:  
  
-   Dsl.LayerModel  
  
-   Dsl.Layer  
  
-   Dsl.Reference  
  
-   CodeSchema_Type  
  
-   CodeSchema_Namespace  
  
-   CodeSchema_Type  
  
-   CodeSchema_Method  
  
-   CodeSchema_Field  
  
-   CodeSchema_Property  
  
 Odkazy z vrstvy na elementy v kódu mají kategorii "Představuje".  
  
##  <a name="debugging"></a>Ladění ověření  
 Chcete-li ladit ověření rozšíření vrstvy, stiskněte CTRL + F5. Otevře se experimentální instanci sady Visual Studio. V tomto případě otevřít nebo vytvořit model vrstvy. Tento model musí být přidružený kód a musí mít alespoň jeden závislostí.  
  
### <a name="test-with-a-solution-that-contains-dependencies"></a>Testování pomocí řešení, které obsahuje závislosti  
 Ověření není proveden, pokud jsou k dispozici následující vlastnosti:  
  
-   Na diagramu závislostí je alespoň jeden odkaz závislostí.  
  
-   Existují vrstvy v modelu, které jsou přidružené elementy kódu.  
  
 Při prvním spuštění experimentální instanci sady Visual Studio k testování ověření rozšíření, otevřete nebo vytvářet řešení, která má tyto vlastnosti.  
  
### <a name="run-clean-solution-before-validate-architecture"></a>Spuštění Vyčistit řešení před ověření architektura  
 Při každé aktualizaci ověřovacího kódu pomocí **Vyčistit řešení** příkaz na **sestavení** nabídky v experimentální řešení, před testovacího příkaz ověřením. To je nezbytné, protože v mezipaměti výsledky ověření. Pokud jste neprovedli aktualizaci diagramu testovací závislostí nebo jeho kód, nebude provedeno metody ověřování.  
  
### <a name="launch-the-debugger-explicitly"></a>Explicitně spuštění ladicího programu  
 Ověření se spustí jako samostatný proces. Proto nebude aktivována zarážky v metodu ověření. Ladicí program musí explicitně připojit k procesu, když ověření bylo zahájeno.  
  
 Připojit ladicí program k procesu ověřování, Vložit volání `System.Diagnostics.Debugger.Launch()` na začátku metodu ověření. Když se zobrazí dialogové okno ladění, vyberte hlavní instanci sady Visual Studio.  
  
 Alternativně můžete vložit volání `System.Windows.Forms.MessageBox.Show()`. Jakmile se zobrazí okno se zprávou, přejděte k hlavní instanci sady Visual Studio a na **ladění** nabídce klikněte na tlačítko **připojit k procesu**. Vyberte proces, který je pojmenován **Graphcmd.exe**.  
  
 Vždy spustit experimentální instanci stisknutím CTRL + F5 (**spustit bez ladění**).  
  
### <a name="deploying-a-validation-extension"></a>Nasazení rozšíření ověření  
 K instalaci rozšíření ověření v počítači, na kterém je nainstalován vhodný verze sady Visual Studio, otevřete soubor VSIX na cílovém počítači. K instalaci na počítači, na který [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] je nainstalován, je nutné ručně extrahovat VSIX obsah do složky rozšíření. Další informace najdete v tématu [nasazení rozšíření pro modelování vrstev](../modeling/deploy-a-layer-model-extension.md).  
  
##  <a name="example"></a>Příklad kódu  
  
```csharp  
using System;  
using System.ComponentModel.Composition;  
using System.Globalization;  
using System.Linq;  
using System.Text.RegularExpressions;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;  
using Microsoft.VisualStudio.GraphModel;  
  
namespace Validator3  
{  
    [Export(typeof(IValidateArchitectureExtension))]  
    public partial class Validator3Extension : IValidateArchitectureExtension  
    {  
        /// <summary>  
        /// Validate the architecture  
        /// </summary>  
        /// <param name="graph">The graph</param>  
        public void ValidateArchitecture(Graph graph)  
        {  
            if (graph == null) throw new ArgumentNullException("graph");  
  
            // Uncomment the line below to debug this extension during validation  
            // System.Windows.Forms.MessageBox.Show("Attach 2 to GraphCmd.exe with process id " + System.Diagnostics.Process.GetCurrentProcess().Id);  
  
            // Get all layers on the diagram  
            foreach (GraphNode layer in graph.Nodes.GetByCategory("Dsl.Layer"))  
            {  
                System.Threading.Thread.Sleep(100);  
                // Get the required regex property from the layer node  
                string regexPattern = "^[a-zA-Z]+$"; //layer[customPropertyCategory] as string;  
                if (!string.IsNullOrEmpty(regexPattern))  
                {  
                    Regex regEx = new Regex(regexPattern);  
  
                    // Get all referenced types in this layer including those from nested layers so each  
                    // type is validated against all containing layer constraints.  
                    foreach (GraphNode containedType in layer.FindDescendants().Where(node => node.HasCategory("CodeSchema_Type")))  
                    {  
                        // Check the type name against the required regex                          
                        CodeGraphNodeIdBuilder builder = new CodeGraphNodeIdBuilder(containedType.Id, graph);  
                        string typeName = builder.Type.Name;  
                        if (!regEx.IsMatch(typeName))  
                        {  
                            // Log an error  
                            string message = string.Format(CultureInfo.CurrentCulture, Resources.InvalidTypeNameMessage, typeName);  
                            this.LogValidationError(graph, typeName + "TypeNameError", message, GraphErrorLevel.Error, layer);  
                        }  
                    }  
                }  
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření diagramů závislostí](../modeling/extend-layer-diagrams.md)
