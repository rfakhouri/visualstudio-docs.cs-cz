---
title: Obslužné rutiny události šíří změny mimo model
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, programming domain models
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: ba210e73d6adc3df2c4f584c5612d5642038ee8f
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="event-handlers-propagate-changes-outside-the-model"></a>Obslužné rutiny události šíří změny mimo model

Vizualizace a modelování SDK, můžete definovat obslužné rutiny událostí úložiště rozšíří změny na prostředky mimo úložiště, jako je například proměnné bez úložiště, soubory, modely v jiných úložišť nebo jiné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření. Obslužné rutiny událostí úložiště jsou spouštěny na konci transakce došlo k aktivační událost. Rovněž jsou prováděna v operaci zpět nebo znovu. Na rozdíl od úložiště pravidla jsou proto je nejvhodnější pro aktualizaci hodnoty, které jsou mimo úložišti události v úložišti. Na rozdíl od událostí rozhraní .NET, jsou obslužné rutiny událostí úložiště zaregistrované pro naslouchání na třídu: nemáte registraci samostatné obslužnou rutinu pro každou instanci. Další informace o tom, jak zvolit různé způsoby zpracování změn najdete v tématu [reakce na a šíření změny](../modeling/responding-to-and-propagating-changes.md).

Grafické prostor a jiných ovládacích prvků uživatelského rozhraní jsou příklady externím prostředkům, které může zpracovávat události v úložišti.

### <a name="to-define-a-store-event"></a>Chcete-li definovat úložiště událostí

1.  Vyberte typ události, které chcete monitorovat. Úplný seznam, podívejte se na vlastnosti <xref:Microsoft.VisualStudio.Modeling.EventManagerDirectory>. Každou vlastnost odpovídá typu události. Nejčastěji používané událostí, které typy jsou:

    -   `ElementAdded` -aktivuje, když element modelu, odkaz vztah, tvar nebo konektor je vytvořen.

    -   ElementPropertyChanged - aktivuje, když hodnota `Normal` mění vlastnost domain. Událost se aktivuje pouze v případě, že novém i starém hodnoty nejsou stejné. Událost nelze použít pro úložiště počítaný a vlastní vlastnosti.

         Ji nelze použít pro vlastnosti role, které odpovídají vztah odkazy. Místo toho použijte `ElementAdded` ke sledování relace domény.

    -   `ElementDeleted` -spustí po element modelu, vztah, tvar nebo konektor byl odstraněn. Pořád přístup k elementu hodnoty vlastností, ale bude mít žádné relace pro další prvky.

2.  Přidejte třídu definici *YourDsl *** DocData** v samostatném souboru kódu v **DslPackage** projektu.

3.  Zápis kódu událost jako metody, jako v následujícím příkladu. Může být `static`, pokud chcete získat přístup `DocData`.

4.  Přepsání `OnDocumentLoaded()` pro registraci obslužné rutiny. Pokud máte více než jednu obslužnou rutinu, můžete je zaregistrovat na stejném místě.

Umístění kód registrace není důležité. `DocView.LoadView()` je alternativního umístění.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Microsoft.VisualStudio.Modeling;

namespace Company.MusicLib
{
  partial class MusicLibDocData
  {
    // Register store events here or in DocView.LoadView().
    protected override void OnDocumentLoaded()
    {
      base.OnDocumentLoaded(); // Don't forget this.

      #region Store event handler registration.
      Store store = this.Store;
      EventManagerDirectory emd = store.EventManagerDirectory;
      DomainRelationshipInfo linkInfo = store.DomainDataDirectory
          .FindDomainRelationship(typeof(ArtistAppearsInAlbum));
      emd.ElementAdded.Add(linkInfo,
          new EventHandler<ElementAddedEventArgs>(AddLink));
      emd.ElementDeleted.Add(linkInfo,
          new EventHandler<ElementDeletedEventArgs>(RemoveLink));

      #endregion Store event handlers.
    }

    private void AddLink(object sender, ElementAddedEventArgs e)
    {
      ArtistAppearsInAlbum link = e.ModelElement as ArtistAppearsInAlbum;
      if (link != null)
            ExternalDatabase.Add(link.Artist.Name, link.Album.Title);
    }
    private void RemoveLink(object sender, ElementDeletedEventArgs e)
    {
      ArtistAppearsInAlbum link = e.ModelElement as ArtistAppearsInAlbum;
      if (link != null)
            ExternalDatabase.Delete(link.Artist.Name, link.Album.Title);
    }
  }
}
```

## <a name="use-events-to-make-undoable-adjustments-in-the-store"></a>Používání událostí s úpravami vrátit v úložišti

Události v úložišti obvykle se nepoužívají pro přenos změn v úložišti, protože obslužná rutina události spustí po potvrzené transakce. Místo toho by použít pravidlo úložiště. Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).

Ale můžete použít obslužné rutiny události provést další aktualizace do úložiště, pokud má uživatel moci vrátit další aktualizace odděleně od původního událostí. Předpokládejme například, že malá písmena jsou obvykle konvence pro alb. Můžete napsat obslužnou rutinu události úložiště, která vyřeší nadpis na malá písmena, poté, co uživatel má zadali velkými písmeny. Ale uživatel může použít příkaz Undo zrušit oprava, obnovení velkých písmen. Druhý vrácení zpět by odebrat uživatele změnit.

Naopak pokud jste napsali pravidlo úložiště pro stejnou věc udělat, změna uživatele a opravu by v rámci jedné transakce, tak, aby uživatel nelze vrátit zpět úpravy bez ztráty původní změny.

```csharp
partial class MusicLibDocView
{
    // Register store events here or in DocData.OnDocumentLoaded().
    protected override void LoadView()
    {
      /* Register store event handler for Album Title property. */
      // Get reflection data for property:
      DomainPropertyInfo propertyInfo =
        this.DocData.Store.DomainDataDirectory
        .FindDomainProperty(Album.TitleDomainPropertyId);
      // Add to property handler list:
      this.DocData.Store.EventManagerDirectory
        .ElementPropertyChanged.Add(propertyInfo,
        new EventHandler<ElementPropertyChangedEventArgs>
             (AlbumTitleAdjuster));

      /*
      // Alternatively, you can set one handler for
      // all properties of a class.
      // Your handler has to determine which property changed.
      DomainClassInfo classInfo = this.Store.DomainDataDirectory
           .FindDomainClass(typeof(Album));
      this.Store.EventManagerDirectory
          .ElementPropertyChanged.Add(classInfo,
        new EventHandler<ElementPropertyChangedEventArgs>
             (AlbumTitleAdjuster));
       */
      return base.LoadView();
    }

// Undoable adjustment after a property is changed.
// Method can be static since no local access.
private static void AlbumTitleAdjuster(object sender,
         ElementPropertyChangedEventArgs e)
{
  Album album = e.ModelElement as Album;
  Store store = album.Store;

  // We mustn't update the store in an Undo:
  if (store.InUndoRedoOrRollback
      || store.InSerializationTransaction)
      return;

  if (e.DomainProperty.Id == Album.TitleDomainPropertyId)
  {
    string newValue = (string)e.NewValue;
    string lowerCase = newValue.ToLowerInvariant();
    if (!newValue.Equals(lowerCase))
    {
      using (Transaction t = store.TransactionManager
            .BeginTransaction("adjust album title"))
      {
        album.Title = lowerCase;
        t.Commit();
      } // Beware! This could trigger the event again.
    }
  }
  // else other properties of this class.
}
```

Pokud píšete událost, která aktualizuje úložiště:

-   Použití `store.InUndoRedoOrRollback` vyhnout se provádění změn modelu elementům ve vrácení zpět. Správce transakcí všechno nastaví v úložišti zpět do původního stavu.

-   Použití `store.InSerializationTransaction` vyhnout se provádění změn při načítání modelu ze souboru.

-   Změny způsobí, že další události, které mají být aktivována. Zajistěte, aby se zabránilo nekonečné smyčce.

## <a name="store-event-types"></a>Ukládání typů událostí

Každý typ události odpovídá kolekci v Store.EventManagerDirectory. Můžete přidat nebo odebrat obslužné rutiny událostí kdykoli, ale je obvykle je přidat při načtení dokumentu.

|`EventManagerDirectory` Název vlastnosti|Spuštěna při|
|-------------------------------------------|-------------------|
|ElementAdded|Instance třídy domény, relace domény, tvaru, konektoru nebo diagramu se vytvoří.|
|ElementDeleted|Element modelu byla odebrána z adresáře element úložiště a již není zdroje nebo cíle žádné relace. Element nebude odstraněn z paměti, ale se uchovávají v případě budoucí vrácení zpět.|
|ElementEventsBegun|Volá se na konci vnější transakci.|
|ElementEventsEnded|Voláno, když byly zpracovány všechny další události.|
|ElementMoved|Element modelu přesunula z oddílu jedno úložiště do druhého.<br /><br /> To není v relaci do umístění souboru obrazce v diagramu.|
|ElementPropertyChanged|Hodnota vlastnosti domény se změnila. Tím se spustí pouze v případě, že nerovné starými a novými hodnotami.|
|RolePlayerChanged|Jednu ze dvou rolí (končí) relace odkazuje nového elementu.|
|RolePlayerOrderChanged|V roli s násobností větší než 1 došlo ke změně pořadí odkazů.|
|TransactionBeginning||
|TransactionCommitted||
|TransactionRolledBack||

## <a name="see-also"></a>Viz také

- [Reagování na změny a šíření změn](../modeling/responding-to-and-propagating-changes.md)
- [Ukázkový kód: okruh diagramy](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]