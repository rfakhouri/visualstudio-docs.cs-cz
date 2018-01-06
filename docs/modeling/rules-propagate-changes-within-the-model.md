---
title: "Pravidla rozšíření změn v rámci modelu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, programming domain models
- Domain-Specific Language, rules
ms.assetid: 1690a38a-c8f5-4bc6-aab9-015771ec6647
caps.latest.revision: "30"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 7f2b46b615c80e2455823ee63262f17f08d307c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="rules-propagate-changes-within-the-model"></a>Pravidla šířící změny v modelu
Můžete vytvořit pravidlo úložiště rozšířit změnu od jednoho prvku na jiné vizualizace a modelování SDK (VMSDK). Když dojde ke změně na libovolný prvek v úložišti, pravidla je naplánováno spuštění, obvykle v případě, že nejkrajnější je transakce potvrzena. Existují různé typy pravidel pro různé druhy událostí, například přidávání element nebo odstranění. Pravidla můžete připojit na konkrétní typy elementů, tvarů nebo diagramů. Mnoho vestavěných funkcí jsou definována pravidly: například pravidla zajistěte, aby diagram aktualizovala při změně modelu. Jazyka specifické pro doménu můžete přizpůsobit přidáním vlastních pravidel.  
  
 Úložiště pravidel jsou obzvláště užitečná pro přenos změn v úložišti – to znamená, změní na elementů modelu, relace, tvarů nebo konektory a jejich domény vlastnosti. Pravidla se nespustí, pokud uživatel vyvolá příkazy Zpět nebo znovu. Místo toho správce transakcí je zajištěno, že obsah úložiště se obnoví na správném stavu. Pokud chcete rozšířit změny na prostředky mimo úložišti, použijte ukládání událostí. Další informace najdete v tématu [událost obslužné rutiny rozšíří změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
 Předpokládejme například, že chcete určit, že vždy, když uživatel (nebo kódu) vytvoří nového elementu typu ExampleDomainClass, další elementu jiného typu je vytvořen v jiné části modelu. Můžete zapsat AddRule a přidružte ji k ExampleDomainClass. V pravidlo můžete vytvořit další element by napsat kód.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
  
namespace ExampleNamespace  
{  
 // Attribute associates the rule with a domain class:  
 [RuleOn(typeof(ExampleDomainClass), FireTime=TimeToFire.TopLevelCommit)]  
 // The rule is a class derived from one of the abstract rules:  
 class MyAddRule : AddRule  
 {  
  // Override the abstract method:  
  public override void ElementAdded(ElementAddedEventArgs e)  
  {  
    base.ElementAdded(e);  
    ExampleDomainClass element = e.ModelElement;  
    Store store = element.Store;  
    // Ignore this call if we're currently loading a model:  
    if (store.TransactionManager.CurrentTransaction.IsSerializing)   
       return;  
  
    // Code here propagates change as required - for example:  
      AnotherDomainClass echo = new AnotherDomainClass(element.Partition);  
      echo.Name = element.Name;  
      echo.Parent = element.Parent;    
    }  
  }  
 // The rule must be registered:  
 public partial class ExampleDomainModel  
 {  
   protected override Type[] GetCustomDomainModelTypes()  
   {  
     List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
     types.Add(typeof(MyAddRule));  
     // If you add more rules, list them here.   
     return types.ToArray();  
   }  
 }  
}  
  
```  
  
> [!NOTE]
>  Kód pravidlo by se měl změnit stav pouze elementy v úložišti; To znamená pravidlo by měl změnit pouze elementů modelu, vztahy, tvarů, konektory, diagramy nebo jejich vlastnosti. Pokud chcete rozšířit změny na prostředky mimo úložišti, definujte ukládání událostí. Další informace najdete v tématu [událost obslužné rutiny rozšíří změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md)  
  
### <a name="to-define-a-rule"></a>Chcete-li definovat pravidla  
  
1.  Definujte pravidla jako předponu třídu `RuleOn` atribut. Atribut přidruží pravidlo s jedním z vaší domény třídy, vztahů nebo elementy diagramu. Pravidlo se použije pro všechny instance této třídy, které mohou být abstraktní.  
  
2.  Zaregistrovat pravidlo jej přidat do sady vrácený `GetCustomDomainModelTypes()` v třídě modelu domény.  
  
3.  Odvození třídy pravidlo z jednoho z abstraktní třídy pravidlo a napsat kód metody spouštění.  
  
 Následující části popisují tyto kroky podrobněji.  
  
### <a name="to-define-a-rule-on-a-domain-class"></a>Chcete-li definovat pravidla na třídě domény  
  
-   V souboru vlastní kód, definice třídy a její předpony <xref:Microsoft.VisualStudio.Modeling.RuleOnAttribute> atribut:  
  
    ```  
    [RuleOn(typeof(ExampleElement),   
         // Usual value - but required, because it is not the default:  
         FireTime = TimeToFire.TopLevelCommit)]   
    class MyRule ...  
  
    ```  
  
-   Typ subjektu v první parametr může být třídy domény, relace domény, tvaru, konektoru nebo diagram. Obvykle použít pravidla pro třídy domény a vztahy.  
  
     `FireTime` Je obvykle `TopLevelCommit`. Tím se zajistí, že pravidlo se spustí až po byly provedeny všechny primární změny transakce. Alternativ jsou vložené, která zpracuje pravidlo brzy po provedení změny; a LocalCommit, který provede pravidlo na konci aktuální transakce (což nemusí být krajních). Můžete také nastavit prioritu pravidla narušit jeho řazení do fronty, ale je to nespolehlivé metoda dosáhnout výsledků, které vyžadujete.  
  
-   Jako typ subjektu můžete zadat u abstraktní třídy.  
  
-   Toto pravidlo se vztahuje na všechny instance třídy subjektu.  
  
-   Výchozí hodnota pro `FireTime` je TimeToFire.TopLevelCommit. To způsobí, že pravidlo spustit, když je nejkrajnější transakce potvrzena. Alternativou je TimeToFire.Inline. To způsobí, že pravidlo provést krátce po aktivační událost.  
  
### <a name="to-register-the-rule"></a>Pravidla registrace  
  
-   Přidat vlastní pravidlo třídy do seznamu typů vrácené `GetCustomDomainModelTypes` v modelu domény:  
  
    ```  
    public partial class ExampleDomainModel  
     {  
       protected override Type[] GetCustomDomainModelTypes()  
       {  
         List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
         types.Add(typeof(MyAddRule));  
         // If you add more rules, list them here.   
         return types.ToArray();  
       }  
     }  
  
    ```  
  
-   Pokud si nejste jisti názvem třídy modelu domény, podívejte se do souboru **Dsl\GeneratedCode\DomainModel.cs**  
  
-   Napište tento kód v souboru vlastního kódu v projektu DSL.  
  
### <a name="to-write-the-code-of-the-rule"></a>Psaní kódu pravidla  
  
-   Odvození třídy pravidlo z jednoho z následujících základních tříd:  
  
    |Base – třída|Aktivační události|  
    |----------------|-------------|  
    |<xref:Microsoft.VisualStudio.Modeling.AddRule>|Se přidá elementu, odkaz nebo tvaru.<br /><br /> Použijte k detekci nové relace, kromě nových elementů.|  
    |<xref:Microsoft.VisualStudio.Modeling.ChangeRule>|Je-li změnit hodnotu vlastnosti domény. Argument metody poskytuje starými a novými hodnotami.<br /><br /> U tvarů, toto pravidlo aktivováno, když integrované `AbsoluteBounds` změny vlastností, pokud se přesune tvaru.<br /><br /> V mnoha případech je pohodlnější přepsat `OnValueChanged` nebo `OnValueChanging` v obslužné rutině vlastnost. Tyto metody jsou volány bezprostředně před a po provedení změny. Naopak pravidlo obvykle běží na konci transakce. Další informace najdete v tématu [domény obslužné rutiny změnit hodnotu vlastnosti](../modeling/domain-property-value-change-handlers.md). **Poznámka:** toto pravidlo není aktivováno, když je vytvořené nebo odstraněné odkaz. Místo toho zápis `AddRule` a `DeleteRule` pro vztah domény.|  
    |<xref:Microsoft.VisualStudio.Modeling.DeletingRule>|Aktivuje, když prvek nebo odkaz je odstranit. Vlastnost ModelElement.IsDeleting platí až do konce transakce.|  
    |<xref:Microsoft.VisualStudio.Modeling.DeleteRule>|Provést, pokud byl odstraněn prvek nebo odkaz. Poté, co byly provedeny všechny ostatní pravidla, včetně DeletingRules spuštění pravidla. ModelElement.IsDeleting hodnotu false a ModelElement.IsDeleted má hodnotu true. Povolit pro následné vrácení zpět, není ve skutečnosti odebrat element z paměti, ale bude odebrán z Store.ElementDirectory.|  
    |<xref:Microsoft.VisualStudio.Modeling.MoveRule>|Element je na jiný přesunout z jednoho úložiště oddílu.<br /><br /> (Všimněte si, že to nesouvisí s grafické pozici obrazce.)|  
    |<xref:Microsoft.VisualStudio.Modeling.RolePlayerChangeRule>|Toto pravidlo se vztahuje pouze vztahy domén. Aktivuje se, pokud přiřadíte element modelu explicitně na libovolném konci odkazu.|  
    |<xref:Microsoft.VisualStudio.Modeling.RolePlayerPositionChangeRule>|Aktivuje se při řazení odkazy z elementu nebo změně pomocí metody MoveBefore nebo MoveToIndex na odkaz.|  
    |<xref:Microsoft.VisualStudio.Modeling.TransactionBeginningRule>|Spustit, když je vytvořena transakce.|  
    |<xref:Microsoft.VisualStudio.Modeling.TransactionCommittingRule>|Spustit, když transakce je možné zapsat.|  
    |<xref:Microsoft.VisualStudio.Modeling.TransactionRollingBackRule>|Spustit, když transakce je vrácena zpět.|  
  
-   Každá třída má metodu, která je přepsat. Typ `override` v třídě chcete zjistit. Parametr tato metoda identifikuje elementu, který mění se.  
  
 Informace o pravidlech následující body:  
  
1.  Sadu změn v transakci mohou spustit mnoho pravidla. Pravidla jsou obvykle spustit, když je nejkrajnější transakce potvrzena. Jsou prováděna v neurčené pořadí.  
  
2.  Pravidlo je vždy provést v transakci. Proto nemáte vytvořit novou transakci provádět změny.  
  
3.  Pravidla nebudou provedeny, když transakce je vrácena, nebo když se operace zpět nebo znovu. Tyto operace obnovit veškerý obsah úložiště do předchozího stavu. Proto pokud pravidla změní stav nic mimo úložišti, se nemusí mějte synchronism s úložištěm obsahu. Pokud chcete aktualizovat stav mimo úložiště, je vhodnější použít události. Další informace najdete v tématu [událost obslužné rutiny rozšíří změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
4.  Některá pravidla jsou spustit, když je model načtený ze souboru. Chcete-li zjistit, zda je v průběhu načítání nebo ukládání, použijte `store.TransactionManager.CurrentTransaction.IsSerializing`.  
  
5.  Pokud kód pravidla vytvoří aktivační události další pravidla, budou přidány na konec seznamu pálení a bude proveden před dokončením transakce. DeletedRules se spustí až po všemi ostatními pravidly. Jedno pravidlo můžete spustit mnohokrát v transakci, jednou pro každé změně.  
  
6.  Předávání informací na Internet a z pravidel, můžete ukládat informace ve `TransactionContext`. Toto je právě slovník, který se zachová během transakce. Je uvolněn při ukončení transakce. Argumenty událostí v každé pravidlo poskytují přístup k němu. Mějte na paměti, že pravidla nebudou provedeny místo.  
  
7.  Použijte pravidla po zvážení jiné alternativy. Pokud chcete aktualizovat vlastnosti, když se změní hodnota, zvažte například používání počítané vlastnosti. Pokud chcete omezit velikosti či umístění obrazce, použijte `BoundsRule`. Pokud chcete, aby odpovídal na změnu v hodnotě vlastnosti, přidejte `OnValueChanged` obslužné rutiny pro vlastnost. Další informace najdete v tématu [reakce na a šíření změny](../modeling/responding-to-and-propagating-changes.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad aktualizuje vlastnosti při vytváření instance vztahu domény k propojení dvou prvků. Pravidlo se spustí, ne jenom v případě, že uživatel vytvoří odkaz v diagramu, ale taky Pokud program kód vytvoří odkaz.  
  
 K testování v tomto příkladu, vytvořte DSL, pomocí šablony řešení tok úkolů a vložte následující kód v souboru v projektu Dsl. Sestavení a spuštění řešení a ukázkový soubor otevřete v projektu ladění. Zakreslit komentář propojení mezi obrazce komentář, element toku. Text v sestavě na nejnovější elementu, který jste se připojili ho k se změní komentář.  
  
 V praxi by obvykle zápisu DeletRule pro každý AddRule.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.VisualStudio.Modeling;  
  
namespace Company.TaskRuleExample  
{  
  
  [RuleOn(typeof(CommentReferencesSubjects))]  
  public class RoleRule : AddRule  
  {  
  
    public override void ElementAdded(ElementAddedEventArgs e)  
    {  
      base.ElementAdded(e);  
      CommentReferencesSubjects link = e.ModelElement as CommentReferencesSubjects;  
      Comment comment = link.Comment;  
      FlowElement subject = link.Subject;  
      Transaction current = link.Store.TransactionManager.CurrentTransaction;  
      // Don't want to run when we're just loading from file:  
      if (current.IsSerializing) return;  
      comment.Text = "Flow has " + subject.FlowTo.Count + " outgoing connections";  
    }  
  
  }  
  
  public partial class TaskRuleExampleDomainModel  
  {  
    protected override Type[] GetCustomDomainModelTypes()  
    {  
      List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
      types.Add(typeof(RoleRule));  
      return types.ToArray();  
    }  
  }  
  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Obslužné rutiny událostí rozšířit změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md)   
 [Umístění a velikost obrazce omezení BoundsRules](../modeling/boundsrules-constrain-shape-location-and-size.md)