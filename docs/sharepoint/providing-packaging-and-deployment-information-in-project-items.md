---
title: "Poskytnutí balení a informace o nasazení v položkách projektu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.SafeControlEntries
- VS.SharePointTools.Project.ProjectOutputReference
- VS.SharePointTools.Project.FeatureProperties
dev_langs:
- VB
- CSharp
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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: adc98932391e726e1704ebe88ec0a9120f7bb678
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="providing-packaging-and-deployment-information-in-project-items"></a>Poskytování informací o balení a nasazení v položkách projektu
  Všechny položky projektu služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] mají vlastnosti, které můžete použít k poskytnutí dalších údajů při nasazení projektu do služby SharePoint. Tyto vlastnosti jsou následující:  
  
-   Vlastnosti funkcí  
  
-   Příjemce funkce  
  
-   Odkazy na výstup projektu  
  
-   Bezpečné ovládací prvek položky  
  
 Tyto vlastnosti se zobrazí v **vlastnosti** okno.  
  
## <a name="feature-properties"></a>Vlastnosti funkcí  
 Použití **vlastnosti funkcí** vlastnosti a určit data, která používá funkci. Data funkce vlastnosti je sadu hodnot (uložené jako páry klíč – hodnota), která je součástí funkce při nasazování do služby SharePoint. Po nasazení funkce můžete přistupovat hodnoty vlastností v kódu.  
  
 Přidáte-li hodnotu vlastnosti funkce položka projektu, hodnota se přidá jako element v manifestu funkce položky. V projektu model Business Data Connectivity (BDC) například vlastnost funkce ModelFileName vypadá takhle:  
  
```  
<Property Key="ModelFileName" Value="BdcModel1\BdcModel1.bdcm" />   
```  
  
 Jakmile nastavíte hodnotu vlastnosti funkce, se přidá jako FeatureProperty – element v souboru .spdata projektu. Informace o přístup k vlastnostem ve službě SharePoint najdete v tématu [SPFeaturePropertyCollection třída](http://go.microsoft.com/fwlink/?LinkId=177391).  
  
 Hodnoty vlastností identické funkce ze všech položek projektu se sloučí v manifestu funkce. Ale pokud dvě položky jiný projekt zadat stejný klíč vlastnost funkce s neodpovídající hodnoty, dojde k chybě ověření.  
  
 Přidání vlastnosti funkcí přímo do souboru funkcí (* .feature), volání [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint objektu modelu metoda <xref:Microsoft.VisualStudio.SharePoint.Features.IPropertyCollection.Add%2A>. Pokud použijete tuto metodu, mějte na paměti, že stejného pravidla o přidání hodnoty vlastností identické funkce ve vlastnostech funkce platí také pro vlastnosti přidat přímo do souboru funkce.  
  
## <a name="feature-receiver"></a>Příjemce funkce  
 Příjemce funkce jsou kód, který provede při určité události položka projektu obsahující funkce. Můžete například definovat přijímačů funkce, které se spouští při funkci je nainstalován, aktivovat nebo upgradovat. Jeden ze způsobů, jak přidat příjemce funkce je přidat přímo na funkce, jak je popsáno v [návod: Přidání přijímačů událostí funkce](../sharepoint/walkthrough-add-feature-event-receivers.md). Kliknutím na odkaz název třídy příjemce funkce a sestavení v **příjemce funkce** vlastnost.  
  
### <a name="direct-method"></a>Přímá metoda  
 Když přidáte příjemce funkce funkce přímo, kód soubor je umístěn v **funkce** uzlu v Průzkumníku řešení. Při sestavování řešení služby SharePoint, kód zkompiluje do sestavení a nasadí do služby SharePoint. Ve výchozím nastavení vlastnosti funkcí **sestavení příjemce** a **příjemce třída** odkazovat na název třídy a sestavení.  
  
### <a name="reference-method"></a>Reference – metoda  
 Jiný způsob, jak přidat příjemce funkce je pomocí **příjemce funkce** vlastnosti položky projektu k odkazování sestavení příjemce funkce. Hodnota vlastnosti příjemce funkce má dva podvlastnosti: **sestavení** a **název třídy**. Sestavení musí používat jeho plně kvalifikovaný, "silné" název a název třídy musí být název úplné typu. Další informace najdete v tématu [sestavení se silným názvem](http://go.microsoft.com/fwlink/?LinkID=169573). Po nasazení řešení do služby SharePoint, používá funkci příjemce odkazované funkce zpracování událostí funkce.  
  
 V okamžiku sestavení řešení slučte hodnoty vlastností příjemce funkce ve funkci a jeho projekty nastavit ReceiverAssembly a ReceiverClass atributy elementu funkce v manifestu funkce soubor řešení (WSP) služby SharePoint. Proto pokud je zadán název třídy sestavení a hodnoty vlastností položka projektu a funkce, se musí shodovat projektu hodnoty vlastností položky a funkce. Pokud se hodnoty neshodují, obdržíte chybu ověření. Pokud chcete, aby položka projektu pro odkazování sestavení příjemce funkce než jeho funkce používá, ho přesunout do jiné funkce.  
  
 Pokud odkazujete sestavení funkce příjemce, který ještě není na serveru, musíte taky zahrnout samotný soubor sestavení v balíčku. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] nepřidá za vás. Když nasadíte tuto funkci, soubor sestavení je zkopírován do buď systému [!INCLUDE[TLA#tla_gac](../sharepoint/includes/tlasharptla-gac-md.md)] nebo na složku Koš ve fyzický adresář služby SharePoint. Další informace najdete v tématu Postupy: [postupy: Přidání a odebrání dalších sestavení](../sharepoint/how-to-add-and-remove-additional-assemblies.md).  
  
 Další informace o přijímačů funkce najdete v tématu [příjemce událostí funkce](http://go.microsoft.com/fwlink/?LinkID=169574) a [funkce události](http://go.microsoft.com/fwlink/?LinkID=169575).  
  
## <a name="project-output-references"></a>Odkazy na výstup projektu  
 Vlastnost odkazy na výstup projektu určuje závislost, například sestavení, která položka vašeho projektu je potřeba spustit. Předpokládejme například, že má vaše řešení BDC projekt a projekt – třída. Pokud projekt BDC má závislost na sestavení, které je výstup třídy projektu, můžete odkazovat sestavení ve vlastnosti projektu BDC odkazy na výstup projektu. Když je zabalené BDC projektu, závislého sestavení součástí balíčku.  
  
 Odkazy na výstup projektu jsou obvykle sestavení, ale v některých případech (například projekty Silverlight), může být jiné typy souborů.  
  
 Další informace najdete v tématu [postupy: Přidání odkazu na výstup projektu](../sharepoint/how-to-add-a-project-output-reference.md).  
  
## <a name="safe-control-entries"></a>Bezpečné ovládací prvek položky  
 SharePoint poskytuje mechanismus zabezpečení, nazývaná bezpečné řízení položky, chcete-li omezit přístup nedůvěryhodným uživatelům některé ovládací prvky. Návrh SharePoint umožňuje nedůvěryhodným uživatelům nahrát a vytvářet stránky ASPX na serveru SharePoint. Tyto uživatelům zabránit v přidání nezabezpečený kód na stránky ASPX, SharePoint omezuje svůj přístup k *bezpečné ovládací prvky*. Bezpečné ovládací prvky jsou ovládací prvky ASPX a webových částí, které jsou označeny jako bezpečné a který můžete použít kterýkoli uživatel na svém webu. Další informace najdete v tématu [krok 4: Přidat webovou část na bezpečné ovládací prvky seznamu](http://go.microsoft.com/fwlink/?LinkID=171014).  
  
 Každá položka projektu služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] má vlastnost s názvem **bezpečné položky řízení** , má dva Boolean podvlastnosti: **bezpečné** a **skriptu bezpečné proti**. Bezpečné vlastnost určuje, jestli se má nedůvěryhodným uživatelům přístup k ovládacím prvku. Vlastnost bezpečné proti skriptu určuje, zda můžete nedůvěryhodným uživatelům zobrazení a změna vlastností ovládacího prvku.  
  
 Bezpečné ovládací prvek položky je odkazováno na základě sestavení. Přidat položky bezpečné řízení projektu sestavení tak, že zadáte je položka projektu **bezpečné položky řízení** vlastnost. Ale můžete také přidat položky bezpečné řízení pro sestavení projektu prostřednictvím **Upřesnit** ve **návrháře balíčků** při přidávání dalších sestavení do balíčku. Další informace najdete v tématu [postup: ovládací prvky označit jako bezpečné ovládací prvky](../sharepoint/how-to-mark-controls-as-safe-controls.md) nebo [registrace sestavení webové části jako bezpečné ovládací prvek](http://go.microsoft.com/fwlink/?LinkID=171013).  
  
### <a name="xml-entries-for-safe-controls"></a>Položky XML pro bezpečné ovládací prvky  
 Když přidáte položku bezpečné řízení položka projektu a sestavení projektu, odkaz je zapsán do manifestu balíčku v následujícím formátu:  
  
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
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [Vložené soubory v řešení pomocí modulů](../sharepoint/using-modules-to-include-files-in-the-solution.md)   
 [Rozšíření balení a nasazení SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  