---
title: Migrace rozšiřitelnost návrháře XAML
ms.date: 04/17/2019
ms.topic: conceptual
author: lutzroeder
ms.author: lutzr
manager: jillfra
monikerRange: vs-2019
ms.openlocfilehash: f83c40a67dc36301816b2384242d790a9f776044
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63447337"
---
# <a name="xaml-designer-extensibility-migration"></a>Migrace rozšiřitelnost návrháře XAML

Od verze Visual Studio 2019 verze 16.1 jako verze public preview, Návrhář XAML podporuje dvě různé architektury: architektura návrháře izolace a novější architekturu surface izolace. Tohoto přechodu je architektura je vyžadovaný jako podpora cílového moduly runtime, který nemůže být hostovaná v procesu rozhraní .NET Framework. Přechod na povrchu izolace architektura přináší změny způsobující chyby modelu rozšíření třetích stran. Tento článek popisuje, jak změny.

**Návrháře izolace** používá WPF designer pro projekty, které se zaměřují na rozhraní .NET Framework a podporuje *. design.dll* rozšíření. Uživatelský kód, ovládacího prvku knihovny a rozšíření třetích stran jsou načteny v externím procesu (*XDesProc.exe*) spolu s skutečné návrháře kódu a návrháře panelů.

**Zařízení Surface izolace** používá Návrhář UPW. Také se používá ve WPF designer pro projekty, které cílí na .NET Core. Zařízení surface izolovaně knihovny kódu a ovládací prvek jediným uživatelem načteným v samostatném procesu, návrháře a jeho panelů jsou načteny v procesu Visual Studio (*DevEnv.exe*). Modul runtime používá se ke spuštění kódu a ovládacího prvku knihovny uživatele se liší od, který používá rozhraní .NET Framework pro skutečné návrháře a kód třetích stran rozšiřitelnosti.

![rozšiřitelnost architekturu migrace](media/xaml-designer-extensibility-migration-architecture.png)

Z důvodu tohoto přechodu je architektura se načtou do stejně jako na knihovny třetích stran ovládací prvek již rozšíření třetích stran. Rozšíření můžete už mají přímé závislosti v knihovnách ovládací prvek nebo přímý přístup k objekty modulu runtime. Rozšíření, které byly dříve vytvořeny pro architekturu pomocí návrháře izolace *Microsoft.Windows.Extensibility.dll* rozhraní API musí migrovat na nový přístup pro práci s architekturou surface izolace. V praxi existující rozšíření muset byl zkompilován proti nová rozhraní API sestavení rozšíření. Přístup k prvku za běhu typy prostřednictvím [typeof](/dotnet/csharp/language-reference/keywords/typeof) nebo instancí modulu runtime musí být nahrazen nebo odebrat, protože ovládací prvek knihovny jsou nyní úlohy načítány v jiném procesu.

## <a name="new-extensibility-api-assemblies"></a>Nová rozšiřitelnost rozhraní API sestavení

Nová rozhraní API sestavení rozšíření jsou podobná stávající rozhraní API sestavení rozšíření, ale použijte jiné schéma pojmenování, aby bylo možné odlišit. Podobně názvy oborů názvů změnili tak, aby odrážela nové názvy sestavení.

| Návrháře izolaci sestavení rozhraní API            | Izolace povrchu API sestavení                       |
|:------------------------------------------ |:---------------------------------------------------- |
| Microsoft.Windows.Design.Extensibility.dll | Microsoft.VisualStudio.DesignTools.Extensibility.dll |
| Microsoft.Windows.Design.Interaction.dll   | Microsoft.VisualStudio.DesignTools.Interaction.dll   |

## <a name="new-file-extension-and-discovery"></a>Novou příponu souboru a zjišťování

Namísto použití *. design.dll* souboru rozšíření, nové surface rozšíření se dají zjistit pomocí odkazu *. designtools.dll* příponu souboru. *. design.dll* a *. designtools.dll* rozšíření může existovat ve stejném *návrhu* podsložky.

Když jsou kompilovány knihoven třetích stran ovládacího prvku pro skutečné cílový modul runtime (.NET Core nebo UPW), *. designtools.dll* rozšíření by měl vždy být zkompilován jako sestavení rozhraní .NET Framework.

## <a name="decouple-attribute-tables-from-runtime-types"></a>Oddělit atribut tabulek z typů modulu runtime

Model rozšiřitelnosti surface izolace neumožňuje rozšíření záviset na knihovnách skutečný ovládací prvek, a proto rozšíření nemohou odkazovat na typy z knihovny ovládacích prvků. Například *MyLibrary.designtools.dll* by neměl být závislý na *MyLibrary.dll*.

Při registraci metadat pro typy prostřednictvím atributu tabulky byly nejběžnější těchto závislostí. Typy kódu rozšíření, která odkazuje na knihovny ovládacích prvků přímo prostřednictvím [typeof](/dotnet/csharp/language-reference/keywords/typeof) pomocí typu založeného na řetězec názvů nahrazeny v nových rozhraní API:

```csharp
using Microsoft.VisualStudio.DesignTools.Extensibility.Metadata;
using Microsoft.VisualStudio.DesignTools.Extensibility.Features;
using Microsoft.VisualStudio.DesignTools.Extensibility.Model;

[assembly: ProvideMetadata(typeof(AttributeTableProvider))]

public class AttributeTableProvider : IProvideAttributeTable
{
  public AttributeTable AttributeTable
  {
    get
    {
      AttributeTableBuilder builder = new AttributeTableBuilder();
      builder.AddCustomAttributes("MyLibrary.MyControl", new DescriptionAttribute(Strings.MyControlDescription);
      builder.AddCustomAttributes("MyLibrary.MyControl", new FeatureAttribute(typeof(MyControlDefaultInitializer));
      return builder.CreateTable();
    }
  }
}
```

## <a name="feature-providers-and-model-api"></a>Poskytovatelé funkce a rozhraní API pro Model

Poskytovatelé funkce jsou implementované v sestavení rozšíření a načten v procesu sady Visual Studio. `FeatureAttribute` budou dál odkazovat funkce poskytovatele typů přímo pomocí [typeof](/dotnet/csharp/language-reference/keywords/typeof).

Protože funkce poskytovatelé jsou nyní úlohy načítány v procesu, která se liší od knihovny kódu a řízení skutečné modulu runtime, nebudou mít přístup přímo k objekty modulu runtime. Místo toho musí být všechny takové interakce převeden používat odpovídající rozhraní API založené na modelu. Rozhraní API modelu byla aktualizována a přístup k <xref:System.Type> nebo <xref:System.Object> je buď již nejsou k dispozici nebo se nahradil údajem `TypeIdentifier` a `TypeDefinition`.

`TypeIdentifier` představuje řetězec bez určení typu název sestavení. A `TypeIdenfifier` lze převést na `TypeDefinition` dotazů na další informace o typu. `TypeDefinition` nelze uložit do mezipaměti instancí do kódu rozšíření.

```csharp
TypeDefinition type = ModelFactory.ResolveType(
    item.Context, new TypeIdentifier("MyLibrary.MyControl"));
TypeDefinition buttonType = ModelFactory.ResolveType(
    item.Context, new TypeIdentifier("System.Windows.Controls.Button"));
if (type != null && buttonType != type.IsSubclassOf(buttonType))
{
}
```

Rozhraní API odebráno ze sady možností izolace rozšiřitelnost rozhraní API:

* `ModelFactory.CreateItem(EditingContext context, object item)`
* `ViewItem.PlatformObject`
* `ModelProperty.DefaultValue`

Rozhraní API, která pomocí `TypeIdentifier` místo <xref:System.Type>:

* `ModelFactory.CreateItem(EditingContext context, Type itemType, params object[] arguments)`
* `ModelFactory.CreateItem(EditingContext context, Type itemType, CreateOptions options, params object[] arguments)`
* `ModelFactory.CreateStaticMemberItem(EditingContext context, Type type, string memberName)`
* `ViewItem.ItemType`
* `ModelEvent.EventType`
* `ModelEvent.IsEventOfType(Type type)`
* `ModeItem.IsItemOfType(Type type)`
* `ModelParent.CanParent(EditingContext context, ModelItem parent, Type childType)`
* `ModelParent.FindParent(EditingContext context, Type childType, ModelItem startingItem)`
* `ModelParent.FindParent(Type childType, GestureData gestureData)`
* `ModelProperty.IsPropertyOfType(Type type)`
* `ParentAdpater.CanParent(ModelItem parent, Type childType)`
* `ParentAdapter.RedirectParent(ModelItem parent, Type childType)`

Rozhraní API, která pomocí `TypeIdentifier` místo <xref:System.Type> a už nebude podporovat argumenty konstruktoru:

* `ModelFactory.CreateItem(EditingContext context, TypeIdentifier typeIdentifier, params object[] arguments)`
* `ModelFactory.CreateItem(EditingContext context, TypeIdentifier typeIdentifier, CreateOptions options, params object[] arguments)`

Rozhraní API, která pomocí `TypeDefinition` místo <xref:System.Type>:

* `ModelFactory.ResolveType(EditingContext context, TypeIdentifier typeIdentifier)`
* `ValueTranslationService.GetProperties(Type itemType)`
* `ValueTranslationService.HasValueTranslation(Type itemType, PropertyIdentifier identifier)`
* `ValueTranslationService.TranslatePropertyValue(Type itemType, ModelItem item, PropertyIdentifier identifier, object value)`
* `ModelService.Find(ModelItem startingItem, Type type)`
* `ModelService.Find(ModelItem startingItem, Predicate<Type> match)`
* `ModelItem.ItemType`
* `ModelProperty.AttachedOwnerType`
* `ModelProperty.PropertyType
* `FeatureManager.CreateFeatureProviders(Type featureProviderType, Type type)`
* `FeatureManager.CreateFeatureProviders(Type featureProviderType, Type type, Predicate<Type> match)`
* `FeatureManager.InitializeFeatures(Type type)`
* `FeatureManager.GetCustomAttributes(Type type, Type attributeType)`
* `AdapterService.GetAdapter<TAdapterType>(Type itemType)`
* `AdapterService.GetAdapter(Type adapterType, Type itemType)`

Rozhraní API, která pomocí `ModelItem` místo <xref:System.Object>:

* `ModelItemCollection.Insert(int index, object value)`
* `ModelItemCollection.Remove(object value)`
* `ModelItemDictionary.Add(object key, object value)`
* `ModelItemDictionary.ContainsKey(object key)`
* `ModelItemDictionary.Remove(object key)`
* `ModelItemDictionary.TryGetValue(object key, out ModelItem value)`

Primitivní typy, jako jsou známé `int`, `string`, nebo `Thickness` lze předat do rozhraní API modelu jako instance rozhraní .NET Framework a se převedou na odpovídající objekt v cílovém procesu modulu runtime. Příklad:

```csharp
using Microsoft.VisualStudio.DesignTools.Extensibility.Features;
using Microsoft.VisualStudio.DesignTools.Extensibility.Model;

public class MyControlDefaultInitializer : DefaultInitializer
{
  public override void InitializeDefaults(ModelItem item)
  {
    item.Properties["Width"].SetValue(800d);
    base.InitializeDefaults(item);
  }
}
```

## <a name="limited-support-for-designdll-extensions"></a>Omezená podpora. design.dll rozšíření

Pokud existuje *. designtools.dll* zjištěnou rozšíření knihovny ovládacích prvků, načtení první a zjišťování pro *. design.dll* rozšíření se přeskočí.

Pokud ne *. designtools.dll* rozšíření jsou k dispozici ale *. design.dll* nalezeno rozšíření, že služba jazyka XAML, pokusí se načíst toto sestavení se extrahovat informace o atributu tabulky pro podporu základní editor a vlastnost inspektoru scénáře. Tento mechanismus je omezený v oboru. Neumožňuje načítání rozšíření návrháře izolace ke spuštění funkce poskytovatele, ale může poskytnout základní podporu pro existující knihovny ovládacího prvku WPF.
