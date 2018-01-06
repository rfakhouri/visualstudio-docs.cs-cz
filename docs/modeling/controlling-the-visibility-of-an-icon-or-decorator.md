---
title: "Řízení viditelnost ikony nebo Dekoratéra | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2697fd5d-b936-4b6b-b87b-be64825dc7a4
caps.latest.revision: "2"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 3a4e1927cd17a5cc86ed58565b53f04aeb6977a6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-the-visibility-of-an-icon-or-decorator"></a>Řízení viditelnosti ikony či dekorátoru
A *dekoratéra* je ikona nebo řádek textu, který se zobrazí na obrazce v jazyce specifické pro doménu (DSL). Můžete nastavit jsou zobrazeny dekoratéra a zmizí v závislosti na stavu vlastnosti v modelu. Například na obrazec představující osobu, může mít různé ikony, které jsou uvedeny v závislosti na osoby pohlaví, počet podřízených prvků a tak dále.  
  
## <a name="controlling-the-visibility-of-an-icon-or-decorator"></a>Řízení viditelnost ikony nebo dekoratéra  
 Následující postup předpokládá, již definovanou obrazce a její mapování na třídu domény. Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md).  
  
#### <a name="to-control-the-visibility-of-an-icon-or-text-decorator"></a>K řízení viditelnost dekoratéra na ikonu nebo text.  
  
1.  V diagramu definice DSL přidejte do třídy tvar ikony nebo dekoratéry textu, které se má zobrazit.  
  
    1.  Klikněte pravým tlačítkem na třídu tvaru, přejděte na **přidat**a potom klikněte na požadovaný typ dekoratéra.  
  
    2.  Nastavte dekoratéra **pozice** vlastnost. Více než jeden dekoratéra může mít stejné pozici. Například můžete mít ikony pro mužského a ženského sdílení stejné pozici.  
  
    3.  Nastavte **výchozí ikonu** vlastnost dekoratéra ikonu.  
  
2.  Vyberte map element diagram, který je šedé řádek mezi tvar třídy a třídy domény v diagramu DSL definice.  
  
3.  V okně podrobností DSL v **Dekoratéra mapy** vyberte dekoratéra. Například MaleDecorator.  
  
4.  Zkontrolujte **viditelnost filtru** pole.  
  
5.  Pokud je vlastnost domény, která by měla řídit zobrazení pro třídu okamžitou domény, ponechejte **cesta k filtru vlastnost** prázdné.  
  
     Jinak klikněte na rozevírací nabídku a přejděte do relace nebo třídy, kde se nachází vlastnost.  
  
    -   Abyste se vyhnuli zprávu o chybách, by neměl procházet vztahu označené jako "*" v nástroji navigace.  
  
6.  Nastavte **vlastnost filtru** pro vlastnost domain. Například pohlaví.  
  
7.  V **viditelnost položek** seznamu, přidejte hodnoty této vlastnosti domény, pro kterou má být zobrazena dekoratéra. Například muže.  
  
8.  Opakujte kroky pro každý ikonu.  
  
9. **Proveďte transformaci všech šablon**, sestavit a spustit a otevřete diagramu testovací.  
  
10. Při změně řízení hodnotu vlastnosti dekoratéry by měl zobrazit a zmizí.  
  
 Často budete chtít viditelnost kontrolován vzorec složitější než jednoduché sady hodnot. Například v tak, aby měl ikony závisí na počtu odkazy určitého typu nebo aby bylo závisí na na tom, zda je číslo v konkrétní rozsah. V takovém případě použijte následující postup.  
  
#### <a name="to-control-the-visibility-of-a-decorator-based-on-a-formula"></a>K řízení viditelnost dekoratéra podle vzorec.  
  
1.  Přidejte vlastnost počítané domény do domény třídy. V **vlastnosti** okno, nastavte následující hodnoty:  
  
     **IsBrowsable =**`False`**-skryje vlastnost od uživatele**   
  
     **Typ =**`Calculated`**– to znamená, že poskytnete kód, který počítá svou hodnotu**   
  
     **Název** například **DecoratorControl**  
  
     **Typ** = `Boolean`  
  
     Další informace najdete v tématu [vypočítaná a vlastní vlastnosti úložiště](../modeling/calculated-and-custom-storage-properties.md).  
  
2.  Zkontrolujte nové vlastnosti řízení dekoratéra zobrazení.  
  
    1.  Vyberte map element diagram, který je šedé řádek z domény třídy pro tvaru. V **DSL podrobnosti** okno, otevřete **DecoratorMap** kartě.  
  
    2.  Zkontrolujte **viditelnost filtru** pole.  
  
    3.  V **vlastnost filtru**, vyberte vlastnost ovládacího prvku **DecoratorControl**.  
  
    4.  V části **viditelnost položek**, zadejte `True`.  
  
3.  Klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů v Průzkumníku řešení.  
  
4.  Klikněte na tlačítko **sestavit řešení** na **sestavení** nabídky.  
  
5.  Dvakrát klikněte na zprávu o chybách, které se zobrazovaly: "*YourClass* neobsahuje definici pro GetDecoratorControlValue...".  
  
     Otevře se v Dsl\GeneratedCode\DomainClasses.cs textový editor. Nad zvýrazněná chybou je komentář, který budete vyzváni k přidání metody.  
  
6.  Všimněte si, obor názvů, třídy a metody které chybí.  Například Company.FamilyTree.Person.GetDecoratorControlValue().  
  
7.  V samostatném souboru kódu zapište definici třídu, která obsahuje metodu chybí. Příklad:  
  
    ```  
    namespace Company.FamilyTree  
    { partial class Person  
      { bool GetDecoratorControlValue()  
        {  
          return this.Children.Count > 0;  
    } } }  
    ```  
  
     Další informace o přizpůsobení modelu pomocí programu kódu najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
8.  Opětovné sestavení a spuštění řešení.  
  
## <a name="see-also"></a>Viz také  
 [Definování konektory a obrazců](../modeling/defining-shapes-and-connectors.md)   
 [Nastavení obrázek na pozadí v diagramu](../modeling/setting-a-background-image-on-a-diagram.md)   
 [Navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)