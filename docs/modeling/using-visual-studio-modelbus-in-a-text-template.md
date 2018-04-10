---
title: V sadě Visual Studio ModelBus textové šablony | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0184e3b543e509d0e523504c0ea07f6fcc36775f
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="using-visual-studio-modelbus-in-a-text-template"></a>Použití prvku Visual Studio ModelBus v textové šabloně
Pokud píšete textové šablony, které čtou model, který obsahuje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus odkazuje, můžete chtít vyřešte reference pro přístup k cílové modelů. V takovém případě je nutné přizpůsobit textové šablony a odkazované jazyky specifické pro doménu (DSL, linky):  
  
-   DSL, který je cílem odkazy musí mít ModelBus adaptér, který je nakonfigurovaný pro přístup z textové šablony. Pokud máte také přístup k DSL z jiný kód, je třeba kromě standardní adaptér ModelBus změněnou konfigurací adaptéru.  
  
     Správce adaptéru musí dědit z <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager> a musí mít atribut `[HostSpecific(HostName)]`.  
  
-   Šablona musí dědit z <xref:Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation>.  
  
> [!NOTE]
>  Pokud chcete číst DSL modely, které neobsahují ModelBus odkazy, můžete direktivy procesorů, které jsou generovány v DSL projekty. Další informace najdete v tématu [přístup k modely z textové šablony](../modeling/accessing-models-from-text-templates.md).  
  
 Další informace o textové šablony najdete v tématu [vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md).  
  
## <a name="creating-a-model-bus-adapter-for-access-from-text-templates"></a>Vytvoření modelu sběrnice adaptéru pro přístup z textové šablony  
 Vyřešit ModelBus odkaz v textové šablony, musí mít cílový DSL kompatibilní adaptéru. Textové šablony provést v samostatné doméně AppDomain z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dokumentu editory, a proto musí načíst model ne přístup prostřednictvím DTE adaptéru.  
  
#### <a name="to-create-a-modelbus-adapter-that-is-compatible-with-text-templates"></a>Chcete-li vytvořit ModelBus adaptér, který je kompatibilní s textové šablony  
  
1.  Pokud nemá cíl DSL řešení **ModelBusAdapter** projektu, vytvořte ji pomocí Průvodce Modelbus rozšíření:  
  
    1.  Stáhněte a nainstalujte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus rozšíření, pokud jste to ještě neudělali. Další informace najdete v tématu [vizualizace a modelování SDK](http://go.microsoft.com/fwlink/?LinkID=185579).  
  
    2.  Otevřete soubor definice DSL. Klikněte pravým tlačítkem na návrhovou plochu a potom klikněte na **povolit Modelbus**.  
  
    3.  V dialogovém okně vyberte **chcete zpřístupnit tento DSL k ModelBus**. Obě možnosti můžete vybrat, pokud chcete tento DSL vystavit její modely i využívat odkazy na další DSL, linky.  
  
    4.  Click **OK**. Nový projekt "ModelBusAdapter" je přidán do DSL řešení.  
  
    5.  Klikněte na tlačítko **proveďte transformaci všech šablon**.  
  
    6.  Znovu sestavte řešení.  
  
2.  Pokud chcete získat přístup DSL z textové šablony i z jiných kódu, třeba příkaz, duplicitní **ModelBusAdapter** projektu:  
  
    1.  V Průzkumníku Windows, zkopírujte a vložte složky, která obsahuje **ModelBusAdapter.csproj**.  
  
    2.  Přejmenujte soubor projektu (například k **T4ModelBusAdapter.csproj**).  
  
    3.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení, přejděte na **přidat**a potom klikněte na **existující projekt**. Vyhledejte nový projekt adaptér **T4ModelBusAdapter.csproj**.  
  
    4.  V každé `*.tt` souboru nového projektu změnit obor názvů.  
  
    5.  Nový projekt v Průzkumníku řešení klikněte pravým tlačítkem myši a potom klikněte na položku Vlastnosti. V editoru vlastnosti změňte názvy generované sestavení a výchozí obor názvů.  
  
    6.  V projektu DslPackage přidáte odkaz na nový projekt adaptéru tak, aby měl odkazy na obou adaptérů.  
  
    7.  V DslPackage\source.extension.tt přidejte řádek, který odkazuje na nový projekt adaptéru.  
  
        ```  
        <MefComponent>|T4ModelBusAdapter|</MefComponent>  
        ```  
  
    8.  **Proveďte transformaci všech šablon** a znovu sestavte řešení. Měli nevyskytnou žádné chyby sestavení.  
  
3.  V novém projektu adaptér přidejte odkazy na následující:  
  
    -   Microsoft.VisualStudio.TextTemplating.11.0  
  
         Microsoft.VisualStudio.TextTemplating.Modeling.11.0  
  
4.  In AdapterManager.tt:  
  
    -   Změňte deklaraci AdapterManagerBase tak, aby dědila z <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>.  
  
         `public partial class <#= dslName =>AdapterManagerBase :`  
  
         `Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager { ...`  
  
    -   U konce souboru nahraďte atribut HostSpecific před AdapterManager třídy. Odeberte následující řádek:  
  
         `[DslIntegration::HostSpecific(DslIntegrationShell::VsModelingAdapterManager.HostName)]`  
  
         Vložte následující řádek:  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
         Tento atribut filtruje sada adaptérů, která je dostupná, když příjemce modelbus hledá adaptér.  
  
5.  **Proveďte transformaci všech šablon** a znovu sestavte řešení. Měli nevyskytnou žádné chyby sestavení.  
  
## <a name="writing-a-text-template-that-can-resolve-modelbus-references"></a>Zápis textové šablony, která může vyřešit ModelBus odkazy  
 Obvykle byste začít se šablonou, která čte a generuje soubory z "zdroje" DSL. Tato šablona používá direktiva, generovaný v projektu DSL zdroj číst zdrojové soubory modelu způsobem, který je popsán v [přístup k modely z textové šablony](../modeling/accessing-models-from-text-templates.md). Zdroj DSL však obsahuje ModelBus odkazy na "target" DSL. Proto je chcete povolit kód šablony vyřešit odkazy a přístup k cíli DSL. Proto musí přizpůsobit šablonu pomocí následujících kroků:  
  
-   Změňte základní třídu pro šablonu <xref:Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation>.  
  
-   Zahrnout `hostspecific="true"` v – direktiva šablony.  
  
-   Cíl DSL a jeho adaptéru a povolit ModelBus, přidejte odkazy na sestavení.  
  
-   Direktiva, generovaný v rámci cíle DSL nepotřebujete.  
  
```  
<#@ template debug="true" hostspecific="true" language="C#"  
inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>   
<#@ SourceDsl processor="SourceDslDirectiveProcessor" requires="fileName='Sample.source'" #>  
<#@ output extension=".txt" #>  
<#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>  
<#@ assembly name = "Company.TargetDsl.Dsl.dll" #>  
<#@ assembly name = "Company.TargetDsl.T4ModelBusAdapter.dll" #>  
<#@ assembly name = "System.Core" #>  
<#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>  
<#@ import namespace="Company.TargetDsl" #>  
<#@ import namespace="Company.TargetDsl.T4ModelBusAdapters" #>  
<#@ import namespace="System.Linq" #>  
<#  
  SourceModelRoot source = this.ModelRoot; // Usual access to source model.  
  // In the source DSL Definition, the root element has a model reference:  
  using (TargetAdapter adapter = this.ModelBus.CreateAdapter(source.ModelReference) as TargetAdapter)   
  {if (adapter != null)  
   {  
      // Get the root of the target model:  
      TargetRoot target = adapter.ModelRoot;  
    // The source DSL Definition has a class "SourceElement" embedded under the root.  
    // (Let's assume they're all in the same model file):  
    foreach (SourceElement sourceElement in source.Elements)  
    {  
      // In the source DSL Definition, each SourceElement has a MBR property:  
      ModelBusReference elementReference = sourceElement.ReferenceToTarget;  
      // Resolve the target model element:   
      TargetElement element = adapter.ResolveElementReference<TargetElement>(elementReference);   
#>  
     The source <#= sourceElement.Name #> is linked to: <#= element.Name #> in target model: <#= target.Name #>.  
<#  
    }  
  }}  
  // Other useful code: this.Host.ResolvePath(filename) gets an absolute filename   
  // from a path that is relative to the text template.  
#>  
  
```  
  
 Po provedení této šablony text `SourceDsl` – direktiva načte soubor `Sample.source`. Šablony můžete přístup k elementům tohoto modelu, od `this.ModelRoot`. Kód můžete použít domény třídy a vlastnosti tohoto DSL.  
  
 Kromě toho můžete šablony vyřešit ModelBus odkazy. Kde odkazy odkazoval na cílovému modelu, umožní direktivy sestavení kód domény třídy a vlastnosti DSL tohoto modelu.  
  
-   Pokud nepoužijete direktivu, který je generovaný projektu DSL, měli byste také zahrnout následující.  
  
    ```  
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.11.0" #>  
    <#@ assembly name = "Microsoft.VisualStudio.TextTemplating.Modeling.11.0" #>  
    ```  
  
-   Použití `this.ModelBus` se získat přístup k ModelBus.  
  
## <a name="walkthrough-testing-a-text-template-that-uses-modelbus"></a>Návod: Testování Text šablony, která používá ModelBus  
 V tomto návodu postupujte takto:  
  
1.  Vytvořte dvě DSL, linky. Jeden DSL *příjemce*, má `ModelBusReference` vlastnost, která mohou odkazovat na jiné DSL *zprostředkovatele*.  
  
2.  Vytvořte dva adaptéry ModelBus ve zprostředkovateli: jeden pro přístup pomocí textových šablon, druhý pro běžné kód.  
  
3.  Vytvořte instanci modely DSL, linky v jednom experimentální projektu.  
  
4.  Nastaví vlastnost domény v jednom modelu tak, aby odkazoval na jiný model.  
  
5.  Poklikejte na soubor obslužné rutiny, které se otevře model, který ukazuje zápisu  
  
6.  Zápis textu šablonu, která může načíst první model, použijte odkaz na jiný model a čtení jiný model.  
  
#### <a name="construct-a-dsl-that-is-accessible-to-modelbus"></a>Konstrukce DSL, které je přístupné pro ModelBus  
  
1.  Vytvořte nové řešení DSL. V tomto příkladu vyberte šablonu řešení tok úkolů. Nastavte název jazyka `MBProvider` a příponu názvu souboru do ".provide".  
  
2.  V diagramu definice DSL, klikněte pravým tlačítkem myši na prázdnou část diagram, který není v horní a pak klikněte na tlačítko **povolit Modelbus**.  
  
    -   Pokud se nezobrazí **povolit Modelbus**, musíte stáhnout a nainstalovat rozšíření VMSDK ModelBus. Najít na webu VMSDK: [vizualizace a modelování SDK](http://go.microsoft.com/fwlink/?LinkID=185579).  
  
3.  V **povolit Modelbus** dialogové okno, vyberte **vystavit tento DSL k ModelBus**a potom klikněte na **OK**.  
  
     Nový projekt, `ModelBusAdapter`, se přidá do řešení.  
  
 Nyní máte DSL, který je přístupný pomocí textových šablon pomocí ModelBus. V kódu příkazy, obslužné rutiny událostí nebo pravidla pro všechny z nich pracovat v objektu třídy AppDomain editoru soubor modelu lze vyřešit na ni odkazují. Textové šablony ale spustit v samostatné doméně AppDomain a nemůžou přistupovat model je upravována. Pokud chcete pro přístup k ModelBus odkazy na tento DSL z textové šablony, musíte mít samostatné ModelBusAdapter.  
  
#### <a name="to-create-a-modelbus-adapter-that-is-configured-for-text-templates"></a>Chcete-li vytvořit ModelBus adaptér, který je nakonfigurován pro textové šablony  
  
1.  V Průzkumníku Windows zkopírujte a vložte složky, která obsahuje ModelBusAdapter.csproj.  
  
     Název složky T4ModelBusAdapter.  
  
     Přejmenujte soubor projektu T4ModelBusAdapter.csproj.  
  
2.  V Průzkumníku řešení přidejte T4ModelBusAdapter MBProvider řešení. Klikněte pravým tlačítkem na uzel řešení, přejděte na **přidat**a potom klikněte na **existující projekt**.  
  
3.  Klikněte pravým tlačítkem na uzel projektu T4ModelBusAdapter a pak klikněte na položku Vlastnosti. V okně Vlastnosti projektu změnit **název sestavení** a **výchozí Namespace** k `Company.MBProvider.T4ModelBusAdapters`.  
  
4.  Do každého souboru *.tt v T4ModelBusAdapter insert "T4" poslední část oboru názvů, tak, aby se podobá následující řádek.  
  
     `namespace <#= CodeGenerationUtilities.GetPackageNamespace(this.Dsl) #>.T4ModelBusAdapters`  
  
5.  V `DslPackage` projekt, přidejte odkaz na projekt `T4ModelBusAdapter`.  
  
6.  V DslPackage\source.extension.tt, přidejte následující řádek v části `<Content>`.  
  
     `<MefComponent>|T4ModelBusAdapter|</MefComponent>`  
  
7.  V `T4ModelBusAdapter` projekt, přidejte odkaz na: **Microsoft.VisualStudio.TextTemplating.Modeling.11.0**  
  
8.  Open T4ModelBusAdapter\AdapterManager.tt:  
  
    1.  Změňte základní třídu AdapterManagerBase k <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>. Tato část souboru, teď vypadá přibližně takto.  
  
        ```  
        namespace <#= CodeGenerationUtilities.GetPackageNamespace(this.Dsl) #>.T4ModelBusAdapters  
        {  
            /// <summary>  
            /// Adapter manager base class (double derived pattern) for the <#= dslName #> Designer  
            /// </summary>  
            public partial class <#= dslName #>AdapterManagerBase   
            : Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager  
            {  
  
        ```  
  
    2.  U konce souboru vložte následující další atribut před třída AdapterManager.  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
         Výsledek vypadá přibližně takto.  
  
        ```  
        /// <summary>  
        /// ModelBus modeling adapter manager for a <#= dslName #>Adapter model adapter  
        /// </summary>  
        [Mef::Export(typeof(DslIntegration::ModelBusAdapterManager))]  
        [Mef::ExportMetadata(DslIntegration::CompositionAttributes.AdapterIdKey,<#= dslName #>Adapter.AdapterId)]  
        [DslIntegration::HostSpecific(DslIntegrationShell::VsModelingAdapterManager.HostName)]  
        [Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]  
        public partial class <#= dslName #>AdapterManager : <#= dslName #>AdapterManagerBase  
        {  
        }  
  
        ```  
  
9. Klikněte na tlačítko **transformaci všech šablon** v nadpisu řádku z Průzkumníku řešení.  
  
10. Znovu sestavte řešení. Klikněte na tlačítko F5.  
  
11. Ověřte, zda DSL funguje stisknutím klávesy F5. Otevřete v projektu experimentální `Sample.provider`. Ukončete experimentální instance [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 ModelBus odkazy na tento DSL lze vyřešit nyní v textových šablonách a také v obyčejnou kódu.  
  
#### <a name="construct-a-dsl-with-a-modelbus-reference-domain-property"></a>Konstrukce DSL s vlastností domény ModelBus odkaz  
  
1.  Vytvoření nové DSL pomocí šablony řešení minimální jazyk. Název jazyka MBConsumer a nastavit příponu názvu souboru do ".consume".  
  
2.  V projektu DSL přidáte odkaz na sestavení MBProvider DSL. Klikněte pravým tlačítkem na `MBConsumer\Dsl\References` a pak klikněte na **přidat odkaz na**. V **Procházet** najděte `MBProvider\Dsl\bin\Debug\Company.MBProvider.Dsl.dll`  
  
     To umožňuje vytvářet kód, který používá jiné DSL. Pokud chcete vytvořit odkazy na několik DSL, linky, přidejte je také.  
  
3.  Definice DSL diagramu, klikněte pravým tlačítkem na diagramu a pak klikněte na **povolit ModelBus**. V dialogovém okně vyberte **povolit tento DSL využívat ModelBus**.  
  
4.  Ve třídě `ExampleElement`, přidejte novou vlastnost domény `MBR`a v okně vlastností nastavte její typ na `ModelBusReference`.  
  
5.  Vlastnost domain v diagramu pravým tlačítkem a pak klikněte na **specifické vlastnosti upravit ModelBusReference**. V dialogovém okně vyberte **element modelu**.  
  
     Nastavte dialogové okno Filtr souborů na následující.  
  
     `Provider File|*.provide`  
  
     Dílčí řetězec po "&#124;" je filtr pro dialogové okno pro výběr souboru. Můžete ji povolit všechny soubory s použitím nastavit *.\*  
  
     V **typ elementu modelu** seznamu, zadejte názvy jedné nebo více domény třídy ve zprostředkovateli DSL (například Company.MBProvider.Task). Může se jednat abstraktní třídy. Pokud seznam nezadáte, může uživatel nastavit odkaz na libovolný element.  
  
6.  Zavřete dialogové okno a **transformaci všech šablon**.  
  
 Vytvořili jste DSL, která může obsahovat odkazy na elementy v jiné DSL.  
  
#### <a name="create-a-modelbus-reference-to-another-file-in-the-solution"></a>Vytvoření ModelBus odkaz na jiný soubor v řešení  
  
1.  V řešení MBConsumer stiskněte CTRL + F5. Experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] se otevře v **MBConsumer\Debugging** projektu.  
  
2.  Přidat kopii Sample.provide k **MBConsumer\Debugging** projektu. To je nezbytné, protože odkaz ModelBus musí odkazovat na soubor ve stejném řešení.  
  
    1.  Klikněte pravým tlačítkem na projekt ladění, přejděte na **přidat**a potom klikněte na **existující položka**.  
  
    2.  V **přidat položku** dialogové okno, nastavte filtr **všechny soubory (\*.\*)** .  
  
    3.  Přejděte na `MBProvider\Debugging\Sample.provide` a pak klikněte na **přidat**.  
  
3.  Otevřete `Sample.consume`.  
  
4.  Klikněte na jeden příklad tvar a v okně vlastností klikněte na tlačítko **[...]**  ve vlastnosti MBR. V dialogovém okně klikněte na **Procházet** a vyberte `Sample.provide`. V okně elementy typu úloh rozbalte a vyberte jeden z elementů.  
  
5.  Uložte soubor.  
  
     (Zatím nezavírejte experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].)  
  
 Vytvořili jste model, který obsahuje ModelBus odkaz na element v jiného modelu.  
  
#### <a name="resolve-a-modelbus-reference-in-a-text-template"></a>Vyřešit ModelBus odkaz v textové šablony  
  
1.  V experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otevřete šablonu ukázkový textový soubor. Nastavte jeho obsah následujícím způsobem.  
  
    ```  
    <#@ template debug="true" hostspecific="true" language="C#"  
    inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>   
    <#@ MBConsumer processor="MBConsumerDirectiveProcessor" requires="fileName='Sample.consume'" #>  
    <#@ output extension=".txt" #>  
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>  
    <#@ assembly name = "Company.MBProvider.Dsl.dll" #>  
    <#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>  
    <#@ import namespace="Company.MBProvider" #>  
    <#  
      // Property provided by the Consumer directive processor:  
      ExampleModel consumerModel = this.ExampleModel;   
      // Iterate through Consumer model, listing the elements:  
      foreach (ExampleElement element in consumerModel.Elements)  
      {  
    #>  
       <#= element.Name #>   
    <#  
        if (element.MBR != null)  
      using (ModelBusAdapter adapter = this.ModelBus.CreateAdapter(element.MBR))  
      {   
              // If we allowed multiple types or DSLs in the MBR, discover type here.  
        Task task = adapter.ResolveElementReference<Task>(element.MBR);  
    #>  
            <#= element.Name #> is linked to Task: <#= task==null ? "(null)" : task.Name #>  
    <#  
          }  
      }  
    #>  
  
    ```  
  
     Všimněte si následující body:  
  
    1.  `hostSpecific` a `inherits` atributy `template` – direktiva musí být nastavena.  
  
    2.  Model příjemce přistupuje prostřednictvím procesoru direktiv, který byl vytvořen v tomto DSL obvyklým způsobem.  
  
    3.  Direktivy jazyka sestavení a import musí být schopen přístup k ModelBus a typy zprostředkovatele DSL.  
  
    4.  Pokud víte, že mnoho MBRs jsou spojeny s stejného modelu, je lepší CreateAdapter volat pouze jednou.  
  
2.  Uložte šablonu. Ověřte, že bude výsledný soubor text vypadá přibližně takto.  
  
    ```  
  
    ExampleElement1   
    ExampleElement2   
         ExampleElement2 is linked to Task: Task2  
  
    ```  
  
#### <a name="resolve-a-modelbus-reference-in-a-gesture-handler"></a>Vyřešit ModelBus odkaz v obslužné rutiny gest  
  
1.  Ukončete experimentální instance [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], pokud je spuštěn.  
  
2.  Přidejte soubor, který je s názvem MBConsumer\Dsl\Custom.cs a nastavit jeho obsah následujícím.  
  
    ```  
  
    namespace Company.MB2Consume  
    {  
      using Microsoft.VisualStudio.Modeling.Integration;  
      using Company.MB3Provider;  
  
      public partial class ExampleShape  
      {  
        public override void OnDoubleClick(Microsoft.VisualStudio.Modeling.Diagrams.DiagramPointEventArgs e)  
        {  
          base.OnDoubleClick(e);  
          ExampleElement element = this.ModelElement as ExampleElement;  
          if (element.MBR != null)  
          {  
            IModelBus modelbus = this.Store.GetService(typeof(SModelBus)) as IModelBus;  
            using (ModelBusAdapter adapter = modelbus.CreateAdapter(element.MBR))  
            {  
              Task task = adapter.ResolveElementReference<Task>(element.MBR);  
              // Open a window on this model:  
              ModelBusView view = adapter.GetDefaultView();  
              view.Show();  
              view.SetSelection(element.MBR);  
            }  
          }  
        }  
      }  
    }  
  
    ```  
  
3.  Stisknutím klávesy CTRL + F5.  
  
4.  V experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otevřete `Debugging\Sample.consume`.  
  
5.  Dvakrát klikněte na jednu tvaru.  
  
     Pokud nastavíte hlavní spouštěcí záznam pro tento element otevře odkazovaný model a je odkazovaný element je vybrán.  
  
## <a name="see-also"></a>Viz také  
 [Integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [Vytvoření kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
