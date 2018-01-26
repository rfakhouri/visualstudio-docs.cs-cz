---
title: "Definování zásad uzamčení pro vytvoření jen pro čtení segmentů | Microsoft Docs"
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
ms.openlocfilehash: 6848f2c0b6c8d25fe7964fdb5519aa3f075bde57
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="defining-a-locking-policy-to-create-read-only-segments"></a>Definování zásady zamykání pro vytváření segmentů jen pro čtení
Rozhraní API neměnitelnosti [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vizualizace a modelování SDK umožňuje aplikaci zámku část nebo všechny model jazyka domény (DSL) tak, aby ho lze číst, ale nebyl změněn. Tato možnost jen pro čtení bylo možné použít, například tak, aby uživatel požádat kolegy opatřit poznámkami a zkontrolovat DSL model, ale můžete zakáže změnu původní.  
  
 Kromě toho, jak vytvořit DSL, můžete definovat *uzamčení zásad.* Uzamčení zásad definuje, které zámky jsou povolené, není povolené nebo povinné. Při publikování DSL, můžete například Doporučte třetích stran vývojáři rozšířit pomocí nové příkazy. Ale můžete také použít uzamčení zásady zabránit jejich změna stavu jen pro čtení zadaného součásti modelu.  
  
> [!NOTE]
>  Uzamčení zásady je možné obejít pomocí reflexe. Poskytuje jasné hranice pro vývojáře třetích stran, ale neposkytuje silné zabezpečení.  
  
 Další informace a ukázky jsou k dispozici v sadě Visual Studio [vizualizace a modelování SDK](https://code.msdn.microsoft.com/Visualization-and-Modeling-313535db) webu.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
  
## <a name="setting-and-getting-locks"></a>Nastavení a získání zámky.  
 Zámky můžete nastavit v úložišti, oddíl nebo jednotlivý prvek. Tento příkaz například zabránit odstranění element modelu a jeho vlastnosti bude také ochrany proti změnám:  
  
```  
using Microsoft.VisualStudio.Modeling.Immutability; ...  
element.SetLocks(Locks.Delete | Locks.Property);  
```  
  
 Ostatní hodnoty zámku lze zabránit změnám v relace, vytváření element, pohyb mezi oddílů a znovu řazení odkazy v roli.  
  
 Zámky platí pro akcí uživatele i na kód programu. Pokud se pokusí provést změnu, kód programu `InvalidOperationException` bude vyvolána. V operaci zpět nebo znovu se ignorují zámky.  
  
 Můžete zjistit, zda má element žádné zámek v dané sadě pomocí `IsLocked(Locks)` a aktuální sadu zámky v elementu můžete získat pomocí `GetLocks()`.  
  
 Můžete nastavit zámek bez použití transakce. Zámek databáze není součástí úložiště. Pokud nastavíte zámek v reakci na změnu hodnoty v úložišti, například v OnValueChanged, měli byste povolit změny, které jsou součástí operace vrácení zpět.  
  
 Tyto metody jsou rozšiřující metody, které jsou definovány v <xref:Microsoft.VisualStudio.Modeling.Immutability> oboru názvů.  
  
### <a name="locks-on-partitions-and-stores"></a>Zámky na oddíly a úložišť  
 Zámky. můžete také použít na oddíly a úložiště. Uzamčení, který je nastavený na oddíl se vztahuje na všechny elementy v oddílu. Tedy například následující příkaz bude zabránit všechny elementy v oddílu odstranění, bez ohledu na stav svých vlastních zámky. Nicméně jiné, jako zamkne `Locks.Property` stále může být nastavené na jednotlivé elementy:  
  
```  
partition.SetLocks(Locks.Delete);  
```  
  
 Uzamčení, které jsou nastavené v úložišti se vztahuje na všechny jeho prvky, bez ohledu na nastavení tohoto zámku na oddíly a elementy.  
  
### <a name="using-locks"></a>Pomocí zámky.  
 Můžete použít zámky provádění systémů, jako jsou následující příklady:  
  
-   Zakáže změny všech elementů a vztahů kromě těch, které představují komentáře. To umožňuje uživatelům opatřit poznámkami model bez provedení změn.  
  
-   Zakáže změny ve výchozím nastavení oddílu, ale povolit změny v diagramu oddílu. Uživatel může změna uspořádání diagramu, ale základní model nelze změnit.  
  
-   Zakáže změny do úložiště s výjimkou skupinu uživatelů, kteří jsou zaregistrovány v samostatné databáze. Pro ostatní uživatele jsou v diagramu a model jen pro čtení.  
  
-   Zakáže změny modelu, pokud je vlastnost typu Boolean diagramu nastavená na hodnotu true. Zadejte příkaz, který tuto vlastnost změnit. Díky tomu uživatelé, kteří budou neprovádějte změny omylem.  
  
-   Zakáže přidání a odstranění elementů a vztahů mezi jednotlivými určité třídy, ale povolit změny vlastností. To poskytuje uživatelům s pevnou formuláře, ve kterém se můžete vyplnit vlastnosti.  
  
## <a name="lock-values"></a>Hodnoty zámku  
 Zámky můžete nastavit na Store, oddíl nebo jednotlivé ModelElement. Zámky je `Flags` výčtu: můžete kombinovat jeho hodnoty pomocí ' &#124;'.  
  
-   Zámky objektu ModelElement, vždy zahrňte zámky svého oddílu.  
  
-   Zámky oddílu, vždy zahrňte zámky úložiště.  
  
 Nelze nastavit zámek pro oddíl nebo úložiště a současně zakázat zámku na jednotlivý prvek.  
  
|Hodnota|Znamená, pokud `IsLocked(Value)` platí|  
|-----------|------------------------------------------|  
|Žádné|Žádné omezení.|  
|Vlastnost|Vlastnosti domény elementů nelze změnit. To neplatí pro vlastnosti, které jsou generovány nástrojem roli třídy domény v relaci.|  
|Přidejte|Nelze vytvořit nové prvky a odkazy v oddílu, nebo uložit.<br /><br /> Nevztahuje se na `ModelElement`.|  
|Přesunutí|Element nelze přesouvat mezi oddílů, pokud `element.IsLocked(Move)` má hodnotu true, nebo pokud `targetPartition.IsLocked(Move)` hodnotu true.|  
|Odstranit|Element nelze odstranit, pokud je tato zámku nastavena elementu samotného, nebo na jeho prvky, ke kterému by odstranění rozšířit, jako je například vložené prvky a obrazců.<br /><br /> Můžete použít `element.CanDelete()` ke zjištění, zda lze odstranit element.|  
|Změna pořadí|Řazení odkazy na roleplayer nelze změnit.|  
|RolePlayer|Nelze změnit sadu odkazy, které pocházejí na tento element. Například nelze vložit nové prvky pod tímto elementem. Odkazy, pro který tento element je cílem to nemá vliv.<br /><br /> Tento element je odkaz, jeho zdrojové a cílové neovlivní.|  
|Všechny|Bitový operátor OR jiných hodnot.|  
  
## <a name="locking-policies"></a>Zásady uzamčení  
 Jako autor DSL, můžete definovat *uzamčení zásad*. Zásadu uzamčení moderates operaci SetLocks(), takže můžete zabránit konkrétní zámky nastavit nebo vyžádá, že konkrétní zámky musí být nastavena. Obvykle byste použili zásadu uzamčení k bránit uživatelům nebo vývojáři z omylem orgán je zamýšlené použití souboru DSL, stejným způsobem, že lze deklarovat proměnnou `private`.  
  
 Můžete také použít zásadu uzamčení nastavit zámky na všechny elementy závisí na typu elementu. Důvodem je, že `SetLocks(Locks.None)` je volána vždy, když je element nejprve vytvořit nebo deserializovat ze souboru.  
  
 Však nelze použít zásadu k odlišení zámky v elementu průběhu své životnosti. K dosažení tohoto vliv, měli byste použít volání `SetLocks()`.  
  
 Chcete-li definovat uzamčení zásady, budete muset:  
  
-   Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy>.  
  
-   Tato třída přidejte do služby, které jsou k dispozici prostřednictvím DocData z vaší DSL.  
  
### <a name="to-define-a-locking-policy"></a>K definování zásad uzamčení  
 <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy>má následující definice:  
  
```  
public interface ILockingPolicy  
{  
  Locks RefineLocks(ModelElement element, Locks proposedLocks);  
  Locks RefineLocks(Partition partition, Locks proposedLocks);  
  Locks RefineLocks(Store store, Locks proposedLocks);  
}  
```  
  
 Tyto metody jsou volány při volání Přišla žádost o `SetLocks()` na Store, oddíl nebo ModelElement. V každé metody jsou k dispozici navrhované sadu zámky. Můžete se vrátit sadě navrhovaných, nebo můžete přidat a odečtena zámky.  
  
 Příklad:  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Immutability;  
namespace Company.YourDsl.DslPackage // Change  
{  
  public class MyLockingPolicy : ILockingPolicy  
  {  
    /// <summary>  
    /// Moderate SetLocks(this ModelElement target, Locks locks)  
    /// </summary>  
    /// <param name="element">target</param>  
    /// <param name="proposedLocks">locks</param>  
    /// <returns></returns>  
    public Locks RefineLocks(ModelElement element, Locks proposedLocks)  
    {  
      // In my policy, users can never delete an element,  
      // and other developers cannot easily change that:  
      return proposedLocks | Locks.Delete);  
    }  
    public Locks RefineLocks(Store store, Locks proposedLocks)  
    {  
      // Only one user can change this model:  
      return Environment.UserName == "aUser"   
           ? proposedLocks : Locks.All;  
    }  
  
```  
  
 Abyste měli jistotu, že uživatelé můžou vždy odstraňovat prvky, i v případě, že jiný kód zavolá`SetLocks(Lock.Delete):`  
  
 `return proposedLocks & (Locks.All ^ Locks.Delete);`  
  
 Tak, aby zakázala změnit ve vlastnostech každý element MyClass:  
  
 `return element is MyClass ? (proposedLocks | Locks.Property) : proposedLocks;`  
  
### <a name="to-make-your-policy-available-as-a-service"></a>Aby vaše zásady dostupný jako služba  
 Ve vašem `DslPackage` projekt, přidejte nový soubor, který obsahuje kód, který se podobá následujícímu příkladu:  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Immutability;  
namespace Company.YourDsl.DslPackage // Change  
{   
  // Override the DocData GetService() for this DSL.  
  internal partial class YourDslDocData // Change  
  {  
    /// <summary>  
    /// Custom locking policy cache.  
    /// </summary>  
    private ILockingPolicy myLockingPolicy = null;  
  
    /// <summary>  
    /// Called when a service is requested.  
    /// </summary>  
    /// <param name="serviceType">Service requested</param>  
    /// <returns>Service implementation</returns>  
    public override object GetService(System.Type serviceType)  
    {  
      if (serviceType == typeof(SLockingPolicy)   
       || serviceType == typeof(ILockingPolicy))  
      {  
        if (myLockingPolicy == null)  
        {  
          myLockingPolicy = new MyLockingPolicy();  
        }  
        return myLockingPolicy;  
      }  
      // Request is for some other service.  
      return base.GetService(serviceType);  
    }  
}  
```
