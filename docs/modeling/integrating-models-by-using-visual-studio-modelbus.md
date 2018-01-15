---
title: "Integrace modelů pomocí Visual Studio Modelbus | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e590b0b0451864c69d548bb643ed4e915f08ad96
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="integrating-models-by-using-visual-studio-modelbus"></a>Integrace modelů pomocí Visual Studio Modelbus
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ModelBus poskytuje metodu pro vytváření odkazů mezi modely a z dalších nástrojů do modelů. Můžete například propojit modely jazyka domény (DSL) a modely UML. Můžete vytvořit integrované sadu DSL, linky.  
  
 ModelBus umožňuje vytvořit jedinečný odkaz na modelu nebo na konkrétní prvku v modelu. Tento odkaz může být uložená mimo modelu, například v elementu v jiného modelu. Když při novější příležitosti nástroj chce získat přístup k elementu, bude infrastruktury modelu sběrnice spouštění na odpovídající model a vrátí element. Pokud chcete, můžete zobrazit modelu pro uživatele. Pokud soubor nelze použít v jeho předchozí umístění, bude ModelBus požádat uživatele, aby ji najít. Pokud uživatel vyhledá soubor, ModelBus opraví všechny odkazy na tento soubor.  
  
> [!NOTE]
>  V aktuálním [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] implementace ModelBus, propojené modely musí být ve stejné položky [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení.  
  
 Další informace a ukázky kódu najdete v tématu:  
  
-   [Postupy: Přidání obslužné rutiny operace přetažení myší](../modeling/how-to-add-a-drag-and-drop-handler.md)  
  
-   [Modelování SDK pro Visual Studio](http://www.microsoft.com/download/details.aspx?id=40754)  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
  
##  <a name="provide"></a>Zajištění přístupu k DSL  
 Před vytvořením ModelBus odkazy na model nebo jeho prvky, je nutné zadat ModelBusAdapter pro DSL. Nejjednodušším způsobem je použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] přípony sběrnice modelu, který přidá příkazy do DSL návrháře.  
  
###  <a name="expose"></a>Aby se zveřejnily definici DSL sběrnice modelu  
  
1.  Stáhnout a nainstalovat rozšíření pro Visual Studio modelu sběrnice, pokud jste ho už nainstalovali. Další informace najdete v tématu [vizualizace a modelování SDK](http://go.microsoft.com/fwlink/?LinkID=185579).  
  
2.  Otevřete soubor definice DSL. Klikněte pravým tlačítkem na návrhovou plochu a potom klikněte na **povolit Modelbus**.  
  
3.  V dialogovém okně vyberte **chcete zpřístupnit tento DSL k ModelBus**. Pokud chcete tento DSL vystavit její modely i využívat odkazy na další DSL, linky, můžete obě možnosti.  
  
4.  Click **OK**. Nový projekt "ModelBusAdapter" je přidán do DSL řešení.  
  
5.  Pokud chcete získat přístup DSL z textové šablony, je třeba upravit AdapterManager.tt v novém projektu. Tento krok vynechte, pokud chcete získat přístup DSL z jiný kód, jako je například příkazy a obslužné rutiny událostí. Další informace najdete v tématu [pomocí Visual Studio ModelBus v textové šablony](../modeling/using-visual-studio-modelbus-in-a-text-template.md).  
  
    1.  Změňte základní třídu AdapterManagerBase k <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>.  
  
    2.  U konce souboru vložte tento další atribut před třída AdapterManager:  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
    3.  V projektu odkazy ModelBusAdapter přidat **Microsoft.VisualStudio.TextTemplating.Modeling.11.0**.  
  
     Pokud chcete získat přístup DSL z textové šablony i z jiných kódu, je třeba dva adaptéry, jeden upravit a jeden ponechat beze změny.  
  
6.  Klikněte na tlačítko **proveďte transformaci všech šablon**.  
  
7.  Znovu sestavte řešení.  
  
 Je nyní možné pro ModelBus otevřete instance této DSL.  
  
 Složka `ModelBusAdapters\bin\*` obsahuje sestavení vytvořené `Dsl` projektu a `ModelBusAdapters` projektu. Chcete-li tento DSL z jiné DSL, měli byste importovat tyto sestavení.  
  
### <a name="making-sure-that-elements-can-be-referenced"></a>A ujistěte se, že může být odkazováno elementy  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Adaptéry ModelBus použijte identifikátor guid elementu k určení, ve výchozím nastavení. Tyto identifikátory musí zachovat proto v souboru modelu.  
  
##### <a name="to-ensure-that-element-ids-are-persisted"></a>Zajistit, že element jsou nastavené jako trvalé ID  
  
1.  Otevřete DslDefinition.dsl.  
  
2.  V Průzkumníku DSL rozbalte **chování serializace Xml**, pak **Data třídy**.  
  
3.  Pro každou třídu, ke které chcete vytvořit Model sběrnice odkazuje:  
  
     Klikněte na uzel třídy a v okně Vlastnosti zkontrolujte, zda **serializovat Id** je nastaven na `true`.  
  
 Případně pokud chcete použít k identifikaci elementy místo identifikátory GUID názvy elementů, můžete přepsat částí generovaného adaptéry. Přepište následující metody ve třídě adaptéru:  
  
-   Přepsání `GetElementId` vrátit identifikátor, který chcete použít. Tato metoda je volána při vytváření odkazů.  
  
-   Přepsání `ResolveElementReference` najít správný element ze sběrnice modelu odkaz.  
  
##  <a name="editRef"></a>Přístup k DSL z jiné DSL  
 Můžete uložit model sběrnice odkazy ve vlastnosti domény v DSL, a můžete napsat vlastní kód, který používá je. Můžete taky umožnit uživatel může vytvořit odkaz na sběrnici modelu výběrem soubor modelu a element v něm.  
  
 K povolení DSL použití odkazů na jiné DSL, měli byste nejdřív si ho *příjemce* modelu sběrnice odkazy.  
  
#### <a name="to-enable-a-dsl-to-consume-references-to-an-exposed-dsl"></a>Chcete-li povolit DSL používat odkazy zveřejněné DSL  
  
1.  Definice DSL diagramu, klikněte pravým tlačítkem na hlavní část diagramu a pak klikněte na **povolit Modelbus**.  
  
2.  V dialogovém okně vyberte **povolení tohoto modelu využívat model sběrnice odkazy**.  
  
3.  V projektu Dsl náročné DSL přidejte následující sestavení do odkazů projektu. Tyto sestavení (soubory .dll) najdete v ModelBusAdapter\bin\\* adresář zveřejněné DSL.  
  
    -   Zveřejněné sestavení DSL, například **Fabrikam.FamilyTree.Dsl.dll**  
  
    -   Model zveřejněné sběrnici adaptér sestavení, například **Fabrikam.FamilyTree.ModelBusAdapter.dll**  
  
4.  Přidejte následující sestavení .NET do odkazů projektu náročné DSL projektu.  
  
    1.  **Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0.dll**  
  
    2.  **Microsoft.VisualStudio.Modeling.Sdk.Integration.Shell.11.0.dll**  
  
#### <a name="to-store-a-model-bus-reference-in-a-domain-property"></a>K uložení odkazu sběrnice modelu do vlastnosti domény  
  
1.  V definici DSL náročné DSL přidejte vlastnost domain na třídu domény a nastavte její název.  
  
2.  Ve vlastnostech s vlastností domény vybrána, nastavte **typ** k `ModelBusReference`.  
  
 V této fázi kód programu můžete nastavit hodnotu vlastnosti, ale je jen pro čtení v okně Vlastnosti.  
  
 Můžete povolit uživatelům nastavit vlastnost s specializované editor odkaz ModelBus. Existují dvě verze tohoto editoru nebo *výběr:* jeden umožňuje uživatelům zvolit soubor modelu a dalších umožňuje uživatelům zvolit soubor modelu a element v modelu.  
  
#### <a name="to-allow-the-user-to-set-a-model-bus-reference-in-a-domain-property"></a>Umožňuje uživateli nastavit odkaz na sběrnici modelu do vlastnosti domény  
  
1.  Vlastnost domain klikněte pravým tlačítkem a pak klikněte na tlačítko **specifické vlastnosti upravit ModelBusReference**. Otevře dialogové okno. Toto je *modelu sběrnice výběr*.  
  
2.  Vyberte odpovídající **druh ModelBusReference**: k modelu, nebo pro element v modelu.  
  
3.  V souboru řetězec filtru dialogové okno, zadejte řetězec `Family Tree files |*.ftree`. Nahraďte váš zveřejněné DSL přípona souboru.  
  
4.  Pokud jste se rozhodli odkazovat na prvek v modelu, můžete přidat seznam typů, které můžete vybrat uživatele, například Company.FamilyTree.Person.  
  
5.  Klikněte na tlačítko **OK**a potom klikněte na **transformaci všech šablon** na panelu nástrojů Průzkumníka řešení.  
  
    > [!WARNING]
    >  Pokud nevyberete platný model nebo entity, na tlačítko OK budou mít žádný vliv, i když se může objevit povoleno.  
  
6.  Pokud zadáte seznam typy cíle například Company.FamilyTree.Person, pak musíte přidat odkaz na sestavení do projektu DSL odkazující na knihovnu DLL cíle DSL, například Company.FamilyTree.Dsl.dll  
  
#### <a name="to-test-a-model-bus-reference"></a>K testování odkaz sběrnice modelu  
  
1.  Vytvořte i zveřejněné a náročné DSL, linky.  
  
2.  Spusťte jeden z DSL, linky experimentální režimu stisknutím klávesy F5 nebo CTRL + F5.  
  
3.  V projektu ladění experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], přidejte soubory, které jsou instancemi třídy každý DSL.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ModelBus můžete řešit pouze odkazy na modely, které jsou položky ve stejné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení. Odkaz na soubor modelu nelze například vytvořit v jiné části systému souborů.  
  
4.  Umožňuje vytvořit některé prvky a odkazy v instanci zveřejněné DSL a uložte jej.  
  
5.  Otevřete instanci náročné DSL a vyberte modelu element, který má odkaz na vlastnost modelu sběrnice.  
  
6.  V okně vlastností klikněte dvakrát na vlastnost referenčního modelu sběrnice. Otevře se dialogové okno pro výběr.  
  
7.  Klikněte na tlačítko **Procházet** a vyberte instanci zveřejněné DSL.  
  
     Nástroje pro výběr se vám také umožní vyberte položku v modelu, pokud jste zadali specifické pro element druh odkaz sběrnice modelu.  
  
## <a name="creating-references-in-program-code"></a>Vytváření odkazů v programovém kódu  
 Když chcete uložit odkaz na modelu nebo element v modelu, můžete vytvořit `ModelBusReference`. Existují dva typy z `ModelBusReference`: model odkazy a odkazy na element.  
  
 Pokud chcete vytvořit odkaz na model, musíte AdapterManager DSL, z nichž je model instance a název souboru nebo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] položka projektu modelu.  
  
 Pokud chcete vytvořit odkaz na element, musíte pro soubor modelu a element, který má odkazovat na adaptér.  
  
> [!NOTE]
>  Pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus, můžete vytvořit odkazy jenom na položky ve stejné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení.  
  
### <a name="import-the-exposed-dsl-assemblies"></a>Import zveřejněné DSL sestavení  
 Využívání projekt přidejte projekt odkazy na sestavení DSL a ModelBusAdapter zveřejněné DSL.  
  
 Předpokládejme například, že chcete uložit v elementech MusicLibrary DSL ModelBus odkazy. Odkazy na ModelBus bude odkazovat na elementy FamilyTree DSL. V `Dsl` MusicLibrary řešení, v uzlu odkazy projektu přidáte odkazy na následující sestavení:  
  
-   Fabrikam.FamilyTree.Dsl.dll - zveřejněné DSL.  
  
-   Fabrikam.FamilyTree.ModelBusAdapters.dll - ModelBus adaptéru zveřejněné DSL.  
  
-   Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0  
  
-   Microsoft.VisualStudio.Modeling.Sdk.Integration.Shell.11.0  
  
 Tyto sestavení lze nalézt v `ModelBusAdapters` projektu zveřejněné DSL, v části `bin\*`.  
  
 V souboru kódu, kde vytvoříte odkazy je obvykle nutné importovat tyto obory názvů:  
  
```  
// The namespace of the DSL you want to reference:  
using Fabrikam.FamilyTree;  // Exposed DSL  
using Fabrikam.FamilyTree.ModelBusAdapters;  
using Microsoft.VisualStudio.Modeling.Integration;  
using System.Linq;  
...  
```  
  
### <a name="to-create-a-reference-to-a-model"></a>Chcete-li vytvořit odkaz na modelu  
 Pokud chcete vytvořit odkaz na model, přístup AdapterManager pro zveřejněné DSL a použít jej k vytvoření odkazu na model. Můžete zadat buď cestu k souboru, nebo `EnvDTE.ProjectItem`.  
  
 Z AdapterManager můžete získat adaptér, který poskytuje přístup na jednotlivé prvky v modelu.  
  
> [!NOTE]
>  Adaptér musí dispose po dokončení s ním. Je nejvhodnější způsob, jak toho docílit `using` příkaz. Toto dokládá následující příklad.  
  
```  
// The file path of a model instance of the FamilyTree DSL:  
string targetModelFile = "TudorFamilyTree.ftree";  
// Get the ModelBus service:  
IModelBus modelBus =   
    this.Store.GetService(typeof(SModelBus)) as IModelBus;  
// Get an adapterManager for the target DSL:  
FamilyTreeAdapterManager manager =   
    (modelbus.GetAdapterManager(FamilyTreeAdapter.AdapterId)   
     as FamilyTreeAdapterManager;  
// or: (modelBus.FindAdapterManagers(targetModelFile).First())  
// or could provide an EnvDTE.ProjectItem  
  
// Create a reference to the target model:  
// NOTE: the target model must be a file in this project.  
ModelBusReference modelReference =  
     manager.CreateReference(targetModelFile);  
// or can use an EnvDTE.ProjectItem instead of the filename  
  
// Get the root element of this model:  
using (FamilyTreeAdapter adapter =   
     modelBus.CreateAdapter(modelReference) as FamilyTreeAdapter)  
{  
  FamilyTree modelRoot = adapter.ModelRoot;  
  // Access elements under the root in the usual way:  
  foreach (Person p in modelRoot.Persons) {...}  
  // You can create adapters for individual elements:  
  ModelBusReference elementReference =  
     adapter.GetElementReference(person);  
  ...  
} // Dispose adapter  
  
```  
  
 Pokud chcete být schopni používat `modelReference` později, můžete ho uložit ve vlastnosti domény, která má externí typ `ModelBusReference`:  
  
```  
using Transaction t = this.Store.TransactionManager  
    .BeginTransaction("keep reference"))  
{  
  artist.FamilyTreeReference = modelReference;  
  t.Commit();  
}  
```  
  
 Chcete-li povolit uživatelům upravit vlastnosti této domény, použijte `ModelReferenceEditor` jako parametr do atribut Editor. Další informace najdete v tématu [povolit uživatelům upravit odkaz](#editRef).  
  
### <a name="to-create-a-reference-to-an-element"></a>Chcete-li vytvořit odkaz na element  
 Adaptér, který jste vytvořili pro model slouží k vytvoření a odkazy.  
  
```  
// person is an element in the FamilyTree model:  
ModelBusReference personReference =   
  adapter.GetElementReference(person);  
```  
  
 Pokud chcete být schopni používat `elementReference` později, můžete ho uložit ve vlastnosti domény, která má externí typ `ModelBusReference`. Chcete-li povolit uživatelům upravit, použijte `ModelElementReferenceEditor` jako parametr do atribut Editor. Další informace najdete v tématu [povolit uživatelům upravit odkaz](#editRef).  
  
### <a name="resolving-references"></a>Řešení odkazů  
 Pokud máte `ModelBusReference` (MBR) můžete získat model nebo model elementu, na který odkazuje. Pokud element se zobrazí na diagram nebo jiné zobrazení, můžete otevřít zobrazení a vyberte požadovaný prvek.  
  
 Adaptér můžete vytvořit z hlavní spouštěcí záznam. Z adaptéru můžete získat kořen modelu. Můžete také vyřešit MBRs, které odkazují na konkrétní elementy v modelu.  
  
```  
using Microsoft.VisualStudio.Modeling.Integration; ...  
ModelBusReference elementReference = ...;  
  
// Get the ModelBus service:  
IModelBus modelBus =   
    this.Store.GetService(typeof(SModelBus)) as IModelBus;  
// Use a model reference or an element reference  
// to obtain an adapter for the target model:  
using (FamilyTreeAdapter adapter =   
   modelBus.CreateAdapter(elementReference) as FamilyTreeAdapter)  
   // or CreateAdapter(modelReference)  
{  
  // Get the root of the model:  
  FamilyTree tree = adapter.ModelRoot;  
  
  // Get a model element:  
  MyDomainClass mel =  
    adapter.ResolveElementReference<MyDomainClass>(elementReference);  
  if (mel != null) {...}  
  
  // Get the diagram or other view, if there is one:  
  ModelBusView view = adapter.GetDefaultView();  
  if (view != null)   
  {  
   view.Open();  
   // Display the diagram:  
   view.Show();   
   // Attempt to select the shape that presents the element:  
   view.SetSelection(elementReference);  
  }  
} // Dispose the adapter.  
```  
  
##### <a name="to-resolve-modelbus-references-in-a-text-template"></a>Chcete-li vyřešit ModelBus odkazy v textové šablony  
  
1.  DSL, které chcete získat přístup, musí mít ModelBus adaptér, který byl nakonfigurován pro přístup pomocí textových šablon. Další informace najdete v tématu [poskytuje přístup DSL](#provide).  
  
2.  Obvykle je budou získávat přístup k cíl, který DSL pomocí modelu sběrnice odkaz (MBR) uložené ve zdroji DSL. Vaše šablona obsahuje proto – direktiva zdroj DSL plus kód vyřešit hlavní spouštěcí záznam. Další informace o textové šablony najdete v tématu [generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md).  
  
    ```  
    <#@ template debug="true" hostspecific="true"   
    inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>   
    <#@ SourceDsl processor="SourceDslDirectiveProcessor" requires="fileName='Sample.source'" #>  
    <#@ output extension=".txt" #>  
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>  
    <#@ assembly name = "System.Core" #>  
    <#@ assembly name = "Company.CompartmentDragDrop.Dsl.dll" #>  
    <#@ assembly name = "Company.CompartmentDragDrop.ModelBusAdapter.dll" #>  
    <#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>  
    <#@ import namespace="System.Linq" #>  
    <#@ import namespace="Company.CompartmentDragDrop" #>  
    <#@ import namespace="Company.CompartmentDragDrop.ModelBusAdapters" #>  
    <# // Get source root from directive processor:  
      ExampleModel source = this.ExampleModel;   
      // This DSL has a MBR in its root:  
    using (ModelBusAdapter adapter = this.ModelBus.CreateAdapter(source.ModelReference) as ModelBusAdapter)   
      {  
      ModelBusAdapterManager manager = this.ModelBus.FindAdapterManagers(this.Host.ResolvePath("Sample.compDD1")).FirstOrDefault();  
      ModelBusReference modelReference =  
        manager.CreateReference(this.Host.ResolvePath("Sample.compDD1"));  
  
      // Get the root element of this model:  
      using (CompartmentDragDropAdapter adapter =   
         this.ModelBus.CreateAdapter(modelReference) as CompartmentDragDropAdapter)  
      {  
        ModelRoot root = adapter.ModelRoot;  
    #>  
    [[<#= root.Name #>]]  
    <#  
      }  
    #>  
  
    ```  
  
 Další informace a návod najdete v tématu [pomocí Visual Studio ModelBus v textové šablony](../modeling/using-visual-studio-modelbus-in-a-text-template.md)  
  
## <a name="serializing-a-modelbusreference"></a>Serializace ModelBusReference  
 Pokud chcete uložit `ModelBusReference` (MBR) ve formě řetězce, může serializovat ho:  
  
```  
string serialized = modelBus.SerializeReference(elementReference);  
// Store it anywhere, then get it back again:  
ModelBusReference elementReferenceRestored =  
    modelBus.DeserializeReference(serialized, null);  
```  
  
 Hlavní spouštěcí záznam, který je serializováno tímto způsobem je nezávislé na kontextu. Pokud používáte jednoduché adaptér na základě souborů sběrnice modelu, hlavní spouštěcí záznam obsahuje absolutní cestu k souboru. Toto je dostatečná, pokud bude nikdy přesouvat soubory instance modelu. Ale soubory modelu obvykle budou položky v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Uživatelé se očekávají, že nemůžete přesunout celý projekt na různé části systému souborů. Budou se také předpokládají, že abyste mohli pokračovat v projektu ve správě zdrojového kódu a otevřete jej v různých počítačích. Názvy cest by měly být serializovány proto relativní k umístění na projekt, který obsahuje soubory.  
  
### <a name="serializing-relative-to-a-specified-file-path"></a>Serializace relativní k cestě zadaný soubor  
 A `ModelBusReference` obsahuje `ReferenceContext`, což je slovník, ve kterém můžete ukládat informace, jako je cesta k souboru relativně ke které by měly být serializovány.  
  
 K serializaci relativně k cestu:  
  
```  
elementReference.ReferenceContext.Add(  
   ModelBusReferencePropertySerializer.FilePathSaveContextKey,   
   currentProjectFilePath);  
string serialized = modelBus.SerializeReference(elementReference);  
```  
  
 K načtení odkazu z řetězce:  
  
```  
ReferenceContext context = new ReferenceContext();  
context.Add(ModelBusReferencePropertySerializer.FilePathLoadContextKey,  
    currentProjectFilePath);  
ModelBusReference elementReferenceRestored =  
    modelBus.DeserializeReference(serialized, context);  
```  
  
### <a name="modelbusreferences-created-by-other-adapters"></a>ModelBusReferences vytvořit další adaptéry  
 Následující informace jsou užitečné, pokud chcete vytvořit vlastní adaptér.  
  
 A `ModelBusReference` (MBR) se skládá ze dvou částí: MBR hlavičky, která je deserializoval sběrnici modelu a adaptéru konkrétní, kterou provádí správce konkrétnímu adaptéru. To umožňuje poskytovat vlastní formát serializace adaptéru. Například může odkazovat databáze spíše než soubor nebo Další informace může ukládat v odkaz na adaptéru. Vlastní adaptér můžete umístit další informace v `ReferenceContext`.  
  
 Při deserializaci MBR, je nutné zadat ReferenceContext, které jsou pak uloženy v objektu MBR. Při serializaci MBR uložené ReferenceContext slouží adaptérem ke generování řetězce. Deserializovaná řetězec neobsahuje všechny informace ReferenceContext. V jednoduchých adaptéru na základě souborů, například ReferenceContext obsahuje kořenovou cestu k souboru, který není uložen v serializovaných MBR řetězec.  
  
 V hlavním spouštěcím záznamu je deserializovat ve dvou fázích:  
  
-   `ModelBusReferencePropertySerializer`je standardní serializátoru, který přistupuje k hlavičce MBR. Používá standardní DSL `SerializationContext` balík vlastností, která je uložena v `ReferenceContext` pomocí klíče `ModelBusReferencePropertySerializer.ModelBusLoadContextKey`. Konkrétně `SerializationContext` by měl obsahovat instanci `ModelBus`.  
  
-   Váš ModelBus adaptér se zabývá konkrétní adaptér součástí hlavního spouštěcího záznamu. Další informace uložené v ReferenceContext z hlavního spouštěcího záznamu může použít. Jednoduché na základě souborů adaptér udržuje kořenové cesty k souborům pomocí klíče `FilePathLoadContextKey` a `FilePathSaveContextKey`.  
  
     Odkaz na adaptéru v souboru modelu je deserializovat jenom v případě, že se používá.  
  
## <a name="to-create-a-model"></a>Pro vytvoření modelu  
  
### <a name="creating-opening-and-editing-a-model"></a>Vytvoření, otevření a úpravy modelu  
 Následující fragment je převzat z ukázky stav počítače na webu VMSDK. Ukazuje použití ModelBusReferences k vytváření a otevírání modelu a získat diagram přidruženého k modelu.  
  
 V této ukázce je název cílového DSL StateMachine. Několik názvů jsou odvozeny od, jako je například název třídy modelu a název ModelBusAdapter.  
  
```  
using Fabrikam.StateMachine.ModelBusAdapters;   
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Integration;  
using Microsoft.VisualStudio.Modeling.Integration.Shell;  
using Microsoft.VisualStudio.Modeling.Shell;  
...  
// Create a new model.  
ModelBusReference modelReference =   
   StateMachineAdapterManager    .CreateStateMachineModel(modelName, fileName);  
//Keep reference of new model in this model.  
using (Transaction t = ...)  
{  
  myModelElement.ReferenceProperty = modelReference;  
  t.Commit();  
}  
// Get the ModelBus service from Visual Studio.  
IModelBus modelBus = Microsoft.VisualStudio.Shell.Package.  
    GetGlobalService(typeof(SModelBus)) as IModelBus;  
// Get a modelbus adapter on the new model.  
ModelBusAdapter modelBusAdapter;  
modelBus.TryCreateAdapter(modelReference,   
    this.ServiceProvider, out modelBusAdapter);  
using (StateMachineAdapter adapter =   
      modelBusAdapter as StateMachineAdapter)  
{  
    if (adapter != null)  
    {  
        // Obtain a Diagram from the adapter.  
        Diagram targetDiagram =   
           ((StandardVsModelingDiagramView)  
                 adapter.GetDefaultView()  
            ).Diagram;  
  
        using (Transaction t =   
             targetDiagram.Store.TransactionManager  
                .BeginTransaction("Update diagram"))  
        {  
            DoUpdates(targetDiagram);  
            t.Commit();  
        }  
  
        // Display the new diagram.  
        adapter.GetDefaultView().Show();  
    }  
}  
```  
  
## <a name="validating-references"></a>Ověřování odkazy  
 BrokenReferenceDetector testy všechny vlastnosti v úložišti, které mohou být uloženy ModelBusReferences. Zavolá akci jste, které poskytují, kde je najít žádnou akci. To je zvlášť užitečné pro metody ověřování. Metodu ověření testy úložiště na pokus o uložení modelu a hlásí poškozenými odkazy v okně chyb:  
  
```  
[ValidationMethod(ValidationCategories.Save)]  
public void ValidateModelBusReferences(ValidationContext context)  
{  
  BrokenReferenceDetector.DetectBrokenReferences(this.Store,  
    delegate(ModelElement element, // parent of property  
             DomainPropertyInfo property, // identifies property  
             ModelBusReference reference) // invalid reference  
    {   
      context.LogError(string.Format(INVALID_REF_FORMAT,   
             property.Name,   
             referenceState.Name,   
             new ModelBusReferenceTypeConverter().  
                 ConvertToInvariantString(reference)),   
         "Reference",   
         element);  
      });  
}}  
private const string INVALID_REF_FORMAT =   
    "The '{0}' domain property of ths ReferenceState instance "  
  + "named '{1}' contains reference value '{2}' which is invalid";  
```  
  
## <a name="actions-performed-by-the-modelbus-extension"></a>Akce prováděné ModelBus rozšíření  
 Tyto informace je nezbytné, ale může být užitečné, pokud provedete rozsáhlé používání ModelBus.  
  
 Rozšíření ModelBus provede tyto změny v řešení DSL.  
  
 Když kliknete pravým tlačítkem na diagram definice DSL, klikněte na tlačítko **povolit Modelbus**a potom vyberte **povolit tento DSL využívat ModelBus**:  
  
-   V projektu DSL je přidán odkaz na **Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0.dll**  
  
-   V definici DSL se přidá odkaz na externí typ: `Microsoft.VisualStudio.Modeling.Integration.ModelBusReference`.  
  
     Zobrazí se odkaz v **DSL Explorer**v části **domény typy**. Odkazy na externí typ přidat ručně, klikněte pravým tlačítkem na kořenový uzel.  
  
-   Přidá nový soubor šablony, **Dsl\GeneratedCode\ModelBusReferencesSerialization.tt**.  
  
 Pokud nastavíte typ vlastnosti domény ModelBusReference a potom klikněte pravým tlačítkem na vlastnost a klikněte na tlačítko **specifické vlastnosti povolit ModelBusReference**:  
  
-   Několik CLR atributy jsou přidány pro vlastnost domain. Zobrazí je v poli vlastních atributů v okně Vlastnosti. V **Dsl\GeneratedCode\DomainClasses.cs**, uvidíte na deklarace vlastnosti atributy:  
  
    ```  
    [System.ComponentModel.TypeConverter(typeof(  
    Microsoft.VisualStudio.Modeling.Integration.ModelBusReferenceTypeConverter))]  
    [System.ComponentModel.Editor(typeof(  
      Microsoft.VisualStudio.Modeling.Integration.Picker  
      .ModelReferenceEditor // or ModelElementReferenceEditor  
      ), typeof(System.Drawing.Design.UITypeEditor))]  
    [Microsoft.VisualStudio.Modeling.Integration.Picker  
      .SupplyFileBasedBrowserConfiguration  
      ("Choose a model file", "Target model|*.target")]  
    ```  
  
 Po kliknutí pravým Diagram definice DSL, klikněte na tlačítko **povolit ModelBus**a vyberte **vystavit tento DSL k ModelBus**:  
  
-   Nový projekt `ModelBusAdapter` je přidán do řešení.  
  
-   Odkaz na `ModelBusAdapter` je přidán do `DslPackage` projektu. `ModelBusAdapter`obsahuje odkaz na `Dsl` projektu.  
  
-   V **DslPackage\source.extention.tt**, `|ModelBusAdapter|` se přidá jako součást MEF.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: otevření modelu ze souboru v programovém kódu](../modeling/how-to-open-a-model-from-file-in-program-code.md)   
 [Postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Použití prvku Visual Studio ModelBus v textové šabloně](../modeling/using-visual-studio-modelbus-in-a-text-template.md)
