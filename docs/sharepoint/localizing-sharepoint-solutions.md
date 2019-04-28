---
title: Lokalizace řešení služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.GlobalAndFeatureResource
- VS.SharePoint.Project.AddResourceDialog
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- globalizing [SharePoint development in Visual Studio]
- localizing [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 90da60cb904ba6e3db2be3805256fcf4eb9122ee
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444346"
---
# <a name="localize-sharepoint-solutions"></a>Lokalizace řešení služby SharePoint

  Proces přípravy aplikací tak, aby bylo možné po celém světě je znám jako lokalizace. Lokalizace je převod prostředků pro konkrétní jazykovou verzi. Další informace najdete v tématu [Globalizing a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md). Toto téma poskytuje přehled o tom, jak lokalizovat řešení služby SharePoint.

 Chcete-li lokalizovat řešení, odeberte z kódu pevně zakódované řetězce a přidáte je do souborů prostředků. Soubor prostředků je [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]– na základě souboru *RESX* rozšíření. Soubor prostředků obsahuje přeložené verze řetězců používané v rámci vašeho řešení. Další informace najdete v tématu [prostředky v aplikacích](http://go.microsoft.com/fwlink/?LinkID=155844).

> [!NOTE]
> Přidejte pouze prostředky řetězců do souborů prostředků řešení služby SharePoint. Přestože Editor prostředků umožňuje přidávat neřetězcové prostředky, neřetězcové prostředky nelze nasazovat do Sharepointu.

## <a name="resource-files"></a>Soubory prostředků
 Existují tři typy souborů prostředků: výchozí, jazykově neutrální a specifické pro jazyk.

|Typ zdrojového souboru|Popis|
|------------------------|-----------------|
|Výchozí|Označované také jako záložní prostředky, výchozí soubory prostředků obsahují řetězce lokalizované pro výchozí jazykovou verzi, například angličtinu. Používají se, pokud lze najít žádné lokalizované soubory prostředků pro určený jazyk. Výchozí prostředky nemají samostatné soubory, jsou uloženy v sestavení hlavní aplikace.|
|Neutrální jazyk|Soubor prostředků obsahující řetězce lokalizované pro jazyk, avšak nikoli konkrétní jazykovou verzi. Například "fr" pro francouzštinu.|
|Specifické pro jazyk|Soubor prostředků obsahující řetězce lokalizované pro jazyk a jazykovou verzi. Například "fr-CA" pro kanadskou francouzštinu.|

 Další informace najdete v tématu [hierarchická organizace zdrojů pro lokalizaci](http://go.microsoft.com/fwlink/?LinkId=178360).

 Chcete-li určit výchozí soubory prostředků v projektech SharePoint, které vyvíjíte v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], zvolte **neutrální jazyk (neutrální země)** ze seznamu jazykových verzí sady **přidat prostředek** dialogu, když jste Přidání zdrojového souboru.

## <a name="localize-visual-studio-sharepoint-solutions"></a>Lokalizace řešení služby SharePoint Visual Studio
 Když lokalizujete řešení, měli byste zvážit všechny textové informace, které se zobrazí uživatelům vašeho řešení. Informační zprávy, chybové zprávy a [!INCLUDE[TLA2#tla_ui](../sharepoint/includes/tla2sharptla-ui-md.md)] řetězce musí být přeloženy a tyto překlady umístěny v souborech prostředků.

 Každý řetězec v souboru prostředků má jedinečný identifikátor. Použijte stejný identifikátor pro řetězce přeložené v každém souboru prostředků. Například pokud je "Řetězec1" identifikátor pro první řetězec v souboru prostředků výchozí, použijte stejný identifikátor pro první řetězec v souborech prostředků specifických pro jazyk.

 Existují tři oblasti, které obvykle lokalizujete ve [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] aplikací služby SharePoint: funkce, stránky ASPX a kód. Pro účely ilustrace v následujících částech Předpokládejme, že máte řešení SharePoint, které chcete lokalizovat do němčiny a japonštiny. Výchozím jazykem je angličtina.

### <a name="localize-features"></a>Lokalizace funkce
 Chcete-li lokalizovat funkci, budete muset nahraďte pevně kódovaného názvu a popisu funkce výrazem, který odkazuje na přeložený nadpis a řetězec v tomto lokalizovaném souboru zdroje. Provedení této změny v **návrháře funkcí** v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [jak: Lokalizace funkce](../sharepoint/how-to-localize-a-feature.md).

 Chcete-li lokalizovat funkci v angličtině do němčiny a japonštiny, přidejte tři položky souborů prostředků projektu do projektu: jeden pro angličtinu, jeden pro němčinu a jeden pro japonštinu. Soubory prostředků funkcí nelze použít k lokalizování ASPX značek nebo kódu. jsou pro ně požadovány samostatné soubory prostředků.

 Jakmile vytvoříte funkci soubory prostředků, přidáte do nich přeložené řetězce. Přístup k lokalizovaným řetězcům pomocí výrazu v následujícím formátu:

```aspx-csharp
$Resources:String ID
```

 Zdroje funkcí v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] jsou vždy pojmenovány prostředky. Pokud vyberete jiný jazyk než neutrální jazyk, pak jazykovou verzi [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] se přidá k názvu souboru prostředků. Například pokud přidáte soubor prostředků neutrální jazyk (výchozí) funkce, je volána *Resources.resx*. Pokud chcete přidat funkce specifické pro jazyk prostředku výběrem kultury japonština (Japonsko), soubor se nazývá *Resources.ja-JP.resx*. Názvy souborů prostředků funkcí jsou automaticky přiřazeny a nedá se změnit.

 Rozsah zdrojů funkcí je místní pro funkci, které se přidají do. Chcete-li vytvořit prostředky, které mohou využívat všechny funkce nebo elementy souboru v řešení, přidejte **globální soubor prostředků** položky projektu namísto funkce zdrojového souboru. **Globální soubor prostředků** položka projektu se nachází v **2010** ve složce **SharePoint** v **přidat novou položku** dialogové okno. Soubory globálních prostředků nasadit do složky \Resources kořenové složky Sharepointu.

### <a name="localize-aspx-page-markup"></a>Lokalizace značky stránky ASPX
 Chcete-li lokalizovat [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] stránek, přidejte tři položky souborů prostředků projektu do projektu: jeden pro angličtinu, jeden pro němčinu a jeden pro japonštinu. Pokud nemáte lokalizovat kód spolu se značkou, můžete místo toho přidat globální soubory prostředků.

 Zadejte název pro soubor prostředků výchozího jazyka. Dejte zdrojovým souborům stejný název s jazykově specifickou kulturu [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]. Například *MyAppResources.de-DE.resx* pro němčinu a *MyAppResources.ja JP.resx* pro japonštinu.

 Nastavte **typ nasazení** vlastnosti každého souboru prostředků na **AppGlobalResource**. To způsobí, že soubory prostředků pro nasazení do složky App_GlobalResources, kde jsou k dispozici pro všechny stránky ASPX a ovládací prvky v řešení. Složka App_GlobalResources je umístěna v C:\inetpub\wwwroot\wss\VirtualDirectories\\< číslo portu\>\App_GlobalResources.

> [!NOTE]
> Pokud používáte jiné globální soubory prostředků, přesuňte je do složky položky projektu, aby vlastnost typ nasazení a další vlastnosti specifické pro SharePoint.

 Soubory prostředků značek ASPX lze také použít k lokalizaci kódu. Pokud používáte prostředky k lokalizaci kódu kromě značek ASPX, nechte akce sestavení vlastnost nastavení každého souboru jako vložený prostředek způsobit, že zdroj kompiloval do satelitního sestavení. Ale pokud používáte pouze k lokalizaci značky soubory prostředků, můžete volitelně změnit akce sestavení na obsah, který zabránit souboru v kompilaci do sestavení hlavní aplikace.

 Nahraďte všechny řetězce pevně zakódovanými vlastnostmi ve vašem kódu stránek a ovládacích prvcích ASPX za výraz v následujícím formátu:

```aspx-csharp
<asp:<class> runat="server" Text="<%$Resources:<Resource File Name>, <String ID>%>" />
```

 Příklad:

```aspx-csharp
<asp:Button ID="btn1" runat="server" onclick="btn1_Click" Text="<%$Resources:Resource1,String7%>"></asp:Button>
```

 Pro ASPX jako text použijte výraz v následujícím formátu:

```aspx-csharp
<asp:literal ID="<ID>" runat="server" Text="<%$Resources:<Resource File Name>, <String ID>%>" />
```

 Příklad:

```aspx-csharp
<asp:literal ID="Literal1" runat="server" Text="<%$Resources:Resource1, String9%>" />
```

 Další informace najdete v tématu [jak: Lokalizace značek ASPX](../sharepoint/how-to-localize-aspx-markup.md).

### <a name="localize-code"></a>Lokalizace kódu
 Kromě lokalizace funkce řetězce a [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] značek, také musíte lokalizovat řetězce zprávy a chybové řetězce, které se zobrazují v kódu řešení. Lokalizované informační a chybové zprávy jsou obsaženy v satelitních sestaveních. Satelitní sestavení obsahují řetězce, které jsou viditelné pro uživatele, jako je například [!INCLUDE[TLA2#tla_ui](../sharepoint/includes/tla2sharptla-ui-md.md)] text a výstupní zprávy, jako jsou výjimky.

 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] používá standardní model střed a paprsek rozhraní .NET Framework. Rozbočovač nebo sestavení hlavní aplikace obsahuje výchozí jazykové prostředky. Paprsky nebo satelitní sestavení obsahují prostředky specifické pro jazyk. Další informace najdete v tématu [Packaging and Deploying Resources](http://go.microsoft.com/fwlink/?LinkId=179280). Satelitní sestavení jsou zkompilovaná ze zdroje (*RESX*) soubory. Když přidáte soubory prostředků specifické pro jazyk do projektu a balíček řešení [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zkompiluje soubory prostředků do satelitních sestavení s názvem *{název projektu}.resources.dll*.

 Stejně jako u značky ASPX můžete Lokalizujte kód aplikace služby SharePoint přidáním samostatných položek projektu souboru prostředků do vašeho projektu. jeden pro výchozí jazyk a jeden pro každý lokalizovaný jazyk. Ale jak bylo zmíněno dříve, pokud již máte soubor prostředků pro lokalizaci značky ASPX, můžete je využít pro lokalizaci kódu. Pokud je potřeba vytvořit soubor prostředků, pojmenujte soubor prostředků výchozího jazyka podle vašeho výběru s příponou *RESX* rozšíření. Pojmenujte zdrojovým souborům stejný název s jazykově specifickou kulturu [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]. Nastavte vlastnost Akce sestavení každého souboru prostředků na integrovaný prostředek a umožněte tak sestavení satelitních prostředků.

 Chcete-li vytvořit satelitní sestavení, sestavte projekt a pak přidejte další sestavení pomocí **Upřesnit** karty **návrháři balíčku**. Pokud přidáte sestavení, předřaďte jazykovou verzi [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] složku pro cestu k umístění, jako například *de-DE\\{název položky projektu}.resources.dll*. To umožňuje balíčku, který bude obsahovat soubory, které mají stejný název.

 Ve vašem kódu nahraďte pevně zakódované řetězce volání <xref:System.Web.HttpContext.GetGlobalResourceObject%2A> metodu pomocí následující syntaxe:

```aspx-csharp
HttpContext.GetGlobalResourceObject("<Resource File Name>", "<String ID>")
```

 Další informace najdete v tématu [jak: Lokalizace kódu](../sharepoint/how-to-localize-code.md).

#### <a name="web-part-code-localization"></a>Lokalizace kódu webové součásti
 Webové součásti zahrnují funkce editoru vlastních vlastností, které obsahují atributy kódu, které používají pevně zakódované řetězce, jako je například WebDisplayName, Category a WebDescription. Chcete-li nahradit řetězec hodnoty pro tyto atributy, vytvořte samostatné třídy, která je odvozena z třídy atributu. V těchto třídách nastavte vlastnost atributu. Vlastnost atributu závisí na základní třídu. Například vlastnost atributu WebDisplayName je DisplayNameValue a vlastnost atributu WebDescription je DescriptionValue.

 V odvozené třídě odkazu na Identifikátor řetězce ze souboru prostředků a objektu ResourceManager získáte lokalizované hodnoty identifikátoru řetězce Vrátí tuto hodnotu na atribut editoru vlastností.

## <a name="see-also"></a>Viz také:
- [Postupy: Lokalizace funkce](../sharepoint/how-to-localize-a-feature.md)
- [Postupy: Lokalizace značek ASPX](../sharepoint/how-to-localize-aspx-markup.md)
- [Postupy: Lokalizace kódu](../sharepoint/how-to-localize-code.md)
- [Postupy: Přidejte soubor prostředků](../sharepoint/how-to-add-a-resource-file.md)
- [Postupy: Určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)
