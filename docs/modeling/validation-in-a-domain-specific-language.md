---
title: "Ověření v jazyce specifické pro doménu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, constraints
- Domain-Specific Language, validation
ms.assetid: 65b93df8-af3c-462b-904c-60292f8ed381
caps.latest.revision: "33"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 1d29c90dbfebaa71ace3e6d1027f17bb43fcd971
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="validation-in-a-domain-specific-language"></a>Ověřování v jazyce specifickém pro doménu
Jako autor jazyka specifické pro doménu (DSL) můžete definovat omezení ověřování, abyste ověřili smysluplný model vytvořený uživatelem. Pokud vaše DSL umožňuje uživatelům kreslení rodiny strom osoby a jejich nadřazených, můžete například napsat omezení, které zajistí, že podřízené položky data narození po svých nadřazených složek.  
  
 Může mít omezení ověřování spustit při uložení modelu, když je otevřen a když uživatel spustí explicitně **ověřením** příkazu nabídky. Můžete také provést ověření v řízení programu. Například může provést ověření v reakci na změnu v hodnotě vlastnosti nebo vztah.  
  
 Ověření je zvláště důležité, pokud píšete textové šablony nebo jiných nástrojů, které zpracovávají modely vašich uživatelů. Ověření zajistí, že modely splnit předpoklady předpokládá, že pomocí těchto nástrojů.  
  
> [!WARNING]
>  Můžete také povolit omezení ověřování být definován v samostatných rozšíření DSL, společně s příkazy nabídky rozšíření a gesto obslužné rutiny. Uživatelé mohou tato rozšíření kromě vaší DSL nainstalovat. Další informace najdete v tématu [rozšíření vaší DSL pomocí MEF](../modeling/extend-your-dsl-by-using-mef.md).  
  
## <a name="running-validation"></a>Spuštění ověření  
 Když uživatel upravuje model, který je instance jazyka specifické pro doménu následující akce můžete spustit ověření:  
  
-   Klikněte pravým tlačítkem na obrázku a vyberte **ověření všech**.  
  
-   Klikněte pravým tlačítkem myši na nejvyšší uzel v Průzkumníku DSL a vyberte **ověřit všechny**  
  
-   Model uložte.  
  
-   Otevřete model.  
  
-   Kromě toho můžete napsat kód programu, který spustí ověření, například v rámci příkazu nabídky nebo v reakci na změnu.  
  
 Všechny chyby ověřování, zobrazí se v **seznam chyb** okno. Uživatel může dvakrát klikněte na chybovou zprávu a vyberte modelu prvky, které jsou příčinu chyby.  
  
## <a name="defining-validation-constraints"></a>Definování omezení ověřování  
 Definování omezení ověření přidáním ověření metody do třídy domény nebo vztahy vaší DSL. Při spuštění ověřování, uživatelem nebo v rámci programu řízení, jsou provést některé nebo všechny metody ověřování. Každá metoda se použije pro každou instanci její třídy a může být několik metod ověření každá třída.  
  
 Každá metoda ověření oznámí všechny chyby, které najde.  
  
> [!NOTE]
>  Metody ověření zprávy o chybách, ale neměňte modelu. Pokud chcete upravit nebo zakázat určité změny naleznete v tématu [alternativy k ověření](#alternatives).  
  
#### <a name="to-define-a-validation-constraint"></a>K definování omezení ověření  
  
1.  Povolení ověřování v **Editor\Validation** uzlu:  
  
    1.  Otevřete **Dsl\DslDefinition.dsl**.  
  
    2.  V Průzkumníku DSL rozbalte **Editor** uzel a vyberte možnost **ověření**.  
  
    3.  V okně vlastnosti nastavit **používá** vlastnosti, které chcete `true`. Je nejvhodnější nastavit tyto vlastnosti.  
  
    4.  Klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů v Průzkumníku řešení.  
  
2.  Zápis definice částečné třídy pro jeden nebo více tříd domény nebo domény vztahy. Zápis do nového souboru kódu v tyto definice **Dsl** projektu.  
  
3.  Každá třída tímto atributem předpony:  
  
    ```csharp  
    [ValidationState(ValidationState.Enabled)]  
    ```  
  
    -   Ve výchozím nastavení bude tento atribut také povolit ověření odvozené třídy. Pokud chcete zakázat ověřování pro určité odvozené třídy, můžete použít `ValidationState.Disabled`.  
  
4.  Přidejte metody ověřování na třídy. Každá metoda ověření může mít libovolný název, ale mít jeden parametr typu <xref:Microsoft.VisualStudio.Modeling.Validation.ValidationContext>.  
  
     Musí obsahovat předponu s jedním nebo více `ValidationMethod` atributy:  
  
    ```csharp  
    [ValidationMethod (ValidationCategories.Open | ValidationCategories.Save | ValidationCategories.Menu ) ]  
    ```  
  
     ValidationCategories zadejte, kdy metodu provést.  
  
 Příklad:  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Validation;  
  
// Allow validation methods in this class:  
[ValidationState(ValidationState.Enabled)]  
// In this DSL, ParentsHaveChildren is a domain relationship  
// from Person to Person:  
public partial class ParentsHaveChildren  
{  
  // Identify the method as a validation method:  
  [ValidationMethod  
  ( // Specify which events cause the method to be invoked:  
    ValidationCategories.Open // On file load.  
  | ValidationCategories.Save // On save to file.  
  | ValidationCategories.Menu // On user menu command.  
  )]  
  // This method is applied to each instance of the   
  // type (and its subtypes) in a model:   
  private void ValidateParentBirth(ValidationContext context)     
  {  
    // In this DSL, the role names of this relationship  
    // are "Child" and "Parent":   
     if (this.Child.BirthYear < this.Parent.BirthYear   
        // Allow user to leave the year unset:  
        && this.Child.BirthYear != 0)  
      {  
        context.LogError(  
             // Description:  
                       "Child must be born after Parent",  
             // Unique code for this error:  
                       "FAB001ParentBirthError",   
              // Objects to select when user double-clicks error:  
                       this.Child,   
                       this.Parent);  
    }  
  }  
```  
  
 Informace o tomto kódu následující body:  
  
-   Metody ověřování můžete přidat do domény třídy ani vztahy domény. Kód pro tyto typy je v **Dsl\Generated Code\Domain\*.cs**.  
  
-   Každá metoda ověření se použijí na každou instanci její třídy a jejích podtříd. V případě relace domény každá instance je propojení mezi dvěma prvky modelu.  
  
-   Metody ověřování se nepoužívají v libovolném zadané pořadí a každá metoda neplatí pro instance své třídy v libovolném pořadí předvídatelný.  
  
-   Je obvykle chybný postup pro metodu ověření pro aktualizaci obsahu úložiště, protože by to vést k nekonzistentním výsledkům. Místo toho sestavu všechny chyby při volání metody `context.LogError`, `LogWarning` nebo `LogInfo`.  
  
-   Ve volání LogError můžete zadat seznam prvků modelu nebo vztah odkazy, které budou vybrány při poklepání chybovou zprávu.  
  
-   Informace o tom, jak číst modelu v programovém kódu najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 V příkladu platí pro následující modelu domény. Relace ParentsHaveChildren má role, které jsou s názvem podřízenými a nadřazenými.  
  
 ![Diagram DSL definice & č. 45; Rodina stromu modelu](../modeling/media/familyt_person.png "FamilyT_Person")  
  
## <a name="validation-categories"></a>Ověření kategorie  
 V <xref:Microsoft.VisualStudio.Modeling.Validation.ValidationMethodAttribute> atribut, zadejte v případě, že metodu ověřování, kterou se má provést.  
  
|Kategorie|Spuštění|  
|--------------|---------------|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Když uživatel vyvolá příkaz nabídky ověřením.|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Při otevření souboru modelu.|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Při uložení souboru. Pokud nejsou chyby ověření, uživatel bude mu udělená možnost uložení zrušení operace.|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Při uložení souboru. Pokud existují chyb z metody v této kategorii, uživatel bude upozorněn, že nemusí být možné znovu otevřít soubor.<br /><br /> Kategorie pro metody ověřování, které testování pro duplicitní názvy nebo ID nebo jinými podmínkami, které by mohly způsobit chyby při načítání.|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Když je volána metoda ValidateCustom. Ověření v této kategorii lze volat pouze z kódu programu.<br /><br /> Další informace najdete v tématu [vlastní ověření kategorie](#custom).|  
  
## <a name="where-to-place-validation-methods"></a>Kam umístit metody ověřování  
 Stejného efektu dosáhnete často umístěním metodu ověření na jiný typ. Může například přidejte metodu do třídy osoba místo ParentsHaveChildren relace a mějte ho iteraci v rámci odkazy:  
  
```  
[ValidationState(ValidationState.Enabled)]  
public partial class Person  
{[ValidationMethod  
 ( ValidationCategories.Open   
 | ValidationCategories.Save  
 | ValidationCategories.Menu  
 )  
]  
  private void ValidateParentBirth(ValidationContext context)     
  {  
    // Iterate through ParentHasChildren links:  
    foreach (Person parent in this.Parents)  
    {  
        if (this.BirthYear <= parent.BirthYear)  
        { ...  
  
```  
  
 **Agregování omezení ověřování.** Chcete-li použít ověření místo, definujte jeden ověřovací metodu třídu vlastníka takové kořenový prvek modelu. Tento postup také umožňuje agregovat více zpráv o chybách do jedné zprávy.  
  
 Nevýhody se, že je kombinovaná metoda méně usnadňují správu, a že omezení musí všechny mít stejnou `ValidationCategories`. Proto doporučujeme, pokud je to možné zachovat každý omezení v samostatné metodě.  
  
 **Předávání hodnot v kontextu mezipaměti.** Parametr kontextu má slovník, do kterého můžete umístit libovolné hodnoty. Slovník trvá po dobu trvání spusťte ověření. Konkrétní ověřovací metodu může například zachovat počtu chyb v kontextu a použít nedošlo k zaplavení okno chyby s opakovaných zprávy. Příklad:  
  
```csharp  
List<ParentsHaveChildren> erroneousLinks;  
if (!context.TryGetCacheValue("erroneousLinks", out erroneousLinks))  
erroneousLinks = new List<ParentsHaveChildren>();  
erroneousLinks.Add(this);  
context.SetCacheValue("erroneousLinks", erroneousLinks);  
if (erroneousLinks.Count < 5) { context.LogError( ... ); }  
  
```  
  
## <a name="validation-of-multiplicities"></a>Ověření Mnohočetnostmi  
 Metody ověřování pro kontrolu minimální násobnost jsou pro vaše DSL automaticky generovány. Kód je zapsán do **Dsl\Generated Code\MultiplicityValidation.cs**. Tyto metody projeví, jakmile povolíte ověření v **Editor\Validation** uzlu v Průzkumníku DSL.  
  
 Pokud nastavíte násobnosti atributu role relace domény, musí být 1.. * nebo 1..1, ale uživatel nevytváří odkaz této relace, zobrazí se chybová zpráva ověření.  
  
 Například pokud má vaše DSL třídy osoby a města a relaci PersonLivesInTown s vztahu **1..\***  v roli města, potom pro každou osobu, která nemá žádné města, chybová zpráva se zobrazí.  
  
## <a name="running-validation-from-program-code"></a>Spuštění ověření z kódu programu  
 Přístup k nebo vytvořit ValidationController můžete spustit ověření. Pokud chcete chyby, který se má zobrazit uživateli v okno chyby, použijte ValidationController, který je připojen k DocData do diagramu. Pokud píšete příkazu nabídky, například `CurrentDocData.ValidationController` je k dispozici v příkazu set – třída:  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Validation;  
using Microsoft.VisualStudio.Modeling.Shell;  
...  
partial class MyLanguageCommandSet   
{  
  private void OnMenuMyContextMenuCommand(object sender, EventArgs e)   
  {   
   ValidationController controller = this.CurrentDocData.ValidationController;   
...  
  
```  
  
 Další informace najdete v tématu [postupy: přidání příkazu do místní nabídky](../modeling/how-to-add-a-command-to-the-shortcut-menu.md).  
  
 Můžete také vytvořit řadič samostatné ověření a spravovat sami chyby. Příklad:  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Validation;  
using Microsoft.VisualStudio.Modeling.Shell;  
...  
Store store = ...;  
VsValidationController validator = new VsValidationController(s);  
// Validate all elements in the Store:  
if (!validator.Validate(store, ValidationCategories.Save))  
{  
  // Deal with errors:  
  foreach (ValidationMessage message in validator.ValidationMessages) { ... }  
}  
  
```  
  
## <a name="running-validation-when-a-change-occurs"></a>Spuštění ověření, když dojde ke změně  
 Pokud chcete zajistit, že uživatel bude-li model stává neplatným okamžitě upozorněn, můžete definovat úložiště událost, která spustí ověřování. Další informace o událostech úložiště najdete v tématu [událost obslužné rutiny rozšíří změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
 Kromě ověřovacího kódu přidat soubor vlastní kód pro vaše **DslPackage** projektu s obsahem, podobně jako v následujícím příkladu. Tento kód používá `ValidationController` připojená k dokumentu. Tento řadič se zobrazí chyby ověření v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] seznam chyb.  
  
```csharp  
using System;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Validation;  
namespace Company.FamilyTree  
{  
  partial class FamilyTreeDocData // Change name to your DocData.  
  {  
    // Register the store event handler:   
    protected override void OnDocumentLoaded()  
    {  
      base.OnDocumentLoaded();  
      DomainClassInfo observedLinkInfo = this.Store.DomainDataDirectory  
         .FindDomainClass(typeof(ParentsHaveChildren));  
      DomainClassInfo observedClassInfo = this.Store.DomainDataDirectory  
         .FindDomainClass(typeof(Person));  
      EventManagerDirectory events = this.Store.EventManagerDirectory;  
      events.ElementAdded  
         .Add(observedLinkInfo, new EventHandler<ElementAddedEventArgs>(ParentLinkAddedHandler));  
      events.ElementDeleted.Add(observedLinkInfo, new EventHandler<ElementDeletedEventArgs>(ParentLinkDeletedHandler));  
      events.ElementPropertyChanged.Add(observedClassInfo, new EventHandler<ElementPropertyChangedEventArgs>(BirthDateChangedHandler));  
    }  
    // Handler will be called after transaction that creates a link:  
    private void ParentLinkAddedHandler(object sender,  
                                ElementAddedEventArgs e)  
    {  
      this.ValidationController.Validate(e.ModelElement,  
           ValidationCategories.Save);  
    }  
    // Called when a link is deleted:  
    private void ParentLinkDeletedHandler(object sender,   
                                ElementDeletedEventArgs e)  
    {  
      // Don't apply validation to a deleted item!   
      // - Validate store to refresh the error list.  
      this.ValidationController.Validate(this.Store,  
           ValidationCategories.Save);  
    }  
    // Called when any property of a Person element changes:  
    private void BirthDateChangedHandler(object sender,  
                      ElementPropertyChangedEventArgs e)  
    {  
      Person person = e.ModelElement as Person;  
      // Not interested in changes in other properties:  
      if (e.DomainProperty.Id != Person.BirthYearDomainPropertyId)  
          return;  
  
      // Validate all parent links to and from the person:  
      this.ValidationController.Validate(  
        ParentsHaveChildren.GetLinksToParents(person)  
        .Concat(ParentsHaveChildren.GetLinksToChildren(person))  
        , ValidationCategories.Save);  
    }  
  }  
}  
  
```  
  
 Obslužné rutiny se také nazývají po zpět nebo znovu operace, které ovlivňují odkazy nebo elementy.  
  
##  <a name="custom"></a>Kategorie vlastního ověřování  
 Kromě standardní ověření kategorie, jako jsou nabídky a otevřete můžete definovat vlastní kategorie. Můžete vyvolat těchto kategorií z kódu programu. Uživatele nelze vyvolat je přímo.  
  
 Typické použití pro vlastní kategorie je definovat kategorie, která ověřuje, zda model splňuje předpoklady konkrétní nástroje.  
  
 Pokud chcete přidat do určité kategorie metodu ověření, předpony s atributem takto:  
  
```csharp  
[ValidationMethod(CustomCategory = "PreconditionsForGeneratePartsList")]  
[ValidationMethod(ValidationCategory.Menu)]   
private void TestForCircularLinks(ValidationContext context)   
{...}  
  
```  
  
> [!NOTE]
>  Můžete před metodu s tolik `[ValidationMethod()]` atributů tak, jak chcete. Metodu můžete přidat do kategorií standardní a vlastní.  
  
 K vyvolání vlastního ověřování:  
  
```csharp  
  
// Invoke all validation methods in a custom category:   
validationController.ValidateCustom  
  (store, // or a list of model elements  
   "PreconditionsForGeneratePartsList");  
```  
  
##  <a name="alternatives"></a>Alternativy k ověření  
 Omezení ověřování zprávy o chybách, ale neměňte modelu. Pokud místo toho chcete zabránit vzniku neplatný model, můžete vytvořit další techniky.  
  
 Tyto postupy však nejsou doporučené. Je obvykle lepší nechat uživatele rozhodnout, jak chybu opravit model neplatný.  
  
 **Upravte změnu k obnovení modelu platnosti.** Například pokud uživatel nastaví vlastnost vyšší než maximální povolený, mohli resetovat vlastnost maximální hodnotě. K tomuto účelu definujte pravidlo. Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).  
  
 **Pokud dojde k pokusu o neplatný změnu vrátit zpět transakci.** Můžete také definovat pravidla pro tento účel, ale v některých případech je možné přepsat obslužnou rutinu vlastnost **OnValueChanging()**, nebo jako přepsat metodu `OnDeleted().` vrácení transakce, použijte `this.Store.TransactionManager.CurrentTransaction.Rollback().` Další informace informace najdete v tématu [domény obslužné rutiny změnit hodnotu vlastnosti](../modeling/domain-property-value-change-handlers.md).  
  
> [!WARNING]
>  Ujistěte se, že uživatel zná, tato změna byla upravena nebo vrácena zpět. Operátor`System.Windows.Forms.MessageBox.Show("message").`  
  
## <a name="see-also"></a>Viz také  
 [Navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Obslužné rutiny události šířící změny mimo model](../modeling/event-handlers-propagate-changes-outside-the-model.md)