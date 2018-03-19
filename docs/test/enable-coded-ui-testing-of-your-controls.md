---
title: "Povolení programového testování uživatelského rozhraní pro vaše ovládací prvky v sadě Visual Studio | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c6ad93e71c4208fb4d9ce9abd75e2bac554ba238
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="enable-coded-ui-testing-of-your-controls"></a>Povolit testování programového uživatelského rozhraní pro vaše ovládací prvky

Implementovat podporu pro programové rozhraní testování framework aby více možností intenzivního testování vlastního ovládacího prvku. Zvýšení úrovně podpory můžete přidat postupně. Spusťte díky podpoře záznam a přehrávání a vlastnost ověření. Potom stavět na, chcete-li povolit Tvůrce programového testu uživatelského rozhraní, rozpoznat vlastní vlastnosti ovládacího prvku. Zadejte vlastní třídy pro přístup k tyto vlastnosti z generovaného kódu. Může také pomoci programové uživatelského rozhraní test Tvůrce zachycení akce způsobem, který bude co nejblíže ke záměr akce dále zaznamenávána.

![CUIT&#95;Full](../test/media/cuit_full.png "CUIT_Full")

## <a name="support-record-and-playback-and-property-validation-by-implementing-accessibility"></a>Podpora záznam a přehrávání a vlastnost ověření pomocí implementace usnadnění přístupu

Tvůrce programového testu uživatelského rozhraní zaznamená informace o ovládacích prvcích, že dojde během nahrávání a poté generuje kód do opakování této relaci. Pokud vaše řízení nepodporuje usnadnění, Tvůrce programového testu uživatelského rozhraní zaznamená akce (jako jsou kliknutí myší) s použitím souřadnice obrazovky. Při přehrávání testu generovaný kód vydává akce v stejné souřadnice obrazovky. Pokud vlastní ovládací prvek se zobrazuje na jiné místo na obrazovce při přehrávání testu, se nezdaří generovaný kód provést akci. Usnadnění pro ovládací prvek není implementací, může se zobrazit testování selhání testu přehrávání na různých obrazovek konfigurace v různých prostředích, nebo když se změní rozložení uživatelského rozhraní.

 ![CUIT&#95;RecordNoSupport](../test/media/cuit_recordnosupport.png "CUIT_RecordNoSupport")

 Pokud budete implementovat usnadnění, Tvůrce programového testu uživatelského rozhraní použije k zaznamenání informací o kontrolu nad při nahrávání testu. Poté při spuštění testu generovaný kód bude opakování tyto události pro ovládací prvek, i když je někde jinde v uživatelském rozhraní. Můžete také vytvořit testovací autoři vyhodnotí pomocí základní vlastnosti vlastního ovládacího prvku.

 ![CUIT&#95;Record](../test/media/cuit_record.png "CUIT_Record")

### <a name="to-support-record-and-playback-property-validation-and-navigation-for-a-windows-forms-control"></a>Pro podporu záznam a přehrávání, ověření vlastností a navigace pro ovládací prvek Windows Forms
 Implementace usnadnění pro ovládací prvek, jak je uvedeno v následujícím postupu a podrobně vysvětleny v <xref:System.Windows.Forms.AccessibleObject>.

 ![CUIT&#95;Accessible](../test/media/cuit_accessible.png "CUIT_Accessible")

1.  Implementovat třídu odvozenou od <xref:System.Windows.Forms.Control.ControlAccessibleObject>a přepsat <xref:System.Windows.Forms.Control.AccessibilityObject%2A> vlastnost, která má vrátit objekt vaší třídy.

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

2.  Přepsání dostupný objekt <xref:System.Windows.Forms.AccessibleObject.Role%2A>, <xref:System.Windows.Forms.AccessibleObject.State%2A>, <xref:System.Windows.Forms.AccessibleObject.GetChild%2A> a <xref:System.Windows.Forms.AccessibleObject.GetChildCount%2A> vlastnosti a metody.

3.  Implementovat jiný objekt usnadnění pro podřízený ovládací prvek a přepsat podřízeného ovládacího prvku <xref:System.Windows.Forms.Control.AccessibilityObject%2A> vlastnost vrátit objekt usnadnění.

4.  Přepsání <xref:System.Windows.Forms.AccessibleObject.Bounds%2A>, <xref:System.Windows.Forms.AccessibleObject.Name%2A>, <xref:System.Windows.Forms.AccessibleObject.Parent%2A>, <xref:System.Windows.Forms.AccessibleObject.Role%2A>, <xref:System.Windows.Forms.AccessibleObject.State%2A>, <xref:System.Windows.Forms.AccessibleObject.Navigate%2A>, a <xref:System.Windows.Forms.AccessibleObject.Select%2A> vlastnosti a metody pro objekt usnadnění podřízeného ovládacího prvku.

> [!NOTE]
> Toto téma začíná přístupnosti ukázce v <xref:System.Windows.Forms.AccessibleObject>a pak vytvoří v této ukázkové v podle zbývajících pokynů. Pokud chcete vytvořit pracovní verzi přístupnosti ukázce, vytvořte konzolovou aplikaci a pak nahraďte kód v souboru Program.cs s ukázkový kód. Přidejte odkazy na usnadnění, System.Drawing a System.Windows.Forms. Změna **vložit zprostředkovatel komunikace s objekty typy** pro usnadnění přístupu k **False** eliminovat upozornění sestavení. Můžete změnit typ výstupu projektu z **konzolové aplikace** k **aplikace Windows** tak, aby se nezobrazí okno konzoly při spuštění aplikace.

## <a name="support-custom-property-validation-by-implementing-a-property-provider"></a>Podporují vlastní vlastnosti ověření implementací vlastnost poskytovatele

Po implementaci základní podpora pro záznam a přehrávání a vlastnost ověření můžete zpřístupnit vlastní vlastnosti ovládacího prvku pro programové testy uživatelského rozhraní implementací <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> modulu plug-in. Následující postup se například vytvoří vlastnost poskytovatele, který umožňuje programové testy uživatelského rozhraní pro přístup k vlastnosti State ovládací prvek graf CurveLegend podřízených ovládacích prvků:

 ![CUIT&#95;CustomProps](../test/media/cuit_customprops.png "CUIT_CustomProps")

### <a name="to-support-custom-property-validation"></a>Pro podporu ověřování vlastní vlastnosti

![CUIT&#95;Props](../test/media/cuit_props.png "CUIT_Props")

1. Přepsání křivky legendy přístupné objektu <xref:System.Windows.Forms.AccessibleObject.Description%2A> vlastnost k předání bohaté vlastnost hodnot v řetězci popis. Více hodnot oddělujte středníkem (;).

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

1. Vytvořte balíček rozšíření testu uživatelského rozhraní pro vlastní ovládací prvek vytvořením projektu knihovny tříd. Přidejte odkazy na usnadnění, Microsoft.VisualStudio.TestTools.UITesting, Microsoft.VisualStudio.TestTools.UITest.Common a Microsoft.VisualStudio.TestTools.Extension. Změna **přibalit definované typy** pro usnadnění přístupu k **False**.

1. Přidání třídy zprostředkovatele vlastnost, která je odvozena z <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>:

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

1. Implementaci zprostředkovatele vlastnost tím, že názvy vlastností a vlastnost popisovačů v <xref:System.Collections.Generic.Dictionary%602>.

1. Přepsání <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A?displayProperty=fullName> indikující, že vaše sestavení poskytuje podporu specifické pro ovládací prvek pro vlastní ovládací prvek a jeho podřízených položek.

1. Přepsání zbývající abstraktní metody <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider?displayProperty=fullName>

1. Přidání třídy balíček rozšíření, který je odvozený od <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>.

1. Definování `UITestExtensionPackage` atribut pro sestavení.

1. Ve třídě balíček rozšíření přepsat <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A?displayProperty=fullName> má vrátit třídu vlastnost poskytovatele, pokud je požadovaná vlastnost poskytovatele.

1. Přepsání zbývající abstraktní metody a vlastnosti <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>.

1. Sestavení vaší binární soubory a zkopírujte je do **%ProgramFiles%\Common\Microsoft Shared\VSTT\10.0\UITestExtensionPackages**.

> [!NOTE]
> Tento balíček rozšíření se použije pro libovolný ovládací prvek, který je typu "Text". Pokud testujete více ovládacích prvků stejného typu, testovat je samostatně, můžete spravovat, které balíčky rozšíření nasazených při záznamu testy.

## <a name="support-code-generation-by-implementing-a-class-to-access-custom-properties"></a>Podpora generování kódu pomocí implementace třídy pro přístup k vlastní vlastnosti

Tvůrce programového testu uživatelského rozhraní generuje kód ze záznamu relace, používá <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl> třídu pro vaše ovládací prvky přístup.

Pokud jste implementovali vlastnost poskytovatele poskytnout přístup k vlastní vlastnosti ovládacího prvku, můžete přidat specializované třídu, která se používá pro přístup k tyto vlastnosti. Přidání Specializovaná třída zjednodušuje generovaného kódu.

### <a name="to-add-a-specialized-class-to-access-your-control"></a>Postup přidání specializované třídy pro přístup k vlastní ovládací prvek

![CUIT&#95;CodeGen](../test/media/cuit_codegen.png "CUIT_CodeGen")

1. Implementace třídy, který je odvozený od <xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls.WinControl> a přidejte typ ovládacího prvku do kolekce vlastností vyhledávání v konstruktoru.

1. Implementujte vlastní vlastnosti ovládacího prvku jako vlastnosti třídy.

1. Přepsání poskytovatele vlastnost <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetSpecializedClass%2A?displayProperty=fullName> metoda vrátí typ novou třídu pro křivku legendy podřízených ovládacích prvků.

1. Přepsání poskytovatele vlastnost <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetPropertyNamesClassType%2A> metoda vrátí typ metody PropertyNames novou třídu.

## <a name="support-intent-aware-actions-by-implementing-an-action-filter"></a>Podporují deklaracemi záměr akce implementací filtr akce

 Když Visual Studio zaznamenává testu, zaznamená jednotlivých událostí myši a klávesnice. Ale v některých případech záměr akce může dojít ke ztrátě řady událostí myši a klávesnice. Například pokud vlastní ovládací prvek podporuje automatické dokončování, stejnou sadu událostí myši a klávesnice, které může vést k jiné hodnoty při při testu přehrávání v jiném prostředí. Můžete přidat filtr akce modul plug-in, nahradí jednu akci řadu události klávesnice a myši. Tímto způsobem můžete nahradit řadu událostí myši a klávesnice, které vyberte hodnotu jedinou akcí, které nastavuje hodnotu. Programové testy uživatelského rozhraní učinit chrání před rozdíly v automatického dokončování z jednoho prostředí do druhého.

### <a name="to-support-intent-aware-actions"></a>Pro podporu deklaracemi záměr akce

![CUIT&#95;Actions](../test/media/cuit_actions.png "CUIT_Actions")

1. Implementace třídy filtru akce, který je odvozený od <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>, přepisování vlastnosti <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> a <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A>.

1. Přepsání <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ProcessRule%2A>. Tady příklad akce poklikejte na soubor nahradí akce jedním kliknutím.

1. Přidat filtr akce <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> metoda vašeho balíčku rozšíření.

1. Sestavení vaší binární soubory a zkopírujte je do %ProgramFiles%\Common Files\Microsoft Shared\VSTT\10.0\UITestExtensionPackages.

> [!NOTE]
> Filtr akce nezávisí na implementaci usnadnění nebo na poskytovateli vlastnost.

## <a name="debug-your-property-provider-or-action-filter"></a>Ladění vlastnost zprostředkovatele nebo akce filtru

Vlastnosti zprostředkovatele a akce filtru jsou implementované v balíčku rozšíření. Tvůrce testu spustí balíček rozšíření v samostatný proces z vaší aplikace.

### <a name="to-debug-your-property-provider-or-action-filter"></a>Chcete-li ladit vlastnosti zprostředkovatele nebo akce filtru

1.  Sestavení ladicí verze vaší kopie balíčku rozšíření knihovna .dll a soubory PDB do %ProgramFiles%\Common Files\Microsoft Shared\VSTT\10.0\UITestExtensionPackages.

2.  Spusťte svoji aplikaci (ne v ladicím programu).

3.  Spuštění Tvůrce programového testu uživatelského rozhraní.

     `codedUITestBuilder.exe  /standalone`

4.  Připojí ladicí program codedUITestBuilder procesu.

5.  Nastavte zarážky v kódu.

6.  V Tvůrci programových testů uživatelského rozhraní vytvořit vyhodnotí prověření poskytovatel vlastnost a záznamů akcí k výkonu filtry akce.

## <a name="see-also"></a>Viz také

- <xref:System.Windows.Forms.AccessibleObject>
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)