---
title: Přizpůsobení a rozšíření jazyka specifického pro doménu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, creating solutions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e6a6bb74d4b4a4fc93c4cf0425c1fe06b9f290a4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-and-extending-a-domain-specific-language"></a>Přizpůsobení a rozšíření jazyka specifického pro doménu
Visual Studio modelování a vizualizace SDK (VMSDK) poskytuje několik úrovní, ve kterém můžete definovat modelování nástroje:

1.  Definujte jazyk specifické pro doménu (DSL) pomocí definice DSL diagramu. Dokáže rychle vytvořit DSL s graficky zápis, čitelné podoby XML a základní nástroje, které jsou požadovány pro generování kódu a další artefaktů.

     Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md).

2.  DSL upřesnit pomocí dalších pokročilých funkcí DSL definice. Například můžete nastavit další odkazy zobrazí, když uživatel vytváří elementu. Tyto postupy jsou většinou dosáhnout v definici DSL a některé vyžadovat zadání několika řádků kódu programu.

3.  Rozšíření vaší nástroje pro modelování pomocí kódu programu. VMSDK je navrženo konkrétně k snadno integrovat kód, který se vygeneruje z definice DSL rozšíření.  Další informace najdete v tématu [psaní kódu jazyka domény sestavit si](../modeling/writing-code-to-customise-a-domain-specific-language.md).

> [!NOTE]
>  Po aktualizaci souborů definic DSL, nezapomeňte znovu klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů Průzkumníka řešení, než znovu sestavit vaše řešení.

##  <a name="customShapes"></a> V této části

|K dosažení tohoto efektu|Najdete v tomto tématu|
|----------------------------|-------------------------|
|Povolte uživatelům nastavit barvy a stylu vlastnosti obrazce.|Klikněte pravým tlačítkem na třídu tvar nebo konektor, přejděte na **přidat zveřejněné**a klikněte na položku.<br /><br /> V tématu [přizpůsobení prezentace v diagramu](../modeling/customizing-presentation-on-the-diagram.md).|
|Různé třídy element modelu vypadat podobně jako v diagramu, sdílení vlastnosti, například počáteční výška a šířka, barva, popisy tlačítek.|Použití dědičnosti mezi tvary nebo konektor třídy. Mapování mezi odvozené tvarů a domény odvozené třídy dědí podrobnosti mapování z rodičů.<br /><br /> Nebo mapování tříd jinou doménu na stejnou třídu tvaru.|
|Třídu modelu element se zobrazí při různých tvarů kontexty.|Map – třída více než jeden tvar do stejné domény třídy. Při sestavování řešení, postupujte podle zprávy o chybách a poskytnout požadovaný kódu se rozhodnout, jaké tvar, který má použít.|
|Barva obrazce nebo další funkce, jako je například písmo označují aktuální stav.|V tématu [aktualizace tvarů a konektory tak, aby odrážela modelu](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md).<br /><br /> Vytvoření pravidla, která aktualizuje vystavené vlastnosti. V tématu [pravidla rozšíření změn v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).<br /><br /> Nebo použijte OnAssociatedPropertyChanged() aktualizovat-zveřejněné funkce jako dvojice šipek, které odkaz nebo písma.|
|Ikona ve tvaru změny k označení stavu.|V okně podrobností DSL nastavte viditelnost dekoratéra mapování. Vyhledejte několik dekoratéry bitové kopie na stejné pozici. V tématu [aktualizace tvarů a konektory tak, aby odrážela modelu](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md).<br /><br /> Nebo přepsat `ImageField.GetDisplayImage()`. Najdete v příkladu v <xref:Microsoft.VisualStudio.Modeling.Diagrams.ImageField>.|
|Nastavit obrázek pozadí na libovolného tvaru|Přepsání InitializeInstanceResources() přidat ukotvené ImageField. V tématu [přizpůsobení prezentace v diagramu](../modeling/customizing-presentation-on-the-diagram.md).|
|K žádné hloubky vnoření obrazce|Nastavte rekurzivního vložení stromu. Definujte BoundsRules tak, aby obsahovala obrazce. V tématu [přizpůsobení prezentace v diagramu](../modeling/customizing-presentation-on-the-diagram.md).|
|Připojte konektory na pevnou bodů na hranici elementu.|Definujte vložené terminálu prvky reprezentována malé porty v diagramu. Použijte BoundsRules opravit porty na místě. Viz ukázka Diagram okruh v [vizualizace a modelování SDK](http://go.microsoft.com/fwlink/?LinkID=186128).|
|Textové pole zobrazí hodnotou odvozenou od ostatních hodnot.|Mapování dekoratéra textu na vlastnosti domény vypočítaná nebo vlastní úložiště. Další informace najdete v tématu [vypočítaná a vlastní vlastnosti úložiště](../modeling/calculated-and-custom-storage-properties.md).|
|Rozšíření změn mezi elementů modelu, nebo mezi tvary|V tématu [ověření v jazyce specifické pro doménu](../modeling/validation-in-a-domain-specific-language.md).|
|Rozšíření změn k prostředkům, například jiné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření mimo úložišti.|V tématu [obslužné rutiny událostí rozšířit změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md).|
|Vlastnost okně se zobrazí vlastnosti související elementu.|Nastavte vlastnost předávání. V tématu [přizpůsobení okna vlastnosti](../modeling/customizing-the-properties-window.md).|
|Kategorie vlastností|Okno vlastností je rozdělené do částí názvem kategorie. Nastavte **kategorie** vlastností vaší domény. Vlastnosti se stejným názvem kategorie se zobrazí ve stejném oddílu. Můžete také nastavit **kategorie** vztah role.|
|Řízení přístupu uživatelů k vlastnosti domény|Nastavit **je Procházet** hodnotu false, chcete-li zabránit zobrazování v okně vlastností v době běhu vlastnost domain. Stále ji můžete namapovat dekoratéry text.<br /><br /> **Je jen pro čtení uživatelského rozhraní** zabrání uživatelům změnit vlastnost domain.<br /><br /> Program přístup pro vlastnost domain nemá vliv.|
|Změňte název, ikona a viditelnost uzlů v Průzkumníku modelu vaší DSL.|V tématu [přizpůsobení Průzkumníka modelu](../modeling/customizing-the-model-explorer.md).|
|Povolit kopírování, vyjímání a vkládání|Nastavte **povolit kopírování vkládání** vlastnost **Editor** uzlu v Průzkumníku DSL.|
|Zkopírujte referenční odkazy a jejich cíle vždy, když se zkopíruje elementu. Zkopírujte například komentáře připojené k položce.|Nastavte **rozšíří kopie** vlastnost zdroje role (představované řádku na jedné straně relace domény v diagramu definice DSL).<br /><br /> Psaní kódu pro přepsání ProcessOnCopy k dosažení složitější účinky.<br /><br /> V tématu [přizpůsobení chování kopie](../modeling/customizing-copy-behavior.md).|
|Odstranit, Nadřadit nebo znovu připojit související prvky, když se odstraní. element.|Nastavte **rozšíří odstranit** hodnotu vztah role. Pro složitější důsledky přepíší `ShouldVisitRelationship` a `ShouldVisitRolePlayer` metody v `MyDslDeleteClosure` třídy, které jsou definované v **DomainModel.cs**<br /><br /> V tématu [přizpůsobení chování při odstranění](../modeling/customizing-deletion-behavior.md)|
|Zachovejte tvar rozložení a vzhled na kopírování a přetáhněte jej.|Přidat konektory a obrazců do zkopírovaný `ElementGroupPrototype`. Je nejvhodnější metodu pro přepsání `ElementOperations.CreateElementGroupPrototype()`<br /><br /> V tématu [přizpůsobení chování kopie](../modeling/customizing-copy-behavior.md).|
|Vkládání obrazců do zvoleného umístění, jako je například aktuálním umístěním kurzoru.|Přepsání `ClipboardCommandSet.ProcessOnCopy()` používat konkrétní umístění verzi `ElementOperations.Merge().` najdete v části [přizpůsobení chování kopie](../modeling/customizing-copy-behavior.md).|
|Vytvořte další odkazy na vložení|Override ClipboardCommandSet.ProcessOnPasteCommand()|
|Povolit přetažení z tohoto diagramu, ostatní DSL, linky a Windows elementy|V tématu [postupy: přidání obslužné rutiny a přetažení](../modeling/how-to-add-a-drag-and-drop-handler.md)|
|Povolit tvar nebo nástroj, který se přetáhli podřízené obrazce, jako je port, jako kdyby byly přetáhli nadřazený.|U třídy cílový objekt, předávání vynechaných objektu do nadřazené definujte sloučení direktivu Element. V tématu [přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md).|
|Povolit nástroj být přetáhli obrazce a další odkazy tvaru nebo nebo objekty vytvořené. Chcete-li například povolit komentář, který má být přetažen na položku, ke kterému má být propojena.|Definovat sloučení direktivu Element u třídy cíle domény a odkazy, které má být vygenerován. V případech, komplexní můžete přidat vlastní kód. V tématu [přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md).|
|Vytvořte skupinu elementů pomocí jednoho nástroje. Například součást s pevnou sadu portů.|Potlačí metodu inicializace sady nástrojů v ToolboxHelper.cs. Vytvořte Element skupiny prototypu (EGP) obsahující elementy a jejich vztah odkazy. V tématu [přizpůsobení nástrojů a sady nástrojů](../modeling/customizing-tools-and-the-toolbox.md).<br /><br /> Buď zahrnout obrazce hlavní a portu EGP nebo definujte BoundsRules na pozici tvarů portu při vytváření instance EGP. V tématu [BoundsRules omezit tvar umístění a velikost](../modeling/boundsrules-constrain-shape-location-and-size.md).|
|Použijte jeden nástroj pro připojení k vytváření instancí několik typů relace.|Přidáte odkaz připojit direktivy (LCD) do Tvůrce připojení, která je volána nástrojem. Monitorů LCD Určuje typ vztahu z typů dva elementy. Chcete-li to závisí na stavech elementů, můžete přidat vlastní kód. V tématu [přizpůsobení nástrojů a sady nástrojů](../modeling/customizing-tools-and-the-toolbox.md).|
|Trvalé nástroje – uživatel může dvakrát klikněte na jakýkoli nástroj vytvořit mnoho tvarů nebo konektory za sebou.|V Průzkumníku DSL, vyberte `Editor` uzlu. V okně Vlastnosti nastavte **používá trvalé položek sady nástrojů**.|
|Definování příkazy nabídky|V tématu [postupy: úprava příkazu standardní nabídky](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md)|
|Omezit model s ověřovací pravidla|V tématu [ověření v jazyce specifické pro doménu](../modeling/validation-in-a-domain-specific-language.md)|
|Generování kódu, konfigurační soubory nebo dokumenty z DSL.|[Vytváření kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md)|
|Přizpůsobit jak modely ukládají do souboru.|V tématu [přizpůsobení úložiště File a serializace XML](../modeling/customizing-file-storage-and-xml-serialization.md)|
|Modely uložte do databáze nebo jiného média.|Přepsání *YourLanguage*DocData<br /><br /> V tématu [přizpůsobení úložiště File a serializace XML](../modeling/customizing-file-storage-and-xml-serialization.md)|
|Několik DSL, linky integrate tak, aby fungovaly v rámci jedné aplikace.|V tématu [integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md).|
|Umožňují vaše DSL potřeba rozšířit o třetích stran a řídit rozšíření.|[Rozšíření vašeho DSL pomocí MEF](../modeling/extend-your-dsl-by-using-mef.md)<br /><br /> [Sdílení tříd mezi jazyky specifickými pro doménu (DSL) pomocí knihovny DSL](../modeling/sharing-classes-between-dsls-by-using-a-dsl-library.md)<br /><br /> [Definování zásady zamykání pro vytváření segmentů jen pro čtení](../modeling/defining-a-locking-policy-to-create-read-only-segments.md)|

## <a name="see-also"></a>Viz také

- [Jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md)
- [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)
- [Sada Modeling SDK pro Visual Studio – jazyky specifické pro doménu](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]