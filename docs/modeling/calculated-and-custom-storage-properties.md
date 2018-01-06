---
title: "Úložiště počítaný a vlastní vlastnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, programming domain properties
ms.assetid: 42b785f9-2b0f-4f13-a6b4-246e5e0d477a
caps.latest.revision: "19"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: cf841cf70f092fb38adc42bfa6271c6c3aa121d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="calculated-and-custom-storage-properties"></a>Vypočtené a vlastní vlastnosti úložiště
Všechny vlastnosti domény v jazyce specifické pro doménu (DSL) lze zobrazit uživateli v diagramu a v Průzkumníku váš jazyk a je přístupný pomocí kódu programu. Vlastnosti se však lišit ve způsobu, jakým jsou uložena jejich hodnoty.  
  
## <a name="kinds-of-domain-properties"></a>Druhy vlastnosti domény  
 V definici DSL, můžete nastavit **druh** vlastnosti domény, jak je uvedeno v následující tabulce:  
  
|Typ vlastnosti domény|Popis|  
|--------------------------|-----------------|  
|**Standardní** (výchozí)|Vlastnost domain, který je uložený v *ukládání* a serializovaných do souboru.|  
|**Vypočítat**|Vlastnost domény jen pro čtení, není uložen v úložišti, která je vypočtená z jiných hodnot.<br /><br /> Například `Person.Age` vypočítat, z `Person.BirthDate`.<br /><br /> Je nutné zadat kód, který provádí výpočet. Obvykle vypočítat hodnotu od dalších vlastností domény. Můžete však také používat externí prostředky.|  
|**Vlastní úložiště**|Vlastnost domény, která se neuloží přímo v úložišti, ale může být get a set.<br /><br /> Je nutné zadat metody, které získat a nastavte hodnotu.<br /><br /> Například `Person.FullAddress` může být uložený v `Person.StreetAddress`, `Person.City`, a `Person.PostalCode`.<br /><br /> Můžete také přístup k externím prostředkům, například k získání a nastavení hodnoty z databáze.<br /><br /> Váš kód by neměl nastavit hodnoty v úložišti při `Store.InUndoRedoOrRollback` hodnotu true. V tématu [transakce a vlastní nastavení](#setters).|  
  
## <a name="providing-the-code-for-a-calculated-or-custom-storage-property"></a>Poskytuje kód pro vlastnost počítaná nebo vlastní úložiště  
 Pokud jste nastavili druh vlastnosti domény vypočítaná nebo vlastní úložiště, je nutné zadat metody přístupu. Při sestavování řešení zprávu o chybách zjistit, co je požadováno.  
  
#### <a name="to-define-a-calculated-or-custom-storage-property"></a>Chcete-li definovat počítané nebo vlastní úložiště vlastnost  
  
1.  V DslDefinition.dsl, vyberte vlastnost domain v diagramu nebo v **DSL Explorer**.  
  
2.  V **vlastnosti** nastavte **druhu** do **vypočítaná** nebo **vlastní úložiště**.  
  
     Ujistěte se, že jste si také nastavili jeho **typ** odpovídá vašim požadavkům.  
  
3.  Klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů **Průzkumníku řešení**.  
  
4.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
     Zobrazí se následující chybová zpráva: "*YourClass* neobsahuje definici pro Get*YourProperty*."  
  
5.  Dvakrát klikněte na chybovou zprávu.  
  
     Otevře se Dsl\GeneratedCode\DomainClasses.cs nebo DomainRelationships.cs. Výše volání zvýrazněná metoda komentář vyzve k zadání implementace pro Get*YourProperty*().  
  
    > [!NOTE]
    >  Tento soubor se generují z DslDefinition.dsl. Pokud chcete upravit tento soubor, změny budou ztraceny při příštím kliknutí na tlačítko **transformaci všech šablon**. Místo toho přidejte požadovaná metoda v samostatném souboru.  
  
6.  Vytvořit nebo otevřít soubor třídy do samostatné složky, například CustomCode\\*YourDomainClass*. cs.  
  
     Ujistěte se, že obor názvů je stejné jako generovaný kód.  
  
7.  V souboru třídy zápisu částečné implementace třídy domény. Ve třídě, zápis definici chybějící `Get` metoda, která se podobá následujícímu příkladu:  
  
    ```  
    namespace Company.FamilyTree  
    {  public partial class Person  
       {  int GetAgeValue()  
          { return System.DateTime.Today.Year - this.BirthYear; }  
    }  }  
    ```  
  
8.  Pokud nastavíte **druhu** k **vlastní úložiště**, budete také muset poskytnout `Set` metoda. Příklad:  
  
    ```  
    void SetAgeValue(int value)  
    { if (!Store.InUndoRedoOrRollback)  
        this.BirthYear =   
            System.DateTime.Today.Year - value; }  
    ```  
  
     Váš kód by neměl nastavit hodnoty v úložišti při `Store.InUndoRedoOrRollback` hodnotu true. V tématu [transakce a vlastní nastavení](#setters).  
  
9. Sestavení a spuštění řešení.  
  
10. Otestujte vlastnost. Ujistěte se, že zkusíte **vrátit zpět** a **vrátit**.  
  
##  <a name="setters"></a>Transakce a vlastní nastavení  
 Metoda Set vlastnost vlastní úložiště nemáte otevřete transakci, protože metoda je volána obvykle v rámci aktivní transakce.  
  
 Však může být sada metoda volána také pokud uživatel vyvolá zpět nebo znovu, nebo pokud transakce je vrácena zpět. Když <xref:Microsoft.VisualStudio.Modeling.Store.InUndoRedoOrRollback%2A> má hodnotu true, metodu Set měl chovat následujícím způsobem:  
  
-   Se nesmí měnit v úložišti, jako je například přiřazení hodnoty k vlastnosti jiné domény. Vrácení zpět manager bude nastavení jejich hodnot.  
  
-   Je však by měl aktualizovat všem externím prostředkům, jako je například databáze nebo obsah souboru nebo objekty mimo úložišti. Tím se zajistí, aby se zachovala v synchronism s hodnotami v úložišti.  
  
 Příklad:  
  
```  
void SetAgeValue(int value)  
{   
  // If we are in Undo, no changes to Store objects:  
  if (!this.Store.InUndoRedoOrRollback)  
  {   
    this.BirthYear = System.DateTime.Today.Year - value;   
  }  
  // But always update external objects:  
  System.IO.File.WriteAllText(AgeFile, value);  
}  
```  
  
 Další informace o transakcích najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
## <a name="see-also"></a>Viz také  
 [Navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Vlastnosti vlastnosti domény](../modeling/properties-of-domain-properties.md)   
 [Jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md)