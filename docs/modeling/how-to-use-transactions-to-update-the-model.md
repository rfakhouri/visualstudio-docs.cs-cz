---
title: 'Postupy: Používání transakcí k aktualizaci modelu'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 590c355d391516def8f65579e5346281e335eea8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-transactions-to-update-the-model"></a>Postupy: Používání transakcí k aktualizaci modelu
Transakce, ujistěte se, že změny, které byly provedeny do úložiště jsou považovány za skupinu. Změny, které jsou seskupené, může být potvrzena nebo vrácena zpět jako na jednu jednotku.

 Vždy, když kód programu změní, přidá nebo odstraní libovolný element v úložišti [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vizualizace a modelování SDK, je nutné provést v transakci. Musí být aktivní instance <xref:Microsoft.VisualStudio.Modeling.Transaction> přidružený k obchodu, když se stane změnu. To platí pro všechny elementy modelu, relace, tvarů, diagramy a jejich vlastnosti.

 Tento mechanismus transakce umožňuje vyhnout se nekonzistentní stav. Pokud dojde k chybě během transakce, všechny změny budou vráceny. Pokud uživatel provede příkaz vrácení zpět, každou poslední transakci je považována za jediném kroku. Uživatele nelze vrátit zpět částí ke změnám, pokud je explicitně umístit do samostatné transakce.

## <a name="opening-a-transaction"></a>Otevírání transakce.
 Je nejvhodnější metody řízení transakce s `using` příkaz uzavřena v `try...catch` příkaz:

```
Store store; ...
try
{
  using (Transaction transaction =
    store.TransactionManager.BeginTransaction("update model"))
    // Outermost transaction must always have a name.
  {
    // Make several changes in Store:
    Person p = new Person(store);
    p.FamilyTreeModel = familyTree;
    p.Name = "Edward VI";
    // end of changes to Store

    transaction.Commit(); // Don't forget this!
  } // transaction disposed here
}
catch (Exception ex)
{
  // If an exception occurs, the Store will be
  // rolled back to its previous state.
}
```

 Pokud výjimku, která zabraňuje konečné `Commit()` spadá změn, úložišti se resetuje do předchozího stavu. To umožňuje zajistit, že chyby nenechávejte modelu v nekonzistentním stavu.

 Můžete vytvořit libovolný počet změny v jedné transakci. Můžete otevřít nové transakce uvnitř aktivní transakce. Vnořené transakce musí potvrzení nebo vrácení před koncem obsahující transakce. Další informace najdete v tématu na příklad <xref:Microsoft.VisualStudio.Modeling.Transaction.TransactionDepth%2A> vlastnost.

 Chcete-li provedené změny trvalé, měli byste `Commit` transakce předtím, než je zrušen. Pokud dojde k výjimce, která není zachycena uvnitř transakce, úložišti se resetuje do stavu před změny.

## <a name="rolling-back-a-transaction"></a>Vrácení transakce zpět
 Chcete-li zajistit, aby zůstává v úložišti, a vrátí do stavu před transakce, můžete použít některý z těchto svoji:

1.  Vyvolejte výjimku, která není zachycena v oboru transakce.

2.  Explicitně vrácení transakce:

    ```
    this.Store.TransactionManager.CurrentTransaction.Rollback();
    ```

## <a name="transactions-do-not-affect-non-store-objects"></a>Transakce neovlivní bez úložiště objektů
 Transakce pouze řídí stav úložiště. Nelze vrátit zpět částečné změny, které byly provedeny na externí položek, jako jsou soubory, databáze nebo objekty, které mají deklarovat s běžné typy mimo definici DSL.

 Pokud výjimku může nechat taková změna nekonzistentní s úložištěm, by se měl zabývat tato možnost v obslužná rutina výjimky. Jedním ze způsobů, abyste měli jistotu, že externím prostředkům zůstaly synchronizované s objekty úložiště je spojit každý externí objekt pro element v úložišti pomocí obslužné rutiny událostí. Další informace najdete v tématu [událost obslužné rutiny rozšíří změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md).

## <a name="rules-fire-at-the-end-of-a-transaction"></a>Ještě efektivněji pravidla na konci transakce.
 Na konci transakce jsou před uvolněním transakce aktivována pravidla připojená k elementů v úložišti. Každé pravidlo je metoda, která se použije pro element modelu, který byl změněn. Například "oprava" pravidel, které aktualizovat stav obrazce, pokud došlo ke změně jeho element modelu a obrazce vytvořit při element modelu. Neexistuje žádné zadaného pořadí. Změny provedené pomocí pravidla můžete aktivovat jiné pravidlo.

 Můžete definovat vlastní pravidla. Další informace o pravidlech, najdete v tématu [reakce na a šíření změny](../modeling/responding-to-and-propagating-changes.md).

 Pravidla neaktivovat poté, co byla operace vrácení zpět, operaci znovu nebo příkaz vrácení zpět.

## <a name="transaction-context"></a>Kontext transakce
 Každou transakci má slovník, ve kterém můžete uložit všechny informace, které chcete:

 `store.TransactionManager`

 `.CurrentTransaction.TopLevelTransaction`

 `.Context.Add(aKey, aValue);`

 To je zvlášť vhodné pro přenos informací mezi pravidla.

## <a name="transaction-state"></a>Stav transakce
 V některých případech, které potřebujete, aby se zabránilo šíření změnu, pokud je tato změna způsobeno zrušení nebo při opětovném provádění transakcí. To může nastat například když napíšete obslužnou rutinu hodnotu vlastnosti, která můžete aktualizovat jinou hodnotu v úložišti. Protože operace zpět se obnoví všechny hodnoty v úložišti do předchozího stavu, není nutné výpočetní aktualizovanými hodnotami. Pomocí tohoto kódu:

```
if (!this.Store.InUndoRedoOrRollback) {...}
```

 Pravidla můžete aktivovat, pokud úložiště je právě načítán původně ze souboru. Abyste se vyhnuli, reagovat na tyto změny, použijte:

```
if (!this.Store.InSerializationTransaction) {...}

```