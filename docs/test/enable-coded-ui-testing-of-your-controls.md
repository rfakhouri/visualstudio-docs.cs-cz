---
title: Povolení programového testování uživatelského rozhraní pro vaše ovládací prvky
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 98eb2df0d846fa542ec01b30ad5abfffa62ff54f
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918265"
---
# <a name="enable-coded-ui-testing-of-your-controls"></a>Povolení programového testování uživatelského rozhraní pro vaše ovládací prvky

Implementujte podporu pro rozhraní programového testování uživatelského rozhraní, abyste měli svůj ovládací prvek větší testovatelné. Zvýšení úrovně podpory můžete přidat přírůstkově. Začněte podporou záznamu a přehrávání a ověření vlastností. Pak Sestavte to tak, aby povoloval Tvůrce programového testu uživatelského rozhraní pro rozpoznávání vlastních vlastností ovládacího prvku. Poskytněte vlastní třídy pro přístup k těmto vlastnostem z generovaného kódu. Můžete také pomáhat Tvůrce programového testu UI zachytávání akcí způsobem, který je blíže záměru zaznamenané akce.

![UI&#95;plná](../test/media/cuit_full.png)

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

## <a name="support-record-and-playback-and-property-validation-by-implementing-accessibility"></a>Podpora záznamů a přehrávání a ověřování vlastností implementací přístupnosti

Tvůrce programového testu uživatelského rozhraní zachycuje informace o ovládacích prvcích, ke kterým dojde během záznamu, a pak vygeneruje kód pro přehrání této relace. Pokud váš ovládací prvek nepodporuje přístupnost, program Tvůrce programového testu UI zachytí akce (například kliknutí myší) pomocí souřadnic obrazovky. Po přehrání testu vygeneruje generovaný kód akce na stejných souřadnicích obrazovky. Pokud se ovládací prvek zobrazí na jiném místě na obrazovce při přehrání testu, vygenerovaný kód selže při provádění akce. Neimplementací přístupnosti pro váš ovládací prvek se může zobrazit chyba testu, pokud se test přehrává v různých konfiguracích obrazovky, v různých prostředích nebo při změně rozložení uživatelského rozhraní.

![UI&#95;RecordNoSupport](../test/media/cuit_recordnosupport.png)

Pokud implementujete přístupnost, Tvůrce programového testu uživatelského rozhraní používá tuto funkci k zachycení informací o vašem ovládacím prvku při záznamu testu. Poté, když spustíte test, vygenerovaný kód přehraje tyto události proti vašemu ovládacímu prvku, i v případě, že je někde jinde v uživatelském rozhraní. Autoři testů mohou také vytvořit výrazy s použitím základních vlastností ovládacího prvku.

![Záznam&#95;UI](../test/media/cuit_record.png)

### <a name="to-support-record-and-playback-property-validation-and-navigation-for-a-windows-forms-control"></a>Podpora záznamu a přehrávání, ověřování vlastností a navigace pro ovládací prvek model Windows Forms
Implementujte přístupnost pro váš ovládací prvek, jak je uvedeno v následujícím postupu, a podrobně vysvětleno <xref:System.Windows.Forms.AccessibleObject>v.

![UI&#95;přístupný](../test/media/cuit_accessible.png)

1. Implementujte třídu, která je odvozena z <xref:System.Windows.Forms.Control.ControlAccessibleObject>a <xref:System.Windows.Forms.Control.AccessibilityObject%2A> přepište vlastnost, která vrátí objekt vaší třídy.

    ```csharp
    public partial class ChartControl : UserControl
    {
        // Overridden to return the custom AccessibleObject for the control.
        protected override AccessibleObject CreateAccessibilityInstance()
        {
            return new ChartControlAccessibleObject(this);
        }

        // Inner class ChartControlAccessibleObject represents accessible information
        // associated with the ChartControl and is used when recording tests.
        public class ChartControlAccessibleObject : ControlAccessibleObject
        {
            ChartControl myControl;
            public ChartControlAccessibleObject(ChartControl ctrl)
                : base(ctrl)
            {
                myControl = ctrl;
            }
        }
    }
    ```

2. Přepište <xref:System.Windows.Forms.AccessibleObject.GetChildCount%2A> vlastnosti a metody <xref:System.Windows.Forms.AccessibleObject.Role%2A>přístupného <xref:System.Windows.Forms.AccessibleObject.GetChild%2A> objektu <xref:System.Windows.Forms.AccessibleObject.State%2A>.

3. Implementujte další objekt usnadnění pro podřízený ovládací prvek a přepište <xref:System.Windows.Forms.Control.AccessibilityObject%2A> vlastnost podřízeného ovládacího prvku tak, aby vracela objekt usnadnění.

4. <xref:System.Windows.Forms.AccessibleObject.Name%2A> <xref:System.Windows.Forms.AccessibleObject.Parent%2A> Přepište<xref:System.Windows.Forms.AccessibleObject.Role%2A>vlastnosti,,, ,<xref:System.Windows.Forms.AccessibleObject.State%2A>, a<xref:System.Windows.Forms.AccessibleObject.Navigate%2A>ametody objektu usnadnění podřízeného ovládacího prvku. <xref:System.Windows.Forms.AccessibleObject.Bounds%2A> <xref:System.Windows.Forms.AccessibleObject.Select%2A>

> [!NOTE]
> V tomto tématu se začíná ukázka přístupnosti v <xref:System.Windows.Forms.AccessibleObject>nástroji a potom se v této ukázce vytvoří ve zbývajících postupech. Pokud chcete vytvořit funkční verzi ukázky přístupnosti, vytvořte konzolovou aplikaci a potom nahraďte kód v *program.cs* ukázkovým kódem. Přidejte odkazy na přístupnost, System. Drawing a System. Windows. Forms. Chcete-li odstranit upozornění sestavení, změňte **typy spolupráce pro vložení** pro přístupnost na **false** . Výstupní typ projektu lze změnit z **konzolové aplikace** na **aplikaci systému Windows** , aby se okno konzoly nezobrazovalo při spuštění aplikace.

## <a name="support-custom-property-validation-by-implementing-a-property-provider"></a>Podpora ověřování vlastních vlastností implementací zprostředkovatele vlastností

Po implementaci základní podpory pro záznam a přehrávání a ověřování vlastností můžete nastavit vlastní vlastnosti ovládacího prvku k dispozici pro programové testy uživatelského rozhraní implementací <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> modulu plug-in. Následující procedura například vytvoří poskytovatele vlastností, který umožňuje programovým testům uživatelského rozhraní získat přístup k vlastnosti State pro podřízené ovládací prvky CurveLegend ovládacího prvku grafu:

![UI&#95;CustomProps](../test/media/cuit_customprops.png)

### <a name="to-support-custom-property-validation"></a>Podpora ověřování vlastních vlastností

![UI&#95;props](../test/media/cuit_props.png)

1. Přepište <xref:System.Windows.Forms.AccessibleObject.Description%2A> vlastnost přístupného objektu legendy křivky tak, aby předávala hodnoty vlastností v řetězci popisu. Více hodnot oddělte středníkem (;).

    ```csharp
    public class CurveLegendAccessibleObject : AccessibleObject
    {
        // add the state property value to the description
        public override string Description
        {
            get
            {
                // Add ";" and the state value to the end
                // of the curve legend's description
                return "CurveLegend; " + State.ToString();
            }
        }
    }
    ```

1. Vytvořte balíček rozšíření pro test uživatelského rozhraní pro váš ovládací prvek vytvořením projektu knihovny tříd. Přidejte odkazy na přístupnost, Microsoft. VisualStudio. TestTools. UITesting, Microsoft. VisualStudio. TestTools. UITest. Common a Microsoft. VisualStudio. TestTools. extension. Změňte **typy spolupráce pro vložení** pro přístupnost na **false**.

1. Přidat třídu poskytovatele vlastností, která je odvozena <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>z:

    ```csharp
    using System;
    using System.Collections.Generic;
    using Accessibility;
    using Microsoft.VisualStudio.TestTools.UITesting;
    using Microsoft.VisualStudio.TestTools.UITest.Extension;
    using Microsoft.VisualStudio.TestTools.UITesting.WinControls;
    using Microsoft.VisualStudio.TestTools.UITest.Common;

    namespace ChartControlExtensionPackage
    {
        public class ChartControlPropertyProvider : UITestPropertyProvider
        {
        }
    }
    ```

1. Implementací názvů vlastností a popisovačů vlastností do vytvořte <xref:System.Collections.Generic.Dictionary%602>zprostředkovatele vlastností.

1. Přepsání <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A?displayProperty=fullName> k označení toho, že vaše sestavení poskytuje podporu pro konkrétní ovládací prvek a jeho podřízené prvky.

1. Přepsat zbývající abstraktní metody<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider?displayProperty=fullName>

1. Přidejte třídu balíčku rozšíření, která je odvozena <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>z.

1. `UITestExtensionPackage` Definujte atribut pro sestavení.

1. V rámci třídy balíčku rozšíření přepište <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A?displayProperty=fullName> , aby vracel třídu poskytovatele vlastností, když je vyžádán poskytovatel vlastností.

1. Přepište zbývající abstraktní metody a vlastnosti <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>.

1. Sestavte binární soubory a zkopírujte je do *%ProgramFiles%\Common\Microsoft Shared\VSTT\10.0\UITestExtensionPackages*.

> [!NOTE]
> Tento balíček rozšíření se použije na libovolný ovládací prvek, který je typu "text". Pokud testujete více ovládacích prvků stejného typu, otestujte je samostatně, abyste mohli spravovat, které balíčky rozšíření budou nasazeny při záznamu testů.

## <a name="support-code-generation-by-implementing-a-class-to-access-custom-properties"></a>Podpora generování kódu implementací třídy pro přístup k vlastním vlastnostem

Když Tvůrce programového testu uživatelského rozhraní generuje kód ze záznamu relace, používá <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl> třídu pro přístup k ovládacím prvkům.

Pokud jste implementovali poskytovatele vlastností k poskytnutí přístupu k vlastním vlastnostem ovládacího prvku, můžete přidat specializovanou třídu, která se používá pro přístup k těmto vlastnostem. Přidání specializované třídy zjednodušuje vygenerovaný kód.

### <a name="to-add-a-specialized-class-to-access-your-control"></a>Přidání specializované třídy pro přístup k ovládacímu prvku

![UI&#95;CodeGen](../test/media/cuit_codegen.png)

1. Implementujte třídu, která je odvozena z <xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls.WinControl> a přidejte typ ovládacího prvku do kolekce vlastností vyhledávání v konstruktoru.

1. Implementujte vlastní vlastnosti ovládacího prvku jako vlastnosti třídy.

1. Přepište <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetSpecializedClass%2A?displayProperty=fullName> metodu poskytovatele vlastnosti tak, aby vracela typ nové třídy pro podřízené ovládací prvky legendy křivky.

1. Přepište <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetPropertyNamesClassType%2A> metodu poskytovatele vlastností, aby vracela typ nové metody ' PropertyNames ' třídy.

## <a name="support-intent-aware-actions-by-implementing-an-action-filter"></a>Akce podporující záměry podpory implementací filtru akcí

Když aplikace Visual Studio zaznamená test, zachytí každou událost myši a klávesnice. V některých případech však může být záměr akce ztracen v řadě událostí myši a klávesnice. Například pokud váš ovládací prvek podporuje automatické dokončování, stejná sada událostí myši a klávesnice může mít za následek jinou hodnotu, když je test přehrán v jiném prostředí. Můžete přidat modul plug-in filtru akcí, který nahradí řadu událostí klávesnice a myši jedinou akcí. Tímto způsobem můžete nahradit řadu událostí myši a klávesnice, které vyberou hodnotu jedinou akcí, která nastaví hodnotu. Provádí ochranu programových testů uživatelského rozhraní z rozdílů v automatickém dokončování z jednoho prostředí do druhého.

### <a name="to-support-intent-aware-actions"></a>Pro podporu akcí s podporou záměrů

![Akce&#95;UI](../test/media/cuit_actions.png)

1. Implementujte třídu filtru akcí, která je odvozena z [UITestActionFilter](/previous-versions/visualstudio/visual-studio-2012/dd985757(v=vs.110))a přepíše vlastnosti [ApplyTimeout](/previous-versions/visualstudio/visual-studio-2012/dd984649%28v%3dvs.110%29), [Category](/previous-versions/visualstudio/visual-studio-2012/dd986905(v=vs.110)), [Enabled](/previous-versions/visualstudio/visual-studio-2012/dd985633(v=vs.110)), [FilterType](/previous-versions/visualstudio/visual-studio-2012/dd778726(v=vs.110)), [Group](/previous-versions/visualstudio/visual-studio-2012/dd779219(v=vs.110)) a [Name](/previous-versions/visualstudio/visual-studio-2012/dd998334(v=vs.110)).

1. Přepsat [ProcessRule](/previous-versions/visualstudio/visual-studio-2012/dd987281(v=vs.110)). Tento příklad nahrazuje akci dvakrát kliknout pomocí akce jediného kliknutí.

1. Přidejte filtr akce do <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> metody balíčku rozšíření.

1. Sestavte binární soubory a zkopírujte je do *%ProgramFiles%\Common Files\Microsoft Shared\VSTT\10.0\UITestExtensionPackages*.

> [!NOTE]
> Filtr akcí nezávisí na implementaci přístupnosti nebo na poskytovateli vlastností.

## <a name="debug-your-property-provider-or-action-filter"></a>Ladění poskytovatele vlastností nebo filtru akcí

Váš zprostředkovatel vlastností a filtr akcí jsou implementovány v balíčku rozšíření. Nástroj test Builder spustí balíček rozšíření v samostatném procesu z aplikace.

### <a name="to-debug-your-property-provider-or-action-filter"></a>Ladění poskytovatele vlastností nebo filtru akcí

1. Sestavení ladicí verze balíčku pro rozšíření zkopírujte soubory *. dll* a *. pdb* do *%ProgramFiles%\Common Files\Microsoft Shared\VSTT\10.0\UITestExtensionPackages*.

2. Spusťte aplikaci (není v ladicím programu).

3. Spusťte Tvůrce programového testu uživatelského rozhraní.

     `codedUITestBuilder.exe  /standalone`

4. Připojte ladicí program k procesu codedUITestBuilder.

5. Nastavte zarážky v kódu.

6. V Tvůrci programového testu uživatelského rozhraní Vytvořte výrazy, které budou uplatňovat poskytovatele vlastností, a zaznamenejte akce pro uplatnění filtrů akcí.

## <a name="see-also"></a>Viz také:

- <xref:System.Windows.Forms.AccessibleObject>
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)