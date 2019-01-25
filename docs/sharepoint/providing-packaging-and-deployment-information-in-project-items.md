---
title: Poskytování informací o nasazení v položkách projektu a balení | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.SafeControlEntries
- VS.SharePointTools.Project.ProjectOutputReference
- VS.SharePointTools.Project.FeatureProperties
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, safe controls
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, feature properties
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
- feature properties [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, feature receiver
- feature receiver [SharePoint development in Visual Studio]
- safe controls [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 248bf442924ab427b41875272771d2d55708f233
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870071"
---
# <a name="provide-packaging-and-deployment-information-in-project-items"></a>Zadání informací o balení a nasazení v položkách projektu
  Všechny položky Sharepointového projektu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] mít vlastnosti, které můžete použít k poskytnutí dalších údajů, když projekt je nasazen na server SharePoint. Tyto vlastnosti jsou následující:  
  
- Vlastnosti funkce  
  
- Příjemce funkce  
  
- Odkazy na výstup projektu  
  
- Položky bezpečného řízení  
  
  Tyto vlastnosti se zobrazí v **vlastnosti** okna.  
  
## <a name="feature-properties"></a>Vlastnosti funkce
 Použití **vlastnosti funkce** vlastnosti a určit tak data, která používá funkci. Data vlastnosti funkce je sada hodnot (uložených jako páry klíč hodnota), která je součástí funkce při nasazování do služby SharePoint. Po nasazení funkce můžete přistupovat hodnoty vlastností v kódu.  
  
 Když přidáte hodnotu vlastnosti funkce do položky projektu, hodnota se přidá jako elementu v manifestu funkce položky. V projektu obchodní Data připojení (BDC) model například vlastnost funkce ModelFileName zobrazí jako:  
  
```xml  
<Property Key="ModelFileName" Value="BdcModel1\BdcModel1.bdcm" />   
```  
  
 Jakmile nastavíte hodnotu vlastnosti funkce, se přidá jako FeatureProperty – element v projektu *.spdata* souboru. Informace o přístup k vlastnostem ve službě SharePoint, naleznete v tématu [SPFeaturePropertyCollection třídy](http://go.microsoft.com/fwlink/?LinkId=177391).  
  
 Hodnoty vlastností identické funkce ze všech položek projektu jsou sloučeny do manifestu funkce. Nicméně pokud dvě položky jiného projektu zadejte stejný klíč vlastnosti funkce neodpovídající hodnotami, dojde k chybě ověřování.  
  
 Přidání vlastnosti funkcí přímo do souboru funkcí (*.feature*), zavolejte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] metody modelu objektu služby SharePoint <xref:Microsoft.VisualStudio.SharePoint.Features.IPropertyCollection.Add%2A>. Pokud použijete tuto metodu, mějte na paměti, že stejné pravidlo o přidání hodnoty vlastností identické funkce ve vlastnosti funkcí platí také pro vlastnosti přidat přímo do souboru funkcí.  
  
## <a name="feature-receiver"></a>Příjemce funkce
 Příjemce funkce se, že kód, který se spustí při výskytu určitých událostí položky projektu obsahující funkci. Můžete například definovat přijímačů funkce, které jsou spuštěny při instalaci, aktivaci nebo upgradu funkce. Jeden ze způsobů, jak přidat příjemce funkce, je přidat přímo do funkce, jak je popsáno v [názorný postup: Přidání přijímačů událostí funkce](../sharepoint/walkthrough-add-feature-event-receivers.md). Dalším způsobem, je tak, aby odkazovaly název třídy příjemce funkce a sestavení v **příjemce funkce** vlastnost.  
  
### <a name="direct-method"></a>Přímé metody
 Při přidání příjemce funkce do funkce přímo, v části je umístěn soubor s kódem **funkce** uzlu v Průzkumníkovi řešení. Při sestavování řešení služby SharePoint se kód zkompiluje do sestavení a nasazení do služby SharePoint. Ve výchozím nastavení vlastnosti funkce **sestavení příjemce** a **přijímače** odkazovat na název třídy a sestavení.  
  
### <a name="reference-method"></a>Reference – metoda
 Dalším způsobem, jak přidat příjemce funkce je použít **příjemce funkce** vlastnosti položky projektu odkazovat na sestavení příjemce funkce. Hodnota vlastnosti příjemce funkce má dva podvlastnosti: **Sestavení** a **název třídy**. Sestavení musí používat jeho plně kvalifikovaný, "silné" název a název třídy musí být úplný název typu. Další informace najdete v tématu [sestavení se silným názvem](http://go.microsoft.com/fwlink/?LinkID=169573). Po nasazení řešení služby SharePoint, používá funkci příjemce odkazované funkce zpracování událostí funkce.  
  
 Řešení na čas, funkci sestavení příjemce hodnoty vlastností ve funkci a jeho projekty sloučit nastavit atributy ReceiverAssembly a ReceiverClass funkce elementu v manifestu funkce řešení služby SharePoint (*WSP* ) soubor. Proto pokud je zadán název třídy sestavení a hodnoty vlastností položky projektu a funkce, musí odpovídat hodnot vlastností funkce a položky projektu. Pokud hodnoty neshodují, zobrazí se chyba ověření. Pokud chcete položku projektu tak, aby odkazovaly sestavení příjemce funkce jiné než té, jeho funkce používá, ji přesunout do jiné funkce.  
  
 Pokud odkazujete sestavení příjemce funkce, který ještě není na serveru, musíte taky zahrnout samotný soubor sestavení v balíčku. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] nepřidá za vás. Při nasazení funkce sestavení soubor je zkopírován do obou systému [!INCLUDE[TLA#tla_gac](../sharepoint/includes/tlasharptla-gac-md.md)] nebo složce Bin ve fyzickém adresáři služby SharePoint. Další informace najdete v tématu Postupy: [Postupy: Přidání a odebrání dalších sestavení](../sharepoint/how-to-add-and-remove-additional-assemblies.md).  
  
 Další informace o funkci příjemci, naleznete v tématu [příjemce událostí funkce](http://go.microsoft.com/fwlink/?LinkID=169574) a [událostí funkce](http://go.microsoft.com/fwlink/?LinkID=169575).  
  
## <a name="project-output-references"></a>Odkazy na výstup projektu
 Vlastnost odkazy na výstup projektu určuje závislost, jako je například sestavení, které položky projektu je potřeba spustit. Předpokládejme například, zda že má vaše řešení projektu BDC a třídy project. Pokud služby BDC projekt obsahuje závislost na sestavení, která je výstupem projektu tříd, můžete odkazovat na sestavení v projektu BDC odkazy na výstup projektu vlastnost. Když je zabalený projektu BDC, závislé sestavení součástí balíčku.  
  
 Odkazy na výstup projektu jsou obvykle sestavení, ale v některých případech (například projekty technologie Silverlight), může být jiné typy souborů.  
  
 Další informace najdete v tématu [jak: Přidání odkazu na výstup projektu](../sharepoint/how-to-add-a-project-output-reference.md).  
  
## <a name="safe-control-entries"></a>Položky bezpečného řízení
 SharePoint poskytuje mechanismus zabezpečení, volá položky bezpečného řízení, chcete-li omezit přístup nedůvěryhodným uživatelům některé ovládací prvky. Návrh umožňuje SharePoint nedůvěryhodným uživatelům k nahrání a vytvoření stránky ASPX na Sharepointovém serveru. K těmto uživatelům zabránit v přidávání nezabezpečený kód do stránky ASPX, SharePoint omezuje přístup k *bezpečné ovládací prvky*. Bezpečné ovládací prvky jsou ovládacích prvcích ASPX a webovými částmi, které jsou označeny jako bezpečné a, který je možné ji žádný uživatel ve vaší lokalitě. Další informace najdete v tématu [krok 4: Přidat do seznamu bezpečných ovládacích prvků webové části](http://go.microsoft.com/fwlink/?LinkID=171014).  
  
 Každé položky projektu služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] má vlastnost s názvem **položky bezpečných ovládacích prvků** , která má dvě logické objektu třídy subproperties: **Bezpečné** a **zabezpečený proti skriptům**. Bezpečné vlastnost určuje, zda nedůvěryhodným uživatelům můžete přistupovat k ovládacímu prvku. Vlastnost bezpečné vůči skriptu určuje, zda lze nedůvěryhodným uživatelům zobrazení a změna vlastností ovládacího prvku.  
  
 Položky bezpečného řízení je odkazováno na základě sestavení. Přidat položky bezpečného řízení projektu sestavení tak, že zadáte v položce projektu **položky bezpečných ovládacích prvků** vlastnost. Ale můžete také přidat položky bezpečného řízení k sestavení projektu prostřednictvím **Upřesnit** kartu **návrháři balíčku** při přidávání dalších sestavení do balíčku. Další informace najdete v tématu [jak: Označení ovládacích prvků jako bezpečných](../sharepoint/how-to-mark-controls-as-safe-controls.md) nebo [registrace do webové části sestavení jako ovládací prvek bezpečný](http://go.microsoft.com/fwlink/?LinkID=171013).  
  
### <a name="xml-entries-for-safe-controls"></a>Záznamů jazyka XML pro bezpečné ovládací prvky
 Když přidáte položku bezpečný ovládací prvek do položky projektu a sestavení projektu, odkaz je zapsán do manifestu balíčku v následujícím formátu:  
  
```xml  
<Assemblies>  
    <Assembly Location="<assembly name>.dll"     
      DeploymentTarget="<'GlobalAssemblyCache' or 'WebApplication'">>  
        <SafeControls>  
            <SafeControl Assembly="<assembly name>.dll" Namespace=  
              "<SharePoint project name>" Safe="<true/false>"     
                TypeName="<control name>"   
                SafeAgainstScript="<true/false>" />  
        </SafeControls>  
    </Assembly>  
</Assemblies>  
```  
  
## <a name="see-also"></a>Viz také:
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [Vložení souborů do řešení pomocí modulů](../sharepoint/using-modules-to-include-files-in-the-solution.md)   
 [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
